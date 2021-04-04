---
title: Learning to let go of CSS control
date: 2017-08-13 10:50:10
tags:
  - blog
  - css
  - architecture
---

Now that I've embraced React and Redux as my javascript framework of choice and have been building with it full time on the last few projects and interesting shift in the way I view CSS has begun.

Previously I would use a pretty minimal set of partials to bootstrap the styles of an application and I would grow that structure as new features were added on and new variables or mix-ins were required. With React I'm now seeing the vision of a component based architecture realized and this more global approach to styles feels like more of an anti-pattern. Through architecting these component based systems I'm still finding there are uses for some degree of global scope for things like grids for layout so to leverage the best of both worlds I've found CSS modules to provide a nice balance.

To demonstrate here is how my typical component structure is setup.

```
/Button
  /Button.js
  /index.js
  /Button.scss
```

Now typically I would pull in partials in the scss file and attempt to style for all of the permutations that I want to use my button for.

**Button.scss**
```
@import '_button.scss'

.Button {
  color: $btn-primary-color;
  background: $btn-primary-bg-color;
  ...
}

.Button--secondary {
  ...
}
```

This worked fairly well for a time but I found that there we lots of instances where I needed to override the default styles to work with a specific composition like in a modal footer or as part of a form. So I would stack a new class onto the component in more of a BEM approach using the `getClassNames` utility I shared in a previous post

**Button.js**
```
function getClasses (parentClasses) {
  const componentClasses = [
    'Button'
  ]
  if (parentClasses) {
    componentClasses.push(parentClasses)
  }
  return componentClasses.join(' ')
}


<Button className={ getClasses('Sign-Up__footer-button') } />
```

This worked well for a time but I found that I was writing a lot more CSS to cover the specific instances where I needed a set of minor tweaks for a composition than I should need but I didn't want to create a big list of modifiers as that wouldn't be maintainable. This approach also felt wrong as the majority of these styles weren't re-usable which defeats the enhancements that originally brought me into preprocessors.

Another challenge was that now that I work in a dedicated javascript development role I collaborate with designers that manage the bulk of our CSS across projects so maintaining my own set of partials isn't really feasible as the baselines need to be strictly versioned outside of my project.

To solve these challenges my team and I decided to adopt CSS modules. By using composition we are now able to maintain a large set of finely tuned variables and mix-ins in a separate project managed as an npm package without designers needing to be up to their eyeballs in React and I can focus on component design without risk of straying from our design standards. To demonstrate here is how I would build the button component.

**Button.scss**
```
.Button {
  composes: Button from '~/teamsnap-ui/src/_button.scss';
}
```

**Button.js**
```
import styles from './Button.scss'

<Button className={ styles.Button } />

```

There are still plenty of challenges to solve for such as how to theme a component for re-use across projects but I'm finding this outsourcing of the primary styles is working really well. I also get the benefit of collision projection BEM provides automatically due to the way these CSS module composed styles are converted into classes via javascript `.Form-Button__as34sdf`.

I've found there are still a few use cases for more global CSS such as grid classes you want to just apply to a component but I'm confident that with time we can find elegant solutions to maintain those as components as well. I hope this helps you find new ways to leverage component architecture and if you have any feedback or suggestions be sure to hit me up on Twitter. Happy Coding.


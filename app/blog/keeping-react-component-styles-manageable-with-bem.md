---
title: keeping react component styles manageable with bem
date: 2016-11-12 21:10:03
tags:
  - blog
  - sass
  - react
  - javascript
---

After a few months of working on a new project and getting comfortable transitioning to React from Angular
I've been turned on to a new strategy for managing component based css. Our team found that using BEM really
helps keep component styles small and manageable while also easy to debug. Below is a high level example of this approach that would require a bundler like webpack and babel to handle the es6 transpilation but could be re-written with es5 syntax as well if one desired.

I had reviewed BEM a few years back while researching large scale css strategies but hadn't fully adopted it as it initially felt a bit too verbose for my liking and at that point I was still writing the majority of my styles in more of a monolithic cascade approach. Now with a simple bit of javascript utility I've found I can maintain tightly scoped modular styles for each component but also leverage a bit of classic cascade with some minimal partials.

First here is a simple component to demonstrate.

```javascript
import React, { Component, PropTypes } from 'react'

export default class ArticleCard extends Component {

  render () {

    const { article } = this.props

    return {
      <article>
        <figure>
          <img src="{ article.img }" />
          <figcaption>
            <h3>{ article.title }</h3>
            <span>{ article.published_date }</span>
          </figcaption>
        </figure>
        <div>
          { article.content }
        </div>
      </article>
    }
  }
}

ArticleCard.propTypes = {
  article: PropTypes.object.isRequired
}
```

Now in this current state the component is modular and not tainted with styles from its specific implementation.
For instance if you want to use this article card on a magazine layout styled homepage and in a sidebar feature of an article detail how can you keep from repeating yourself while still being able to add some context
from each instance where the component is used? Our team uses a simple function for css class management.

```javascript
function getClasses (parentClasses) {
  const componentClasses = [
    'article'
  ]
  if (parentClasses) {
    componentClasses.push(parentClasses)
  }
  return componentClasses.join(' ')
}
```

With this small utility function we can dynamically pass in context so lets add it to the component and implement some BEM classes to provide a surface area for some basic styles.

```javascript
import React, { Component, PropTypes } from 'react'
import './_ArticleCard.scss'

function getClasses (parentClasses) {
  const componentClasses = [
    'article'
  ]
  if (parentClasses) {
    componentClasses.push(parentClasses)
  }
  return componentClasses.join(' ')
}

export default class ArticleCard extends Component {

  render () {

    const { article, articleClasses } = this.props

    return {
      <article className={ getClasses(props.articleClasses) }>
        <figure className='article__card'>
          <img src="{ article.img }" className='article__card-image'/>
          <figcaption className='article__card-caption'>
            <h3 className='article__card-title'>{ article.title }</h3>
            <span className='article__card-date'>{ article.published_date }</span>
          </figcaption>
        </figure>
        <div className='article__card-content'>
          { article.content }
        </div>
      </article>
    }
  }
}

ArticleCard.propTypes = {
  article: PropTypes.object.isRequired,
  articleClasses: PropTypes.array
}

```

Now with some BEM class names nesting in sass makes the verbosity far less cumbersome but also enforces the scoping we need for a truly reusable component.

```css

/* _ArticleCard.scss */

.article {
  &__card {
    display: flex;
    flex-direction: column;
    background: white;
    color: slategray;
  }
  &__card-image {

  }
  &__card-caption {

  }
  &__card-title {
    font-size: 3rem;
  }
  &__card-date {
    font-size: 1.6rem;
  }
  &__card-content {

  }
}

```

Now each parent component that is using this Card component can also pass in a css class to provide some top level styles based on its context.

```javascript

import ArticleCard from 'your/project/path/ArticleCard'

function ArticlePage(props) {
  return (
    <Page>
      <ArticleCard
        article={ articleData }
        articleClasses={ ['article-page'] } />
    </Page>
  )
}

```

This pattern really helped me to start thinking more creatively about re-usable styles but more through the lens of components rather than a styles that cascade through global partials and mixins. Hopefully you too find it useful.

Cheers.

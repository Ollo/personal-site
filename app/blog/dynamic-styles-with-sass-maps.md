---
title: dynamic styles with sass maps
tags:
  - blog
  - sass
  - css
date: 2015-12-16 10:10:37
---

So recently I was working on an angular directive that produced a content card and each of them needed a unique accent color. Each of these cards are produced through an `ng-repeat` as a result of an api response that was fairly limited in data / context. Essentially all I had to identify each card was a single letter that was used on each card.

Usually in this situation I would just manually write six disctinct classes since there was such a small number of variants but lately I've been seeing some fun applications of sass maps and functions so I wanted to give them a shot. Below is what I ended up with.

```less
$card_colors: (
  'r': $blue,
  'i': $green,
  'a': $mustard,
  's': $burnt_orange,
  'e': $spray_blue,
  'c': $burnt_sienna_red
);

@function get-color($color_code: r) {
  @return map-get($card_colors, $color_code);
}

@each $background, $color_code in $card_colors {
  .code_background-#{$background} {
    background-color: get-color($background);
  }
}
```

Overall I'm pretty pleased with the power of this approach but I do worry a little about how readable and maintainable this approach would be for a developer that comes behind me.

I also at some point need to do some performance evaluations as traditionally sass maps haven't been recommended in production due to performance. Thoughts?

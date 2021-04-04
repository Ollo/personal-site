---
title: selective data loading in angular
date: 2016-04-27 12:23:13
tags:
  - blog
  - javascript
  - angular
---

Today I was working on a new feature for a large angular application.
The feature called for an adaptive carousel that loaded different data based on the viewport. I typically dislike this kind of design since if not handled correctly can create bad experiences for mobile users.

Typically developers will just hide and show different versions of the component based on a css breakpoint. But this approach means that all the data is loaded potentially multiple times and just hidden if its not needed in the view. This can cause very latent interfaces on mobile so I decided to tackle this through javascript.

```javascript
determineShowAmount($window);

// Only show the number of cards appropriate for the viewport
angular.element($window).on('resize', function() {
  determineShowAmount($window);
  $scope.$digest();
});


function determineShowAmount($window) {
  if($window.innerWidth < 768) {
    $scope.cardLimit = 2;
  }
  else if ($window.innerWidth >= 768 && $window.innerWidth < 1024) {
    return $scope.cardLimit = 3;
  }
  else {
    return $scope.cardLimit = 4;
  }
}
```

I still have some performance testing to do as binding to the `$window` resize event feels potentially expensive but so far the performance has been great.

If anyone has any feedback or better practices for this type of scenario I would love to hear it. Hit me up on twitter and let me know.

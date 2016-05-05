# Angular Animation

* CSS Transitions
* CSS Keyframes
* Web Animation API

Angular 2 combines all above.

Angular 1 relies lots of CSS and barely JavaScript. In other word, angular 1 heavily relies on browser.

Angular 2 is different from Angular1.

* No CSS Transition/Keyframes
* Web Animations
* Component States
* Timeline-based

Demo: https://github.com/matsko/ng-conf-demos

## The basic

```html
<div @myAnimation="expression">
  <!-- ... -->
</div>
```

```
@Component({
  ...  
})
```

## Component UI States

Use "@" Sign to declare

## Performance

* No relies on DOM
* Web Animation integration
* Code generation
* Web workers

## Web animation polyfill

* https://github.com/angular/element-animate-polyfill

## Staggering

* full support
* linear, reverse
* DOM specific

## Component access

Component can access Animations for listening on state

## Custom renderers

Animation in the platform level (in web and mobile devices like native script)

## When is release date

In few weeks

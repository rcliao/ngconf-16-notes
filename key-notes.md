# Key notes from Angular team

https://docs.google.com/presentation/d/1GII-DABSG5D7Yhik4Be5RvL6IXPt-Kg8lXFLnxkhKsU/edit#slide=id.g128d8fde34_1_2

Angular 2 from framework to platform.

* Dependency injection
* Decorators (@)
* Zones
* Compile (offline)
* Change (change detector)
* Render (renders to browser, native components or server side template)
* Material
* Mobile (first mobile toolkit)
* Universal (angular on the server)
* CLI
* Language services (typescript and support in IDE)
* Augury (chrome plugin debugger)
* ngUpgrade

Things before Angular 2 final release:

* Performance
* Productivity
* Versatility

## Performance

* Render => ~~2.5x faster~~
* Re-render => ~~4.2x faster~~
* Always => 5x faster

Html template => optimized JavaScript (template compiler) => deploy

Angular 2 library is now 45k compared to angular 1 50k.

**Automatic lazy loading**

* via ngRouter to do lazy loading

* Angular universal to do server side template loading
  * available
    1. node.js
    2. asp.net

**Web workers**

ui thread and other thread got separated.

## Productivity

Chrome plugin debugger tool ... https://augury.angular.io/

**Simplicity**

`[]` and `()`

Style guide with angular2:

* https://angular.io/styleguide
* https://github.com/mgechev/codelyzer

**Cli**

## Versatility

Unified development

* Not just web platform

Mobile toolkit: https://mobile.angular.io/

**Progressive web apps**

Installed mobile

* Ionic
* Native script
* React native

Installed desktop

* Eletron
  * move threads from ui thread to do stuff
* Windows universal

UI components

* Material 2

Built together with partners:

Angular2 support from native script:

https://www.nativescript.org/ng-conf

Angular 2 challenges:

Traditional bootstrap may not work.

Angular 2 why?

* Shadow dom emulation
* Lone of code size reduce
* Change detection (faster data binding)

Enterprise problems

* Performance
* SEO
* Accessibility
* Global teams

Angular 1 problems

* SEO doesn't rendered correctly

Angular 2:

* Instantly rendered
* Final DOM represented
* Accessibility (JavaScript less critical)

Angular universal makes various things great specifically for accessibility.

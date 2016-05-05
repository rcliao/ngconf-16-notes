# Multi-slot transclusion

New in Angular 1.5 and Angular 2.

Standard Transclusion definition:

Transplanting DOM nodes into another component.

In angular 1:

* `ng-trnsclude`
* `transclude: true`

**New**

Multi-slot Transclusion

Angular 1.5

* `ng-transclude="heading"`
* ```
transclude: {
  heading: 'outside-heading'
}
```

Angular 2

* `<ng-content select="[outside-heading]">`

Demo: 
https://plnkr.co/edit/1xYetO?p=preview

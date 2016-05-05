# Angular Key Notes 2

## The road ahead

* Offline compiler

Dynamic mode => 116kb after minified
Static mode => 49.4kb

```
import {AppNgFactory} from './'
```

`ngc` => angular compiler command

Compiling in Angular 1

```
browser => browser => browser => js
xhr     => parser  => dom     => angular1
```

Polymorphic = very bad at optimization

Compiling in Angular 2

```
file     => node   => node => JS     => JS
template => parser => AST  => source => Angular2
```

Monomorphic = huge speed boost


Offline compile => inline modules => tree-shake => minify

## Pseudocode of offline compile

```js
class HelloWorldFactory extends ComponentFactory<DemoApp> {
  e0, e1, e2;
  lastName;
  constructor(private renderer: Renderer, private context: DemoApp) {
    e0 = renderer.createElement(null, 'div');
    e1 = renderer.createText(e0, 'Hello ');
    e2 = renderer.createText(e0, '');
  }

  detectChangeInternal() {
    var name = this.context.name;
    if (name !== this.lastName) {
      renderer.setText(e0, this.lastName = name);
    }
  }
}
```

## Inline modules

from import files to single file concatanates everything

## Tree-shaking

Exclude not-used files

## Minified

Simply minify

## Advanced Material 2

Material export some common libraries that doesn't depends on material.

Some advanced material elements:

* md-map
* md-video-player
* md-text-editor
* Automatic form generation
* md-chart
* md-data-table

## Effortless Upgrades

Ever green angular version.

Use typescript to propose upgrade refactoring in compile time.

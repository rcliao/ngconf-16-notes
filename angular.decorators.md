# Demystifying Decorators

A new way of using existing JavaScript features

```
@ClassDecorator()
class Foo {
  @PropDecorator prop;
  constructor(@ArgumentDecorator args)
}
```

Decorators run when code is created.

```js
function Describe(description) {
  return (target, prop) => {
    target.desc = target.desc || {};
    target.desc[prop] = description
  }
}
```

```js
class CliCommands {
  @Describe('Log into a remote server')
  static login() {
    // ...
  }
}
```

Decorators can get you into trouble

Things to do:

* Avoid mutation
* Standardization is in progress
* Keep it simple

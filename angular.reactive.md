# Reactive Programming

rx-js

https://github.com/mattpodwysocki/ng-conf-2016

Reactive Extensions (Rx)

**BIG** async problems

Everything about your app today is asynchronous.

Asynchronous problems

* Memory leaks
* Race conditions
* Callback hell
* Complex state machines
* Disjointed error handling

Promise only solves part of problems

Problems of promises

* No way to cancel a Promise
* How do I clean up after using the resource like finally block in Java

Reactive way of solving callback hell

```js
const subscription = authorizations.subscribe(
  license => player.play(license),
  error => showDialog('Error')
);
```

What is Reactive Programming?

Server side rendering for Angular 2.

Solving:

1. Gap events    ==> preboot
2. Async         ==> zone.js
3. Dependencies  ==> DI

## Gap Events

### Purpose

Keep the event between client bootstraps.

Progress web Application

* Application shell
* Content

Protractor/karma

Use async pattern to test

**Dependencies**

e.g. window.localStorage

Use dependency injection to inject store

Create store interface and implement basic on platform (browser or server)

Browser still uses localStorage while server may use some in memory storage (like redis)

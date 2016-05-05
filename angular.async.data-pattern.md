# Async Data Pattern

Observables everywhere.

Observables are just arrays laid out in time.

> Array is just laid out in memory.

What if my database was an observables?

Firebase

* User Auth
* Realtime database
* Static hosting

AngularFire 1.x = synchronized collections with `$digest()`

Observables model async data streams.

AngularFire2 synchronizes collections as observables.

```
import {FIREBASE_PROVIDERS, defaultFirebase} from 'angularfire2';

bootstrap(..., [
  
]);
```

```
import {AngularFire} from 'angularfire2';

@Component({
  // ...
  template: `
    <ul>
      <li *ngFor="let person of people | async">
        {{person | json}}
      </li>
    </ul>
  `
})
class MyComponennt {
  people: Observable<any>
  // ...
}
```

AngularFire2 is in beta.

Get started

```
npm i angularfire2
```

https://github.com/angular/angularfire2

# @ngrx

Provide a suite of lightweight, interoperable, reactive services and components for Angular 2.

Some current components:

* @ngrx/store
* @ngrx/devtools
* @ngrx/router
* @ngrx/db

Some components coming soon:

* @ngrx/resource
* @ngrx/socket
* @ngrx/api
* @ngrx/???

@ngrx/store

Reactive redux for Angular 2.

Redux => A predictable state container for JavaScript apps.

* Reducers

```js
import {provideStore} from '@ngrx/store';

bootstrap(app, [
  provideStore({todos, visibilityFilter})
]);
```

```js
@Component({
  selector: 'my-app'
  template: `
    <child-app [todos]="todos | async"></child-app>
  `
})
export class App {
  todos: Observable<Todo[]>;
  
  constructor(store: Store<AppState>) {
    store.subscribe(state => {
      console.log(state);
    });
    this.todos = store.select(state => state.todos);
    store.dispatch({
      type: 'ANYTHING',
      payload: {
        foo: 'bar'
      }
    });
  }
}
```

```js
@Componennt({
  selector: 'child-app'
  changeDetection: ChangeDectionStrategy.OnPush
})
export class ChildAppComponent {
  @Output action = new EventEmitter();
  @Input todos: [];
  
  change() {
    this.action.emit({
      action: '',
      payload: {
        foo: 'baz'
      }
    });
  }
}
```

Include <ngrx-devtools> directive to debug

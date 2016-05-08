# The secret weapon of Angular 2

Type support

Core types:

* string
* number
* boolean
* Array
* any
* interface

Union type:

```typescript
accessories: string | string[]; // accept both string or array of string type
```

Tooling support:

* Code help/intellisense
* Refactoring
* Peek/go to
* Find references

**Interfaces**

```
interface ICustomer {
  firstName: string;
  lastName: string;
  age?: number; // optional
}
```

```
this.service.get()
  .subscribe((data: ICustomer[])=> this.customers = data);
```

Generics

**Code templates**

```
export class List<T> {
  add(item: T) { ... }
}
```

```
var customers = new List<ICustomer>();
customers.add({firstName: 'eric', lastName: ''});
customers.add(42); // not valid!
```

http://tinyurl.com/TSSecretWeapon

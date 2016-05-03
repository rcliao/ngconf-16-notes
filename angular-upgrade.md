# Angular Upgrade Workshop

See angular-upgrade-app repository:

https://github.com/thoughtram/angular-upgrade-app

Slides:

http://thoughtram.io/angular-upgrade-slides/#/

Steps:

1. Include ngUpgrade from angular and export instance
2. Bootstrap angular using upUpgradeAdapter
3. Downgrading Angular 2 components  
```javascript
angular
.module('contast-list-app-2')
.directive(
  'ContastListItem',
  upgradeAdapter
    .downgradeNg2Component(ContactsListItemComponent) # downgraded angular 2 component
);
```
4. Upgrade Angular 1 components  
```js
// angular 2 component instance
const ZippyComponent =
  upgradeAdapter.upgradeNg1Component('zippyComponent');
// notes: make sure to upgrade template syntax of the consumer of this "zippy-component"

@Component({
  // ...
  directives: [ZippyComponent]
})
```
5. Upgrade Angular 1 providers  
```js
// upgrade provider/services and attach it in angular 2 DI
upgradeAdapter.upgradeNg1Provider('contactsService');
upgradeAdapter.upgradeNg1Provider('$routeParams');

@Component()
export class ContactDetailComponent {

  contact: Contact;

  constructor(
    @Inject('contactsService') contactsService,
    @Inject('$routeParams') $routeParams) {
    this.contact =
      contactsService.getContact($routeParams.id);
  }
}
```
6. Downgrade Angular 2 providers  
```
angular.module('contacts-service', [])

.service('contactsService',
  upgradeAdapter.downgradeNg2Provider(ContactsService)
);
```
7. Upgrade angular 1 provider  
```
upgradeAdapter.addProvider(ContactsService);

@Component()
export class Component {
  constructor(contactsService: ContactsService) {

  }
}
```

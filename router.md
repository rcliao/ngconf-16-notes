# Angular2: Router

Application is divided into components. And each component can be loaded into `outlet`.

Lazy loading!

Only loads the necessary components based on the route.

**Tree<UrlSegment>**

my.app/user/1234/details -> user -> 1234 -> details

Convert component in route loader to string and rely on the specific structure so that System.js can do the lazy-loading for Angular.

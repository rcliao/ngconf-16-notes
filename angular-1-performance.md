# Angular 1 Application Performance

## Tips & tricks

1. Always use the latest version of Angular
2. Disable debug data: https://docs.angularjs.org/guide/production
3. Always use `track by`
4. Bundle JavaScript
5. Don't duplicate AJAX
6. Limit simultaneous AJAX  

  > Can only make 6 requests at the same time from a browser
  > aggregator service to combine requests

7. Do not block event loop 

Route stabilization

Introduce analytics to detect performance of certain route.

## Performance Improvement Process

1. A real-world problem exists
2. Establish a baseline
3. Identify and improve the biggest bottleneck
4. Measure and assess


Use $timeout to group digest cycle together other $timeout(s)

Remember to clean up widget via `$scope.on('$destroy', fn)`

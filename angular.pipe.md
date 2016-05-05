# Pipe Hype

Pipes are reusable way to transform any type of data on the fly.

Replace pipe using regex to replace.

## How to write custom Pipes

```js
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'filter'
})
export class FilterPipe {
  transform(files: string[], filterBy) {
    if (files) {
      // ...
      return filteredFiles;
    }
  }
}
```

## Change detection

Change detection and pipe can be tricky to deal with.

Use `pure` to indicate pure pipe or impure pipe. (immutable or mutable pipe)

In component, you have to indicate the reference change like below:

```js
this.files = this.files.concat(newFile);
```

or to define pipe to "impure"

```
@Pipe({
  name: 'filter',
  pure: false
})
// ... more pipe implementation
```

or change "changeDetection"

```html
<element
  changeDetection: ChangeDetectionStrategy.Push
>
```

`async` pipe is impure pipe.

```js
@Component({
  selector: 'custom-activities',
  template: `<p>{{activities | async}}`
})
class ActivitiesComponent{
  activities: Observable<string>;
}
```

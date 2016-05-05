# Angular 2 Form and Validation

Form Validation

Demo:

https://github.com/deborahk/ngconf2016

## Template-driven forms

Validation and everything is in template itself

Controls:

```html
<div [ngClass]="{'error': title.errors}">
  <input
    required
    minlength="3"
    maxlength="50"
    [(ngModel)]="movie.title"
    ngControl="title"
    #title="ngForm" />
</div>
```

Validations:

```html
<span
  *ngIf="title.touched && title.errors">
  <span *ngIf="title.errors.required">Enter title</span>
</span>
```

Template driven forms is very similar to Angular 1.

## Partial Model-driven forms

Keep input, data binding and error messages in template.

Moves over controls, form and validation in the class.

```js
@Component({
  template: `
    <form [ngFormmodel]="editForm">
      <label for="">Title</label>
      <input type="text" [(ngModel)]="movie.title" ngControl="title" />
      <span *ngIf="title.touched && title.errors">
        <span *ngIf="title.errors.required">Enter title</span>
      </span>
    </form>
  `
})
export class MovieEditComponent {
  editForm: ControlGroup;
  title: Control;
  
  constructor(private _fb: FormBuilder) {
    this.title = new Control(
      '',
      Validators.compose([
        Validators.required, 
        Validators.minLength(3),
        Validators.maxLength(50)
      ])
    );
    this.editForm = this._fb.group({
      'title': this.title
    });
  }
}
```

## Model-driven forms

Everything in the class: controls, default values, validation, error messages.

Input and control binding in template;

```js
@Component({
  template: `
  <form [ngFormModel]="editForm">
    <input type="text" ngControl="title">
    <span *ngIf="formError.title">
      {{formError.title}}
    </span>
  </form>
  `
})
export class FormAppComponent {
  this.formError = {
    'title': ''
  };
  this._messages = {
    'title': {
      'maxLength': 'Max error'
    }
  };
  
  constructor(private _fb: FormBuilder) {
    this.title = new Control(
      'this.movie.title',
      Validators.compose([
        Validators.required
      ])
    );
  }
  
  onMovieRetrieved(movie: IMovie) {
    this.editForm.valueChanges
      .subscribe(data => this.onValueChanged(data));
  }
}
```

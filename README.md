# angular-cheetshet
This is living document. Information will be added and updated frequenty.

[Official cheatsheet](https://angular.io/guide/cheatsheet)

[Official Style Guide](https://angular.io/guide/styleguide)

### Info about angular-cli
1. librabry - used to publish angular librabry.
2. application - diffrent application


### applying class
`[class.name-of-class-to-apply]="conditionToApplyClass"`
`<input #nameControl="ngModel">` This `"nameControl"` template variable will give  access to the "NgModel" instance for this from input. 

### Keep in mind
1. `BrowserAnimationsModule` and `HttpModule` shound be import only once either in `root` module or `core module`
2. `CommonModule` should be imported instead of `BrowserModule` if both module is imported.


### Requriements of components
1. Modular
2. Atomic
3. Self-contained.

### knowing if there is listener
`this.emitter.observers.length > 0` (here `this.emmitter` the `@Outpu()` of the component)


### Types of Directives
1. `Component`
2. `Attribute Directive` changes the apperance or behavior of a DOM element.
3. `Structural Directive`


### Query Decoractors
1. ViewChild `@ViewChild(selector) tmplB: TemplateRef<any> `
2. ViewChildern `@ViewChildern(selector) tmplLstA: QueryList<TemplateRef<any>>`
3. ContentChild `@ContentChild(selector) tmplA: TemplateRef<any>`
4. ContentChildern `@ContentChildren(selector) tmplLstB: QueryList<TemplateRef<any>>`

### Shadow Piercing
`::ng-deep.viewType {}` can be used to break the shadow dom or view encapulation in angular. I will only effect the Child Components only.


### Pipes
try to use only pure pipe. Be careful when using `async` pipe in angular

### ngFor
1. use `trackBy` in `ngFor` for any list.
` *ngFor="let item of list; trackBy: trackByFunc"`
`const trackByFunc = (idx: number, itm: any) => itm.id`

### Caching

#### Caching Adds Complexity
1. `Cache management`
2. `Security`
3. `Storage`
4. `Extrage Logic`

#### Memoizing is best option
1. Can be easily done by TypeScript decorators.
2. `@Memomize(5)
    public callApi() {}
    `


### reducing import
1. imports required components in routing module and set the static proporty in routing module
2. use routing module static property for importing and exproting the component.

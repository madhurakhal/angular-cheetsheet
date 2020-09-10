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

### Preventing Reimport of Core
1. Core should only be imported into the root/app module
`export function throwIfAlreadyLoaded(parentModule: any, moduleName: string) {
    if (parentModule) {
        throw new Error(`${moduleName} has already been loaded. Import core modules in the AppModule only`);
    }
}
export class CoreModule {
    constructor(@Optional() @SkipSelf() parentModule: CoreModue) {
        throwIfAlreadyLoaded(parentModule, 'CoreModule')
    }
}
`
2. Alternative: Base class as a guard.
`
export class EnsureModuleLoadedOnceGuard {
    constructor(targetModuel: any) {
        if(targetModule) {
            throw new Error(`${targetModule.constructor.name} has already been loaded. Import core modules in the AppModule only`);
        }
    }
}

export class CoreModule extends EnsureModuleLoadedOnceGuard {
    constructor(@Optional() @SkipSelf() parentModule: CoreModue) {
        super(parentModule)
    }
}
`

### Container Components
1. Interact with the store
2. Pass obserable streams via async pipe
3. Receive events from child presenter components
4. Decide what toe do with events/data

### Presentational Container
1. Receive plain data from parent
2. Display data/make it pretty
3. User/system events are raised to parent via emitters
    1. Decisions are deferred
    2. Component is resuable and flexible
4. No knowledge of store, services, selectors, actions etc.


### Importants
1. In `tsconfig.json`
`
paths: {
  '@core/*': ['app/modules/core/*']
}
`
2. Don't do `<input [value]="'hello world'"/>`

### Content porjection
2. <ng-content></ng-content>
1. ngProjectAs

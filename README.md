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
2. `Attribute Directive`
3. `Structural Directive`

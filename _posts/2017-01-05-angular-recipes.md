---
layout: post
title: Angular 2 recipes / Tips & tricks
published: true
---
Tips & tricks for tricky but useful things in angular 2. The type of problems that are too small  to deserve a full blog post, and that you do not know how to name to search for.

### Elvis operator and bracket notation

Bracket notation is javascript is an alternative to dot notation to display the content of an object. The main advantage is has is that you can use variable inside the bracket to display a property whose name depends of a variable.

Elvis operator is a syntax for angular 2 that allow to tell angular renderer to ignore template binding of sub-properties for object that does not exist yet. Indeed it is generally that the object is not yet loaded from the backend.

From this [link](http://stackoverflow.com/questions/35768768/angular2-using-elvis-operator-on-object-key-with-forward-slash)


The Elvis operator is only available for the . not for other dereference operators like []. As a workaround use

```
data?.record ? data.record['name/first'] : null
```

### Object property binding & async pipe with bracket syntax

Yes but how to use a bracket syntax with async syntax.

[http://stackoverflow.com/questions/36803389/angular2-async-pipe-not-does-not-fill-object-data-into-template](http://stackoverflow.com/questions/36803389/angular2-async-pipe-not-does-not-fill-object-data-into-template)

I have an observable that I want to pass to a component.
Once passed I want a sub property that is static in that case : the first item of an array.
Or may be dynamic, a component property.    

The problem is that : `(imagesFB | async)[0]` would fail because the item does not exist at first and the async is for imagesFB not for the resulting array that (imagesFB | async) return.

So with a ternary syntax :

```
 (bolean) ? /* code if true */ : /* code if false */ ;`
```

We do the trick.

````
ui-gallery-image([image]="(imagesFB | async) ? (imagesFB | async)[0] : null")
````

### Instanciation of class or static method

There is 3 keywords that can be used in a class.
To defined a property or method

* **public** to get the method available from other classes
* **private** to get it only usable inside the class
* **static** allow to use a class without instantiating it
Instantiate a class, is creating a local copy of it. For example if we are in a component, that mean that we are using an instance of a class.
An instance is creating by passing it to the component constructor like this.

````js
import { UploadService }         from '../../../services/api/upload.service'

export class UiUploadUploadcareComponent {
  constructor(
    private uploadService: UploadService,
  ){
  }

  upload() {
    // we use the instance of the class with this
    this.uploadService.upload()
  }
````

But by using static we do not need, and we cannot actually create a local instance

````js
import { StaticService }         from '../../../services/static.service'

export class UiUploadUploadcareComponent {
  constructor(
    // we do not need to instanciate the class
  ){
  }

  upload() {
    // we use the static method useStaticClass
    // of StaticService  class without the this keyword
    StaticService.useStaticClass()
  }
````


### Simplify module definition with the spread operator

* [Doc of spread operator](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Operators/Spread_operator)

````js
@NgModule({
  imports: [
    ...MODULES
  ],
  declarations: [
    ...PIPES,
    ...COMPONENTS
  ],
  exports: [
    ...MODULES,
    ...PIPES,
    ...COMPONENTS
  ]
})
````

### Export of modules to be compatible with lazy loading, AOT and universal angular

````js

const PIPES = [
  // put pipes here
];

const COMPONENTS = [
  // put shared components here
];

const PROVIDERS = [
  ModelService,
  ApiService
]

@NgModule({
  imports: [
    ...MODULES
  ],
  declarations: [
    ...PIPES,
    ...COMPONENTS
  ],
  exports: [
    ...MODULES,
    ...PIPES,
    ...COMPONENTS
  ]
})
export class SharedModule {
  static forRoot(): ModuleWithProviders {
    return {
      ngModule: SharedModule,
      providers: [
        ...PROVIDERS
      ]
    };
  }
}
````

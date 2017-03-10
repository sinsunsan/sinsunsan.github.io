---
published: true
layout: post
title: The tutorials I've read to learn Angular 2
---
Here is a curated list of some good tutorials we used to learn the version 2 of angular.

## General

* Official angular 2 tutorial      
[https://angular.io/docs/ts/latest/tutorial/](https://angular.io/docs/ts/latest/tutorial/)
*  Light weight documentation with both ES6 and Angular 2 made by Ionic team     
[Learn angular 2](http://learnangular2.com)
* 132+ Video tutorial on specific pratical cases
[https://egghead.io/technologies/angular2](https://egghead.io/technologies/angular2)

## Ressources and tutorials list

* Awesome Angular       [https://github.com/AngularClass/awesome-angular](https://github.com/AngularClass/awesome-angular2#ahead-of-time-compilation)

## Forms

* Guide to forms in angular 2    
[http://blog.ng-book.com/the-ultimate-guide-to-forms-in-angular-2/](http://blog.ng-book.com/the-ultimate-guide-to-forms-in-angular-2/)

* Angular forms beyond the basics   
[http://restlet.com/blog/2016/02/17/implementing-angular2-forms-beyond-basics-part-2/](http://restlet.com/blog/2016/02/17/implementing-angular2-forms-beyond-basics-part-2/)
Some more advanced form topics like automatically adding class for bootstrap or async validation...


### Reactive forms or model driven fields

* Using Angular2 model driven forms    
[https://scotch.io/tutorials/using-angular-2s-model-driven-forms-with-formgroup-and-formcontrol](https://scotch.io/tutorials/using-angular-2s-model-driven-forms-with-formgroup-and-formcontrol)
* Introduction to Angular 2 Forms - Template Driven vs Model Driven or Reactive Forms   
[http://blog.angular-university.io/introduction-to-angular-2-forms-template-driven-vs-model-driven](http://blog.angular-university.io/introduction-to-angular-2-forms-template-driven-vs-model-driven)
* Reactive forms    
[https://toddmotto.com/angular-2-forms-reactive](https://toddmotto.com/angular-2-forms-reactive)

### Forms fields

* Example of different types of fields    
[https://scotch.io/tutorials/how-to-deal-with-different-form-controls-in-angular-2](https://scotch.io/tutorials/how-to-deal-with-different-form-controls-in-angular-2)

## Events / Change detection

* Event and @output decorator     
[https://toddmotto.com/component-events-event-emitter-output-angular-2](https://toddmotto.com/component-events-event-emitter-output-angular-2)
* Change detection in Angular 2
[http://blog.thoughtram.io/angular/2016/02/22/angular-2-change-detection-explained.html](http://blog.thoughtram.io/angular/2016/02/22/angular-2-change-detection-explained.html)
* How to replicate $scope.$emit with global events ? More technics that official ways
[http://stackoverflow.com/questions/34700438/global-events-in-angular-2](http://stackoverflow.com/questions/34700438/global-events-in-angular-2)

## Components

* Children view    
[http://blog.mgechev.com/2016/01/23/angular2-viewchildren-contentchildren-difference-viewproviders]()

* Dump / Smart component architecture :
A way to organize component to differentiate presentational component highly reusable and intelligent component that actually handle the logic and specific stuff
[https://teropa.info/blog/2016/02/22/dumb-components-and-visual-feedback-in-angular-apps.html]()

## Components @input

* How to define a inner child component property on-change to allow pass observable as input.   [http://almerosteyn.com/2016/03/immutable-component-input-from-observable](http://almerosteyn.com/2016/03/immutable-component-input-from-observable)

## Component ngInit vs constructor

* Difference between constructor and ngOnInit     
 [http://stackoverflow.com/questions/35763730/difference-between-constructor-and-ngoninit](http://stackoverflow.com/questions/35763730/difference-between-constructor-and-ngoninit)

## Dynamic component / Component inheritance / Communication between components...

* dynamically creating component in angular 2 [http://blog.rangle.io/dynamically-creating-components-with-angular-2/](http://blog.rangle.io/dynamically-creating-components-with-angular-2/)

* Component inheritance introduced in 2.3     
[https://scotch.io/tutorials/component-inheritance-in-angular-2](https://scotch.io/tutorials/component-inheritance-in-angular-2)

* Different ways for communication between components :

    * With input with a setter
    * With input via ngChanges detection
    * With @viewchild that allow to manipulate child methods
    * With a service and observable subject

[https://angular.io/docs/ts/latest/cookbook/component-communication.html](https://angular.io/docs/ts/latest/cookbook/component-communication.html)

### DOM

* How to use the angular 2 renderer service to manipulate the DOM in a way all platforms (server, browser, mobile.. can accept)

[https://netbasal.com/angular-2-explore-the-renderer-service-e43ef673b26c#.mah8emsrl](https://netbasal.com/angular-2-explore-the-renderer-service-e43ef673b26c#.mah8emsrl)

## Directives

* Structural (ngIf...or custom) or attributes (ngClass... or custom) directives      
[https://angular-2-training-book.rangle.io/handout/advanced-angular/directives/](https://angular-2-training-book.rangle.io/handout/advanced-angular/directives/)

## Observables / RxJS

Angular 2 adopted this new concept of observable which basically is a more advanced form of promise.
RxJs is the  implementation of Observable used by angular which is being developed by Microsoft.

* This post list 3 common problems with can have with observable.

* **Pitfall 1** : not subscribing to an observable is similar to having a function but not exucuting it

> An observable itself is just a definition of a way to handle a stream of values. We can think of it as something close to a function. Creating an observable is somewhat similar to declaring a function, the function itself is just a declaration. Calling the function is something entirely different, as defining a function does not execute its code.

> We need to call the function in order for something to happen, and that is also the case with an Observable: we need to subscribe to it in order for it to work!

 [http://blog.angular-university.io/angular-2-rxjs-common-pitfalls/](http://blog.angular-university.io/angular-2-rxjs-common-pitfalls/)

* Building a data store with observable
[http://blog.angular-university.io/how-to-build-angular2-apps-using-rxjs-observable-data-services-pitfalls-to-avoid/](http://blog.angular-university.io/how-to-build-angular2-apps-using-rxjs-observable-data-services-pitfalls-to-avoid/)

## ngFor, ngIf, ...


* Revision of what ngFor can do
   * how to get the index
   * how to track by another value that default (by object Identity)
   * using odd, even, last, first for dynamic class naming

 > ngFor by default tracks list items using object identity. This means that if you build a list of new objects from scratch with the exact same values as the previous list and pass this newly built list to ngFor, Angular will not be able to tell that a given list item is already present or not.

[http://blog.angular-university.io/angular-2-ngfor/](http://blog.angular-university.io/angular-2-ngfor/)

## Modules

Organize your code in a modular way. Import a module instead of importing a dozen of files (javascript modules). Despite of the use of ES6 modules in angular, angular  modules @ngModules are still useful to bundle a feature or a shared utility together.

* [https://scotch.io/bar-talk/getting-to-know-angular-2s-module-ngmodule](https://scotch.io/bar-talk/getting-to-know-angular-2s-module-ngmodule)

* The ng module FAQ is a good place to better understand the ngModules API fine tuning     [https://angular.io/docs/ts/latest/cookbook/ngmodule-faq.html#!#q-declarable](https://angular.io/docs/ts/latest/cookbook/ngmodule-faq.html#!#q-declarable)

## Decorator / Annotation syntax [Typescript]

* Difference between decorator and annotation [http://blog.thoughtram.io/angular/2015/05/03/the-difference-between-annotations-and-decorators.html](http://blog.thoughtram.io/angular/2015/05/03/the-difference-between-annotations-and-decorators.html)

## Dependency injection

* How to inject window in a service to keep it compatible with angular  dependency injection philosophy        [https://juristr.com/blog/2016/09/ng2-get-window-ref](https://juristr.com/blog/2016/09/ng2-get-window-ref/)


## Pipes

* Simple tutorial to do a custom  pipe available in its components then make it available application wide    [https://scotch.io/tutorials/create-a-globally-available-custom-pipe-in-angular-2](https://scotch.io/tutorials/create-a-globally-available-custom-pipe-in-angular-2)

## Router

* In depth practical article on the new  angular 2 router     [https://scotch.io/tutorials/routing-angular-2-single-page-apps-with-the-component-router](https://scotch.io/tutorials/routing-angular-2-single-page-apps-with-the-component-router)

## ES 6

* Exploring JS / Full online book on javascripting with extensive doc on ES6
[http://exploringjs.com/es6/ch_destructuring.html#_object-destructuring](http://exploringjs.com/es6/ch_destructuring.html#_object-destructuring)

## Typescript

* Detailed explanation about how the modules resolution works for the typescript compiler. How typescript find a module when we write something like :   

```js
// Relative import
import { Component, Input }   from '@angular/core';
// Non relative  import
import { OptionService }      from '../../../services/api/option.service';
```    

[https://www.typescriptlang.org/docs/handbook/module-resolution.html](https://www.typescriptlang.org/docs/handbook/module-resolution.html)

## System.js / JSPM

* A installation guide using JSPM / Typescript and System.js    
[http://www.mario-brendel.com/angular2-setup/2016/01/28/Angular2_Jspm_Setup_Part1/](http://www.mario-brendel.com/angular2-setup/2016/01/28/Angular2_Jspm_Setup_Part1/)

## Angular 2 & firebase

* Detailed post that explained the principle of firebase, why it is a good solution for BaaS application and allow to develop faster. Then it describe the integration in Angular2 with the angular fire library [http://blog.angular-university.io/angular-2-firebase](http://blog.angular-university.io/angular-2-firebase/)
* The official docs ? [https://angularfire2.com/api/](https://angularfire2.com/api/)
* The doc in the project [https://github.com/angular/angularfire2/tree/master/docs](https://github.com/angular/angularfire2/tree/master/docs)

## AOT Ahead of Time Compilation

* Demystifying AOT : Nice slides that present AOT as an easy thing ... [http://slides.com/wassimchegham/demystifying-ahead-of-time-compilation-in-angular-2-aot-jit#/30](http://slides.com/wassimchegham/demystifying-ahead-of-time-compilation-in-angular-2-aot-jit#/30)

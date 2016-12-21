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

## Forms

* Guide to forms in angular 2    
[http://blog.ng-book.com/the-ultimate-guide-to-forms-in-angular-2/](http://blog.ng-book.com/the-ultimate-guide-to-forms-in-angular-2/)

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

## Components 

* Children  view    
[http://blog.mgechev.com/2016/01/23/angular2-viewchildren-contentchildren-difference-viewproviders]()

## Modules 

Organize your code in a modular way. Import a module instead of importing a dozen of files (javascript modules). Despite of the use of ES6 modules in angular, angular  modules @ngModules are still useful to bundle a feature or a shared utility together. 

* [https://scotch.io/bar-talk/getting-to-know-angular-2s-module-ngmodule](https://scotch.io/bar-talk/getting-to-know-angular-2s-module-ngmodule)

## Decorator / Annotation syntax [Typescript]

* Difference between decorator and annotation [http://blog.thoughtram.io/angular/2015/05/03/the-difference-between-annotations-and-decorators.html](http://blog.thoughtram.io/angular/2015/05/03/the-difference-between-annotations-and-decorators.html)

## ES 6 

* Exploring JS / Full online book on javascripting with extensive doc on ES6 
[http://exploringjs.com/es6/ch_destructuring.html#_object-destructuring](http://exploringjs.com/es6/ch_destructuring.html#_object-destructuring)

## Typescript 

* Detailed explanation about how the modules resolution works with the typescript compiler. How typescript find a module when we write something like :    
```js
import { Component, Input }                from '@angular/core';
import { OptionService }                   from '../../../services/api/option.service';
```    
https://www.typescriptlang.org/docs/handbook/module-resolution.html

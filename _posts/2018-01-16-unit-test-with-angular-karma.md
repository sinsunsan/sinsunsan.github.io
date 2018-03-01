
---
layout: post
title: Unit test angular 5 with karma
published: true
---

* Official document in angular site 
https://angular.io/guide/testing#testing-utility-apis

* Practical tutorial in the context of angular 
https://semaphoreci.com/community/tutorials/testing-components-in-angular-2-with-jasmine

* What is unit test and continuous integration
http://taco.visualstudio.com/en-us/docs/unit-test-01-primer

* unit testing angular (Jasmine + Karma) 
https://codecraft.tv/courses/angular/unit-testing/jasmine-and-karma/

* A bit old but great description of 3 types of tests to angular components by Victor Savkin
https://vsavkin.com/three-ways-to-test-angular-2-components-dcea8e90bd8d

* Angular testing recipes 
A repository to an app with many testing case ordered by type
https://github.com/juristr/angular-testing-recipes

* Angular testing guide : good practicle documentation of test per types (component, service, pipes....)
https://medium.com/google-developer-experts/angular-2-testing-guide-a485b6cb1ef0

In this article he explain 3 types of components testing : 

* **isolated tests** are a great way to test drive your components and test complex logic. 
* **Shallow tests** are isolated tests on steroids, and they should be used when writing a meaningful test requires to render a component’s template. 
* **Integration tests** verify that a group of components and services (e.g., the router) work together.

* Testing component by rangle.io 
https://angular-2-training-book.rangle.io/handout/testing/components/

### DebugElement vs fixture.debugElement

2 Ways to access the DOM inside unit test in angular 

https://stackoverflow.com/questions/37705599/angular2-testing-whats-the-difference-between-a-debugelement-and-a-nativeeleme

https://angular.io/guide/testing#debugelement

The code Of Debug element a wrapper on DOM API 
https://angular.io/api/core/DebugElement
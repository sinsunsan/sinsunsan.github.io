---
layout: post
title: Start angular 2 now! What are the main differences with angular 1.
published: false
---

Angular 2 architecture have changed, but javascript too. The rise of ES6 usage accompany the release of angular 2. 
Angular  choose to have dependencies on zone.js and on typescript though it is possible to use angular 2 without typescript

## Typescript 

Typescript is  a superset on ES6. It means it have more features than ES6, but all features of ES6. The main feature it have is hard typings hence the name typescript https://www.typescriptlang.org
But not only, it allow also to use the decorator syntax @ used by angular heavily. 

At first I was not very enthusiast to use Typesript, because it is a software made by Microsoft and I kept with some bad opinions about this firm. But also because I kept with the idea hard typings was a thing for old fashioned java, c++ guys and was not useful in modern workflows. 

I changed my mind, about Microsoft and about hard typings! It could be really useful, and the best is that you can use it a lot or in a minimal way if you want. It allow you to intercept simple errors before compilation, which is not bad. 

The drawbacks are : 
* you can have bugs only caused by typings stuff....
* you need to compile back to a file readable by the browser but less readable by you. But anyway with ES6 we will be obliged to work like this till ES6 will be readable directly in all browsers.


## System js and ES6 stuff 

* **You need a package loader!**
    
* **ES6 is not only syntax changes**

## Components everywhere 

## Binding 
 * the syntax has changed
 * the 2 way bindings is no more the defrult 

## Syntax of standard directive

## Observable on top of promise

## Zone.js 

## Debuging 

The debug tools are not the same. I've not finished to discovered the possibilities. But I've found a chrome extension [Augury](https://augury.angular.io) that seem the defacto standard for viewing components hierarchy and properties. It display very nicely the dependencies, the components nesting. 

Though it does not always display all the public properties of the components classes. It is possible to type $a to debug in the console withing a component available properties. Though I did not find  yet the equivalent of $scope.mydata in angular 1.

It seems that is is not more useful to write $log.debug but the standard console.log seems enough. How to prevent console logs to display in prod? Do not know yet.


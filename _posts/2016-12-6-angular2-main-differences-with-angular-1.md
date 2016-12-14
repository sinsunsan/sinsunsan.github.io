---
layout: post
title: Start angular 2 now! Main differences from v1
published: true
---

Angular 2 architecture have changed, but javascript too. The rise of ES6 is parallel to the release of angular 2. 
Angular choose to have dependencies on typescript though it is possible to use angular 2 without typescript

## Typescript 

Typescript is  a superset on ES6. It means it have more features than ES6, but all features of ES6. The main feature it have is hard typings hence the name typescript https://www.typescriptlang.org
But not only, it allows also to use the decorator syntax @ used by angular heavily. 

At first I was not very enthusiast to use Typesript, because it is a software made by Microsoft and I kept with some bad opinions about this firm. But also because I kept with the idea hard typings was a thing for old fashioned java, c++ guys and was not useful in modern workflows. 

I changed my mind, about Microsoft and about hard typings! It could be really useful, and the best is that you can use it a lot or in a minimal way if you want. It allow you to intercept simple errors before compilation, which is not bad. 

The drawbacks are : 
* you can have bugs only caused by typings stuff....
* you need to compile back to a file readable by the browser but less readable by you. But anyway with ES6 we will be obliged to work like this till ES6 will be readable directly in all browsers.


## System js and ES6 stuff 

* **You need a package loader!**
    
* **ES6 is not only syntax changes**

## Components everywhere 

The component syntax is much, much clearer that in angular 1. By the way everything is component. That mean that no part of the page rendered by angular is not a component. 
That does not mean you need to over structure your app, with components, sub-components. 
It is up to  you to be granular as it is useful for you

## Binding 
 * the syntax has changed
 * the 2 way bindings is no more the default
 * Top > bottom binding is the default : the binding propagate to component and sub-components
 * To make bottom > top updates, you need to use a event system 
 
## Observable on top of promise

Observable are a new type of async object, like  promise but with much more possibilities. 
The doc of observable is available here : [reactivex.io](http://www.reactivex.io). 
Practically at first it could be as simple as replacing the **then** of promises 
by the **subscribe** of observable. 
But as you get more familiar with observables, you can do more.

{% highlight js %}

this.projectService
    .getProject(id)
    .subscribe(
    	project => {
    		this.project = project.fields;
    	}
    );
{% endhighlight ruby %}

          

## Debuging 

The debug tools are not the same. I've not finished to discovered the possibilities. But I've found a chrome extension [Augury](https://augury.angular.io) that seem the defacto standard for viewing components hierarchy and properties. It display very nicely the dependencies, the components nesting. 

Though it does not always display all the public properties of the components classes. It is possible to type $a to debug in the console the component available properties. Though I did not find  yet the equivalent of $scope.mydata in angular 1 : a quick way to output available data directly from the element tab of chrome debugger;

It seems that is is not more necessary to write $log.debug as the standard console.log seems enough. How to prevent console logs to display in prod? Do not know yet.

## Zone.js

### Events

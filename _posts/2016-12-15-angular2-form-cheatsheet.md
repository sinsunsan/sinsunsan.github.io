---
layout: post
title: Angular 2 forms cheatsheets
published: true
---
Angular 2 form add many improvements on angular1 version. There is good in depth tutorials explaining how to use it. 

But let's list some elements to record for those who used angular forms in version 1.


### 2 way to build forms : template driven and model driven 

Template driven is the tradionnal way with html and angular directives. 

* **Advantages**: 
   * Feel more natural and readable 
   * More customisable for usecase  not foreseen by the framework

* **Drawbacks**: 
   * Many boilerplates code : code that is always the same in all forms and not specific to this specific form. Boilerplates code is error prone because you can always mistype... And when there is a change in a big site, hundreds of templates need to be changed.

Model driven is with a form javascript API that angular 2 introduces in core. Where as in the version 1 only libraries were developing this concept.

* **Advantages**: 
  * Very compact declarative style  form definition 
  * Minimal boilerplates
  * Easy updates and config sharing among many forms 
  
* **Drawbacks**: 
  * You need to learn the API 
  * May feel less understandable for people that do not know the API


---
layout: post
title: Documentation generator for angular 5
published: true
---

## Documentation generators 

Analyse the code and comments and ouput a documentation automatically

Doc generator for Typescript / angular

### Compodoc [https://compodoc.github.io/compodoc/](https://compodoc.github.io/compodoc/)

* Advantages: 
   * simple to have a first result : angular structuration + typescript annotation make a lot of job
   * Have diffent themes similar that mimick other documentation system
   * Angular-CLI friendly - Compodoc support out of the box Angular-CLI projects

* Drawbacks 
    * Light support of jsdoc tags Support of **@param**, **@returns**, **@link** and **@example** tags

  
### Typedoc  

# Typedoc vs Compodoc 

* [Typedoc vs Compodoc on medium](https://medium.com/falafel-software/generating-documentation-for-angular-2-apps-and-nativescript-b8d2fa0bc9ae) This article explain the main difference between both tool one generic to typescript projects, the other specific to angular + typescript

* Issue discussing about that in the [angular starter project](https://github.com/AngularClass/angular-starter/issues/1370) Compodoc seems to be the clear winner with a nice viewer and an automatic documatation out of the box.

### Typescript documentation example 

2 examples found [here](https://blog.cloudflare.com/generating-documentation-for-typescript-projects/) that compare jsdoc and type script documentation style

**js doc style documentation**
<script src="https://gist.github.com/sinsunsan/fc197335138c579a1fff961b81102483.js"></script>

**typescript style documentation**
<script src="https://gist.github.com/sinsunsan/25729f1bfa42fd3d3d2d3a7a1ad98ec2.js"></script>

## Documentation standards

Define a standard for code commenting that can be used by documentation generators 

### Js doc 

* [Documentation of jsDoc](http://usejsdoc.org/)
* [Typedoc vs jsDoc](https://blog.cloudflare.com/generating-documentation-for-typescript-projects/)

---
layout: post
title: Practical guide to use angular 2 universal starter
published: true
---

Angular Universal allow to do server side rendering of the angular code.
Waiting front end code generate the page.

It allow that even if a user act on the page (click on items, change page...), the changes occurring in the server rendered side are replayed in the client rendered page.

So the end user will not see anything except it will be faster, Whereas google will see all the pages as though it were a normal user.

Look at this article to [have a more global view on angular universal](http://dev.sebastienlucas.com/universal-angular/).


## Clone the angular universal starter

* Universal angular starter    
[https://github.com/angular/universal-starter](https://github.com/angular/universal-starter)

## What file do what?

Here is the schema that I borrow from this [good article](https://medium.com/google-developer-experts/angular-universal-for-the-rest-of-us-922ca8bac84) by Wassim Chegham on Medium, that explain the role of each file.


![Files structure explained](../images/universal-files.png)

## Some vocabulary to start

For convenience let's use the following acronyms.

* **SSR** : Server side rendering
* **CSR** : Client side rendering

## Explanation of the role of each file in angular starter

### Files in the src folder

[src folder code on github](https://github.com/angular/universal-starter/tree/master/src)

In this folder are the files to be reused in your application.

### Files to handle SSR (Server Side Rendering)

* **node.module.ts** :
* **server.aot.ts** :
* **server.routes.ts** :
* **server.ts** :


### Files to handle CSR (Client Side Rendering)

_To be configured or customized_

* **browser.module.ts** Main angular @ngmodule for client side will replace your current MainModule or rootModule.


_To keep as if of minimally customized_

* **__workaround.browser.ts** : Patch of angular core (useful till angular v4) for CSR (Client Side Rendering) called  by client.ts

* **client.aot.ts** : bootstrap file version for AOT (Ahead of Time compilation)

* **client.ts** : bootsrap file for non AOT settings.

The main features of bootstrap files is the replace the the standard bootstraper
With a specific one. So this 3 lines are important :

````js
import { platformUniversalDynamic } from 'angular2-universal/browser';

// ...  More code

export const platformRef = platformUniversalDynamic();

platformRef.bootstrapModule(MainModule);

// ...  More code
````

* **__workaround.node.ts** : Patch of angular core (useful till angular v4) for SSR (Server Side Rendering)


In this file is an example of a definition of a main @ngmodule that you should use or replicate if you want to be universal angular compatible.

### Files used by both

* **index.html**

The [index.html](https://github.com/angular/universal-starter/blob/master/src/index.html) is pretty standard and you can use yours but mind the line at the end.
That insert the bundled file that is compiled by webpack.
You should do the same

* **typings.d.ts** An ambient type definition file that add typings to the variable used in this library. [Look at the code](https://github.com/angular/universal-starter/blob/master/src/typings.d.ts) to learn more about how to define types this way.


* **angular2-meta.ts** [File code](https://github.com/angular/universal-starter/blob/master/src/angular2-meta.ts). Related to the way meta tags (the tags at the top of HEAD section of the html documented is handled)

### Files in the src/app folder

[scr/+app folder on github](https://github.com/angular/universal-starter/tree/master/src/%2Bapp)

The files and sub-directories in this folder represent an example app with different cases you may encounter (lazy loading, loading data from an api..)

This is just an example app and you probably won't need it.

An exception could be a cache service

In [universal-starter/src/+app/shared/](https://github.com/angular/universal-starter/tree/master/src/%2Bapp/shared)

You may reuse some file to make the optional but recommended cache system functional in your app too.

### package.json of the universal starter

Specific parts to be added for universal rendering
```js
{

// Equivalent o platform browser but for the server
"@angular/platform-server": "~2.1.2",

// Deal with initialization
"@angularclass/bootloader": "~1.0.1",
"@angularclass/idle-preload": "~1.0.4",

// Rendering engine for express that know angular 2
"angular2-express-engine": "~2.1.0-rc.1",
"angular2-platform-node": "~2.1.0-rc.1",

// main library for angular 2 universal
"angular2-universal": "~2.1.0-rc.1",

// Some polyfill for the angular or node part
"angular2-universal-polyfills": "~2.1.0-rc.1"
}
```

---
layout: post
title: angular 2 selected libraries
published: false
---

Angular 2 libraries are less numerous than angular 1 equivalents, but they are growing fast. The good point is that you do not loose to much time finding the right one, as it used to be the case with angular 1. And as angular 2 is much clearer, they are generally easier to understand with less code, no dependency to jQuery...


### List of angular 2 resources

* **Awesome Angular**       [https://github.com/AngularClass/awesome-angular](https://github.com/AngularClass/awesome-angular2#ahead-of-time-compilation)


* **Awesome angular components** List of angular 2 components

[https://github.com/brillout/awesome-angular-components](https://github.com/brillout/awesome-angular-components)

### Font & icon

* **angular2-fontawesome** Font awesome wrapper,  make the icon a component or a directive and make font awesome options customisable

[https://github.com/travelist/angular2-fontawesome](https://github.com/travelist/angular2-fontawesome)


### Layout

* **flex layout** api on top of flexbox to automatize flex code and take account of breakpoint ...
Use directives to styles the page. Is independent of Angular material.

In their [flexbox api](https://github.com/angular/flex-layout/wiki/API-Documentation#containers)

There are
* container directives
* Child elements in a container directives
* Special directives (responsive utility...)

Code look like that
````pug
div(fxFlex fxLayout='row')
    div(fxFlex="20%")
      p Code
    div(fxFlex="30%")
      p Start Date
    div(fxFlex="30%")
      p End Date
    div(fxFlex="20%")
      p Status
````

And is then interpreted at run time to adapt to screen size.

### Parallax

* **Ang2 parallax**

[https://github.com/allenRoyston/ang2-parallax](https://github.com/allenRoyston/ang2-parallax)

###  Angular 2 UI components library

* **angular material 2**

[https://github.com/angular/material2](https://github.com/angular/material2)

* **semantic ui**

[https://semantic-ui.com/](https://semantic-ui.com/)
Plus it's angular 2 library
[ng-semantic.herokuapp.com](ng-semantic.herokuapp.com)

* **primeng** a collection of widget and library

[https://www.primefaces.org/primeng/#/fileupload](https://www.primefaces.org/primeng/#/fileupload)

* **ng bootstrap** a famous UI library in angular 1

[https://valor-software.com/ng2-bootstrap](https://valor-software.com/ng2-bootstrap)

* **dev extreme** Specialized in data viz, tables, filtering...

[https://github.com/DevExpress/devextreme-angular#demos](https://github.com/DevExpress/devextreme-angular#demos)

* **Fuel UI** On top of bootstrap 4

[http://fuelinteractive.github.io/fuel-ui/](http://fuelinteractive.github.io/fuel-ui/)

## Events

* **ng-radio** a message bus for angular to replace missing $cope.$emit and allow sibling components to talk and more generally global casting of  a message. Use RxJs [https://github.com/govorov/ng-radio](https://github.com/govorov/ng-radio)


* **angular2 notification** : toaster or browser notification to confirm events...
[https://github.com/flauc/angular2-notifications](https://github.com/flauc/angular2-notifications)

## Pipes

* **Angular pipes** : Shared pipes (filters) libraries. Standard  angular pipe are very limited but pipes are very similar project, so a library of pipes makes a lot of sense
[https://github.com/fknop/angular-pipes](https://github.com/fknop/angular-pipes)

The doc the [different available pipes](https://fknop.gitbooks.io/angular-pipes) it is available here or there on [how to define pipes in your modules and components](https://github.com/a8m/ng-pipes)

* **angular-linky** : angular wrapper on a js library that transform in links emails, urls, phone numbers...

[https://github.com/dzonatan/angular-linky](https://github.com/dzonatan/angular-linky)

* **Angular 2 Mardown** Convert markdown to html

Angular 2 markdown make also the auto-linking, you can  see all markdown styles in their [demo](https://dimpu.github.io/angular2-markdown/home).

[https://github.com/dimpu/angular2-markdown](https://github.com/dimpu/angular2-markdown)

* **Moment date pipes**

[https://github.com/urish/angular2-moment](https://github.com/urish/angular2-moment)


## Logging

* **ngLogger** a logger service for angular : allow to disable loging to group log....

[https://github.com/noemi-salaun/ng-logger](https://github.com/noemi-salaun/ng-logger)

## Data

* **JS-DATA** Data store for js  (front and back)
[Angular 2 example](https://github.com/js-data/js-data-examples/blob/master/client/angular2/src/store.ts)
[Using observable](http://www.js-data.io/v3.0/docs/jsdata-observables)


* **Angular + Redux** Integration of redux data store with angular 2

[https://github.com/angular-redux/store](https://github.com/angular-redux/store)

## Dynamic component....

* **ng-dynamic** One use case is "project" content to a content...dynamically

[https://github.com/laco0416/ng-dynamic](https://github.com/laco0416/ng-dynamic)

## Infinite scroll

* **Angular 2 infinite scroll**    [https://github.com/orizens/angular2-infinite-scroll](https://github.com/orizens/angular2-infinite-scroll)  


* **ng2-page-scroll** Scroll in the page
[https://github.com/Nolanus/ng2-page-scroll](https://github.com/Nolanus/ng2-page-scroll)

* **Angular Perfect Scrollbar** Wrapper for perfect scroll bar, a lib to customise the scrollbars

[https://github.com/zefoy/ngx-perfect-scrollbar](https://github.com/zefoy/ngx-perfect-scrollbar)

## Layout

* Flex  layout : Angular team  implementation of flexbox

[https://github.com/angular/flex-layout](https://github.com/angular/flex-layout)

## Drag & Drop

* Dragula : the most popular but as a wrapper to a vanilla js lib [https://github.com/valor-software/ng2-dragula](https://github.com/valor-software/ng2-dragula)

* Ng-dnd : angular native library
[https://github.com/akserg/ng2-dnd](https://github.com/akserg/ng2-dnd)

## Documentation

* **Angular doc** : Online documentation from github repo    [http://angulardoc.io/main](http://angulardoc.io/main)


## Observable

* **Using RXJS n angular**

[https://auth0.com/blog/making-use-of-rxjs-angular/](https://auth0.com/blog/making-use-of-rxjs-angular/)

* **Hot and cold observable**

[https://medium.com/@benlesh/hot-vs-cold-observables-f8094ed53339#.pf8m2ewlp](https://medium.com/@benlesh/hot-vs-cold-observables-f8094ed53339#.pf8m2ewlp)

* **Observable and subjects**

[http://stackoverflow.com/questions/39494058/angular-2-behavior-subject-vs-observable](http://stackoverflow.com/questions/39494058/angular-2-behavior-subject-vs-observable)

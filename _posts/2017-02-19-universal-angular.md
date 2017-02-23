---
layout: post
title: Angular 2 Universal Introduction (server side rendering)
published: true
---

We have written a more [step by step tuto to start with angular universal starter](http://dev.sebastienlucas.com/how-to-use-the-angular-universal-starter/).

But let's start with an introduction of what it is.

## Why

* SEO Friendly
* Social  media friendly (link posted in facebook, twitter...)
* Faster for the end users

## How  it works

* The site is rendered entirely in the backend with the good state
* It records the events the user may have triggered (click, hover..., change menu... )
* When the front end is loaded (in an hidden div), the events are replayed from the info stored by the backend
* Then it handle the rest of the request...

More details of  loading process step by step :

[https://github.com/angular/universal/blob/master/DOCUMENTATION.md#-how-does-it-work](https://github.com/angular/universal/blob/master/DOCUMENTATION.md#-how-does-it-work)

## Ressources

* **Universal angular starter**

[https://github.com/angular/universal-starter](https://github.com/angular/universal-starter)
* **Server side rendering in angular 2 with angular universal (scotch.io)**

[https://scotch.io/tutorials/server-side-rendering-in-angular-2-with-angular-universal](https://scotch.io/tutorials/server-side-rendering-in-angular-2-with-angular-universal)

* **A more cleaned up official tutorial**

[https://universal.angular.io/quickstart/](https://universal.angular.io/quickstart/)

* **Tutorial form angular academy**  

Explain a static prerendering technic (using gulp prerender) and at the end problem of authenticated prerendering and how to get the connected user info.

[http://blog.angular-university.io/angular-2-universal-meet-the-internet-of-the-future-seo-friendly-single-page-web-apps/](http://blog.angular-university.io/angular-2-universal-meet-the-internet-of-the-future-seo-friendly-single-page-web-apps/)

* **Another tuto on universal on medium : good  illustration**

[https://medium.com/google-developer-experts/angular-universal-for-the-rest-of-us-922ca8bac84#.h5ngcepfb](https://medium.com/google-developer-experts/angular-universal-for-the-rest-of-us-922ca8bac84#.h5ngcepfb)


* **A Fork of angular CLI that is compatible with universal**

[https://github.com/devCrossNet/universal-cli](https://github.com/devCrossNet/universal-cli)

## Unsolved questions

* How to deal with front router parameter in backend ?
`{ path: 'page/:pageId', component: pageComponent },`

* What to do with jquery library ? How jquery libs wrapper should be ? that touch the DOM ?


## What **not** to do in angular 2 to be universal loader compatible

* Not manipulate DOM directly nor with jquery
`document.domMethod() or $('dom-element')`
Instead use the following angular methods
    * [ElementRef](https://angular.io/docs/js/latest/api/core/index/ElementRef-class.html)
    * [Renderer](https://angular.io/docs/js/latest/api/core/index/Renderer-class.html)
    * [ViewContainerRef](https://angular.io/docs/ts/latest/api/core/index/ViewContainerRef-class.html)

## Libraries needed

* Template url and styles url need to be inlined and packed in the angular component :
> To use `templateUrl` or `styleUrls` you must use **`angular2-template-loader`** in your TS loaders.

If  you use inline css or html already this step is not necessary, but if you prefer like me writing css and html in a separate file, the content of the files need to be inline  by this  web pack plugin.

[https://github.com/TheLarkInn/angular2-template-loader](https://github.com/TheLarkInn/angular2-template-loader)


## How to test that the server rendering is correct ?

* See the source of the page : The source of the page is supposed to be the unmodified content retrieved from the server, whereas chrome debug explorer show the code produced from that by angular
* Disable javascript to have only the  server rendering :

This solution was proposed by [@MarkPieszak](https://github.com/angular/universal-starter/issues/372#issuecomment-281711218)
> One super easy way to test SSR is to go to your Chrome devtools, settings, and click the Disable JavaScript checkbox. Then try refreshing / clicking around your app. No client-side at all, everything came from the server! :)

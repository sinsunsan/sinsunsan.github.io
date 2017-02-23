---
layout: post
title: Universal angular global view
published: true
---
### Why

* SEO Friendly
* Social  media friendly (link posted in facebook, twitter...)
* Faster for the end users

### How  it works

* The site is rendered entirely in the backend with the good state
* It records the events the user may have triggered (click, hover..., change menu... )
* When the front end is loaded (in an hidden div), the events are replayed from the info stored by the backend
* Then it handle the rest of the request...

More details of  loading process step by step
[https://github.com/angular/universal/blob/master/DOCUMENTATION.md#-how-does-it-work](https://github.com/angular/universal/blob/master/DOCUMENTATION.md#-how-does-it-work)

### Ressources

* Universal angular starter     
[https://github.com/angular/universal-starter](https://github.com/angular/universal-starter)
* Server side rendering in angular 2 with angular universal (scotch.io)    
[https://scotch.io/tutorials/server-side-rendering-in-angular-2-with-angular-universal](https://scotch.io/tutorials/server-side-rendering-in-angular-2-with-angular-universal)
* A more cleaned up official tutorial   
[https://universal.angular.io/quickstart/](https://universal.angular.io/quickstart/)

* Tutorial form angular academy    

Explain a static prerendering technic (using gulp prerender) and at the end problem of authenticated prerendering and how to get the connected user info.

[http://blog.angular-university.io/angular-2-universal-meet-the-internet-of-the-future-seo-friendly-single-page-web-apps/](http://blog.angular-university.io/angular-2-universal-meet-the-internet-of-the-future-seo-friendly-single-page-web-apps/)

* Another tuto on universal on medium : good  illustration

[https://medium.com/google-developer-experts/angular-universal-for-the-rest-of-us-922ca8bac84#.h5ngcepfb](https://medium.com/google-developer-experts/angular-universal-for-the-rest-of-us-922ca8bac84#.h5ngcepfb)


* A Fork of angular CLI that is compatible with universal

[https://github.com/devCrossNet/universal-cli](https://github.com/devCrossNet/universal-cli)

### Starting

* Clone the starter repo [https://github.com/angular/universal-starter](https://github.com/angular/universal-starter)
* `npm run build` to build the modules
* `npm start` to start and see the test app set in universal loader with webpack

* **Create 2 boostrap files**: You will have 2 bootstraping files server.ts && client.ts for backend and front end or universal-server.ts && universal-client.ts to separate them more clearly from the other

#### Install

* Install angular universal library    
`npm install angular2-universal --save`

* Install the bootloader    
`npm install @angularclass/bootloader --save`      
[https://github.com/AngularClass/angular2-bootloader](https://github.com/AngularClass/angular2-bootloader)

* Install Polyfills

`npm install angular2-universal-polyfills --save`

* Angular 2 + express connection

`npm install angular2-express-engine --save`

* Express

The express node.js server

`npm install express --save`

#### client.ts

* Write the client.ts or copy it from a starter

```js
// ./src/client.ts
// the polyfills must be the first thing imported
import 'angular2-universal-polyfills';

// Angular 2
import { enableProdMode } from '@angular/core';
import { platformUniversalDynamic } from 'angular2-universal/browser';
import { bootloader } from '@angularclass/bootloader';

import { MainModule } from './browser.module';

export const platformRef = platformUniversalDynamic();

export function main() {
  return platformRef.bootstrapModule(MainModule);
}
// Bootstrap
bootloader(main);
```

* **Change bootstrap service**   

Where as non universal setup use this to bootstrap
`import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';`
we need to replace it by
`import { platformUniversalDynamic } from 'angular2-universal/browser';`

* **main module config**

The UniversalModule need to be imported first

```js
// ./src/browser.module.ts
import { NgModule } from '@angular/core';
import { UniversalModule } from 'angular2-universal/browser';

@NgModule({
    ...
  imports: [
    // Import this first
    UniversalModule,
    ...
  ]
})
export class MainModule {}
````

#### server.ts

The [starter full version](https://github.com/angular/universal-starter/blob/master/src/server.ts)

This is a Simplified version with only the universal specific settings.

You can find it [here](https://github.com/angular/universal/blob/master/DOCUMENTATION.md#-nodejs--express-integration).

````js
// ./src/server.ts
// polyfills have to be first
import 'angular2-universal-polyfills';
import { createEngine, ExpressEngineConfig } from 'angular2-express-engine';
import { MainModule } from './app.node.module';  // will change depending on your app

// 1. set up Angular Universal to be the rendering engine for Express
app.engine('.html', createEngine({}));

// 2. get the top level NgModule for the app and pass in important values to Angular Universal
app.get('/*', (req, res) => {

  // Our Universal - express configuration object
  const expressConfig : ExpressEngineConfig = {
    req,
    res,
    ngModule: MainModule,
    preboot: false,
    baseUrl: '/',
    requestUrl: req.originalUrl,
    originUrl: 'http://localhost:3000'
  };

  // NOTE: everything passed in here will be set as properties to the top level Zone
  // access these values in your code like this: Zone.current.get('req');
  // this is temporary; we will have a non-Zone way of getting these soon
  res.render('index', expressConfig);
});
````

#### node.module.ts

````ts
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { RouterModule } from '@angular/router';
import { UniversalModule } from 'angular2-universal/node';

@NgModule({
  imports: [
    UniversalModule,
    FormsModule,
    RouterModule,
    ...
   ],
   ...
})
export class MainModule {}
````

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

### Unsolved questions

* How to deal with front router parameter in backend ?
`{ path: 'page/:pageId', component: pageComponent },`

* Runnning  server code is compiled by webpack, so atom.io typescript interpreter
Because for example node global object is unknow for it

### How to start from the angular universal starter

* [https://github.com/angular/universal/blob/master/DOCUMENTATION.md#-nodejs--express-integration](https://github.com/angular/universal/blob/master/DOCUMENTATION.md#-nodejs--express-integration)

### What not to do in angular 2 to be universal loader compatible

* Not manipulate DOM directly nor with jquery
`document.domMethod() or $('dom-element')`
Instead use the following angular methods
    * [ElementRef](https://angular.io/docs/js/latest/api/core/index/ElementRef-class.html)
    * [Renderer](https://angular.io/docs/js/latest/api/core/index/Renderer-class.html)
    * [ViewContainerRef](https://angular.io/docs/ts/latest/api/core/index/ViewContainerRef-class.html)
* What to do with jquery library ? How jquery libs wrapper should be ?


### Libraries needed

* Template url and styles url need to be inlined and packed in the angular component :
> To use `templateUrl` or `styleUrls` you must use **`angular2-template-loader`** in your TS loaders.

If  you use inline css or html already this step is not necessary, but if you prefer like me writing css and html in a separate file, the content of the files need to be inline  by this  web pack plugin.


[https://github.com/TheLarkInn/angular2-template-loader](https://github.com/TheLarkInn/angular2-template-loader)


### How to test that the server rendering is correct ?

* See the source of the page : The source of the page is supposed to be the unmodified content retrieved from the server, wheras chrome debug explorer show the code produced from that by angular
* Disable javascript to have only the  server rendering :

This solution was proposed by []@MarkPieszak](https://github.com/angular/universal-starter/issues/372#issuecomment-281711218)
> One super easy way to test SSR is to go to your Chrome devtools, settings, and click the Disable JavaScript checkbox. Then try refreshing / clicking around your app. No client-side at all, everything came from the server! :)

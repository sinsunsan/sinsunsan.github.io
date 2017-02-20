---
layout: post
title: Universal angular
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

### Ressources

* Universal angular starter     
[https://github.com/angular/universal-starter](https://github.com/angular/universal-starter)
* Server side rendering in angular 2 with angular universal (scotch.io)    
[https://scotch.io/tutorials/server-side-rendering-in-angular-2-with-angular-universal](https://scotch.io/tutorials/server-side-rendering-in-angular-2-with-angular-universal)

### Starting

* Clone the starter repo [https://github.com/angular/universal-starter](https://github.com/angular/universal-starter)
* `npm run build` to build the modules
* `npm start` to start and see the test app set in universal loader with webpack

* **Create 2 boostrap files**: You will have 2 bootstraping files server.ts && client.ts for backend and front end or universal-server.ts && universal-client.ts to separate them more clearly from the other
* Install angular universal library    
`npm install angular2-universal --save`

* Install the bootloader    
`npm install @angularclass/bootloader --save`      
[https://github.com/AngularClass/angular2-bootloader](https://github.com/AngularClass/angular2-bootloader)


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

* **Import angular-universal in your mail module**

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



### Libraries needed

* Template url and styles url need to be inlined and packed in the angular component :
> To use `templateUrl` or `styleUrls` you must use **`angular2-template-loader`** in your TS loaders.

If  you use inline css or html already this step is not necessary, but if you prefer like me writing css and html in a separate file, the content of the files need to be inline  by this  web pack plugin.


[https://github.com/TheLarkInn/angular2-template-loader](https://github.com/TheLarkInn/angular2-template-loader)

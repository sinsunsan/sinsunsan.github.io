---
published: true
layout: post
title: JSPM / A good alternative to web pack
---
Jspm is an alternative to using webpack. It's philosophy is quite different and intersting. Here is what you need to know about it. 

The main site 
http://jspm.io/

The documentation of  jspm
https://github.com/jspm/jspm-cli/tree/master/docs

* JSPM use existing Package managers : NPM & Github 

* JSPM manager the config.js file to be used by system.js 

* JPSM store it's information is 2 places: the **package.json** and the **config.js** file 
The first one is used by NPM and allow to reproduce the exact JSPM installation 
The second is used by system.js and allow to the JS module  loader to do the mappging between named ```import  import * from { @angular }```
and the exact location of the file in the `jspm_packages`

### How to 

#### how to update JSPM managed libraries ot latest version 

````jspm update````

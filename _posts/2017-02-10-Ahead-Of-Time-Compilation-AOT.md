---
layout: post
title: AOT : Ahead of Time Compilation / Why you should use it
published: true
---

AOT is a way to speed up angular loading by precompiling it in advance.

Nice slides by [@manekinekko](https://twitter.com/manekinekko) that explain the concept.

<iframe src="//slides.com/wassimchegham/demystifying-ahead-of-time-compilation-in-angular-2-aot-jit/embed" width="576" height="420" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

### Ressources

* [The official tutorial](https://angular.io/docs/ts/latest/cookbook/aot-compiler.html)
* [Demystifying AOT simple slides to understand AOT](http://slides.com/wassimchegham/demystifying-ahead-of-time-compilation-in-angular-2-aot-jit#/30))

### What ?

Angular code need to be compiled to be executed.
There is 2 ways of doing this compilation
* JIT- Just in Time :   
This compilation can take place before the code is starting in the client.
It is the standard way of developing, you probably already practice.
* AOT- Ahead of Time :
The code is precompiled so it take less time to download for each client and get executed

### Which benefits in using AOT ?

* **Save libs transfer**: Do not need to download the compiler and other libs only useful for compilation process
* **Save compilation time**: Do not need to wait for the compilation process to take place in the client
* **Detect errors early**: Allow to detect compilation errors early without that the client even saw it
* **Save http request**: The templates and css are inlined in the compilation process so you save many http request that slow down the loading
* **Better security**: Less javascript evaluation mean less possiblity for vulnerability

### How to install it in your projects

* 1/ Download compiler libs

   * @angular/compiler-cli
   * @angular/platform-server

`npm install @angular/compiler-cli @angular/platform-server --save`

> You will run the ngc compiler provided in the @angular/compiler-cli npm package instead of the TypeScript compiler (tsc).


* 2/ Copy tsConfig.json

`cp tsconfig.json tsconfig-aot.json`


* 3/ in **compilerOptions** change module": "system" to "module": "ES2015"

* 4/ add the **angularCompilerOptions**

"angularCompilerOptions": {
   "genDir": "aot",
   "skipMetadataEmit" : true
 }

* 5/ Check and fix if need Component-relative Template URLS

[More about component relative paths](https://blog.thoughtram.io/angular/2016/06/08/component-relative-paths-in-angular-2.html)
...

* 6/ Add a line in your package.json scripts
```json
"scripts": {
  "ngc": "node_modules/.bin/ngc -p tsconfig-aot.json"
}
```
run the command
`npm run ngc`
It will compile the code to aot folder

* 7/ Change the boostraping

 * 8/ Add treeshaking with rollup

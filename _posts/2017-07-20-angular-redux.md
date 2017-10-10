---
layout: post
title: Angular + Redux = NGRX / A  rxjs powered redux store
published: true
---

### What it is?
Redux is a way to store in a centralized place data so that all the app  can udpate flowlessly by subscribing to some events. For exemple if a component need to listen udpates of "projects" content, he get informed when this event occur.

### Links to start with

* Angular 2 and Redux simplified 
[https://medium.com/beautiful-angular/angular-2-with-redux-using-ngrx-store-2f93a8ad0dd](https://medium.com/beautiful-angular/angular-2-with-redux-using-ngrx-store-2f93a8ad0dd)

* There is a official [demo / starter app](https://github.com/ngrx/platform/tree/master/example-app) to get a global view on a ngrx based application

[Demo code](https://github.com/ivanderbu2/angular-redux) on how he setup Redux in an angular 2/4 project.

* [in depth tuto about ngrx for angular 2-4](https://blog.angular-university.io/angular-ngrx-store-and-effects-crash-course)

### Blog university tutorial notes

* The tuto start with a description of the facebook counter bug that initiated the switch to a redux like architecture for Facebook homepage. 

* Notion of viewModel which is the derivation of the a model for the diplay purpose of a view. 
* > The transformation from view to view Model is done via a function called a Selector - the input of a Selector is the Model, and the output is the View Model
* the data is stored as a map rather that an array (optimized for by id query (same way firebase used)) 

Example map 

````
{
    1: 
        { 
            id: 1, 
            value: "blue"
        }

}
````

* In the store we store both application model and ui state and user preference...


### What to install 
 
* [store](https://github.com/ngrx/store) The main component (but not obligatory) to install the architecture. For example you can use actions and effects without to the store
* [store dev tools](https://github.com/ngrx/store-devtools) Tools integrated with the chrome extension to debug ngrx powered application
* [router store](https://github.com/ngrx/router-store-builds) integration with the angular router
* [effects](https://github.com/ngrx/effects) Side effects.... (there is a different version for angular 2 and 4)


But since 4 version all those packages are put in [one github repository](https://github.com/ngrx/platform). Installing each libs separetely is though still needed.

````
npm install @ngrx/store @ngrx/store-devtools @ngrx/router-store-builds @ngrx/effects --save
````


Tigger an error is state is not correctly cloned  in the reducer

````
npm install ngrx-store-freeze --save-dev
````

you should then have in your package.json something like 
````
dependencies: {
    "@ngrx/effects": "^4.0.0",
    "@ngrx/router-store": "^4.0.0",
    "@ngrx/store": "^4.0.0",
    "@ngrx/store-devtools": "^4.0.0",
},
"devDependencies": {
    "ngrx-store-freeze": "^0.2.0",
}
````

### NGRX terminology 

* **store**: the shared service managed by the ngrx library that manage state and trigger event when the state is changed
* **state**: current value of the store. the state is customized by feature to make available the useful part of the  global state
* **action**: an action triggered by the user like clicking on a button, changing view that impact the global state
* **effect**: a change to do when an action is triggered



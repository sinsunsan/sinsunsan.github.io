---
layout: post
title: Observable RXJS practical examples for Angular 2
published: true
---

### [Observable] Observable.combineLatest

* **When to use ?** : You have 2 queries or more. You need to do something depending of the results of those queries. For example  you need to wait for page params and get the connected user informations...

> CombineLatest emits an item whenever any of the source Observables emits an item (so long as each of the source Observables has emitted at least one item)

So you have 2 or more async observables, the Observable.combineLatest is called after each emitted their first value, and give the opportunity to a function to remit a item  with the value  of the last emitted item

* [official doc](http://reactivex.io/documentation/operators/combinelatest.html)


### [Subject] Behavior subject

A variable  that is changed using next() and "watched" using subscribe
* [official doc on subjects](http://reactivex.io/documentation/subject.html)

* **When to use ?** : When we need to keep an updatable value (for example the connected  user) and get all components updated when this value change

### [Operator] map

Allow to change the  value of each emited items before  it is sent to function subscribing to it.

* **When to use ?** : After api query when we generally want to convert to Json, control with libraries like [TypedJson](https://github.com/JohnWeisz/TypedJSON)...

* [ official doc on map operator](http://reactivex.io/documentation/operators/map.html)

---
published: true
title: Debug tips & tricks for Angular 2
---

A few debug tricks learned by the ways.

### Screen debug with | json pipe

You can use Augury but some time a simple in screen debug is convenient.

You can do it thanks to the json pipe that transform json objects in string.    

`my object | json`    

It is convenient for forms where we want to see the consequence of your actions. And track the form state.

Using html PRE tag allow to display the json with line break.


````
<div style="margin-top: 20px" *ngIf="f">
	<div>Form details:-</div>
	<pre>Is form valid?: <br>{{f.valid | json}}</pre>
	<pre>Is form submitted?: <br>{{f.submitted | json}}</pre>
	<pre>submitted value: <br>{{f.value | json}}</pre>
</div>
````

### Augury

[https://augury.angular.io/](https://augury.angular.io/)

Augury is a more complete debug utility for chrome.
It can display the state of variable in each component.

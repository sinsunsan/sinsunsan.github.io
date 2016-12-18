---
published: true
title: Debug tips & tricks for Angular 2
---
A few debug tricks learning by the ways

You can use Augury but some time a simple in screen debug is convenient. 
You can do it thanks to the json pipe than transform json object in string.    
`my object | json`    

It is not very readable for long objects, but do the trick for some. 
It is convenient for forms where we want to see the consequence of ours actions. 
And track the form state. 

````
h4 Form Debug
div valid: {{ projectForm.valid}}
div data: {{ projectForm.value | json }}
div project: {{ project | json }}
````
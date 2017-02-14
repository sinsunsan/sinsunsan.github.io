---
layout: post
title: Typescript / The future of javascript now!
published: true
---

* Type script official documentation
[https://www.typescriptlang.org/](https://www.typescriptlang.org/)

* An open source book on typescript
[https://basarat.gitbooks.io/typescript](https://basarat.gitbooks.io/typescript)

### Example of a d.ts file

[https://github.com/limonte/sweetalert2/blob/master/sweetalert2.d.ts](https://github.com/limonte/sweetalert2/blob/master/sweetalert2.d.ts)

Definition of the main function of sweealert 2 ( a library to display nice alert confirm modal

````
function swal(title: string, message?: string, type?: SweetAlertType): Promise<any>;
````

the function parameters are defined by not the content of the function wich is not the purpose of the d.ts file is here to documentate the typings of js files of existing libraries not written dirctly in typescript. 

We identify the syntax for funtion parameters : 

* **title** is the first argument and should be a string 
* **message** is the second argument and should be a string, it is an optional parameter it don't produce an error if not provided. 
* **type** is optional and is not using a standard type but a custom type SweetAlertType that is defined elsewhere 
* **`: Promise<any>`** refer to what the function should return. It should return a Promise with a collection / array of element of any types

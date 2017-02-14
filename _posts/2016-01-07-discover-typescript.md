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

The function parameters are defined by not the content of the function which is not the purpose of the d.ts file is here to documentate the types of js files of existing libraries not written directly in typescript. 

We identify the syntax for function parameters : 

* **title** is the first argument and should be a string 
* **message** is the second argument and should be a string, it is an optional parameter it don't produce an error if not provided. 
* **type** is optional and is not using a standard type but a custom type SweetAlertType that is defined elsewhere 
* **`: Promise<any>`** refer to what the function should return. It should return a Promise with a collection / array of element of any types

Then we follow with the definition of an interface. Interface ies the definition of an empty object that serve as a model to constrain object with real data in it. It serve as a guide for developer that in the code use an implementation of this same object. It serve to define what we called custom types, types are not the standard string, bolean....

````
 export interface SweetAlertOptions {
        /**
         * The title of the modal, as HTML.
         * It can either be added to the object under the key "title" or passed as the first parameter of the function.
         * Default: null
         */
        title?: string;

        /**
         * The title of the modal, as text. Useful to avoid HTML injection.
         * Default: null
         */
        titleText?: string;
        
        // More fields definition
   }
 ````
 
 An other syntax is alternative types
 ` width?: number|string;`    
 Here we allow either number either string for the optional property 'width' of the SweetAlertOptions object.
 
 
 We identify also this syntax 
`preConfirm?: (inputValue: any) => Promise<any>;`
it defined a function with the new ES6 syntax called fat arrow syntax => 
So this function assigned to optional `preconfirm` property need an argument `inputValue` of any type 
that return a promise with a collection of element of any type.


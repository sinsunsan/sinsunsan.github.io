---
layout: post
title: How to use Airtable API
published: true
---
Airtable is an interesting tool for web developer as it is as the crossroad of database ui like phpmyadmin, robotmongo, a spreadsheet like google spreadsheet and a api. 

You can use airtable as an api in a nobackend strategy. Even if you end up using other data storage. It is a good way to start prototyping with true data. Its simplicity of usage allow all team members even non technical to participate. 

You can create your [free account](https://airtable.com/invite/tmyzgSjU "Airtable database in the cloud"). 

## Where to find documentation about Airtable API ? 

The main documentation is findable inside your Airtable UI

- Click on the contextual menu    

![Airtable API doc]({{site.baseurl}}/_posts/airtable1.png)


- Then a documentation screen show up dependent of your database settings    

![Airtable contextual doc]({{site.baseurl}}/_posts/airtable3.png)![airtable3.png]


* A [blog post explaining some changes](http://blog.airtable.com/post/138484080527/the-right-sort-of-api-updates) (feb 2016) to the api client

* a [codepen](https://codepen.io/airtable/full/rLKkYB) allowing to quickly url encode parameters


## Airtable API usage examples

Let's look at some nice usage of airtable API.

Airtable is an easy to use database that can be edited by non developper. It has a nice api that can do powerful filtering. 


Let's see a few example of which queries can be made: 

### API query usage

In all example {tableId} is to be replaced by your table Id. 
And {DatabaseId} by your database Id

* **Limit number of items per page**   
To do pagination   

`https://api.airtable.com/v0/{DatabaseId}/{TableId}?pageSize=1`
    
* **Filters items with a title equal to a defined value**   
Exact title match   

`https://api.airtable.com/v0/{DatabaseId}/{TableId}?filterByFormula={title}="Ternes"`
     
* **Filters records using a math function on one of their number field**   
We want to display records with a currency field "cost" superior to defined amount   

`https://api.airtable.com/v0/{DatabaseId}/{TableId}?filterByFormula={cost}>1000000`

### Filter a list by a related field

A related field relates 2 tables let's take an example. A project table and an architect table. The "architect" field in the "project" table refer to the architect that have designed the project. An architect tables show more details on this architect.

The  problem is that in the api the output of a related field is an array of the related records id. 

![Related fields in airtable]({{site.baseurl}}/_posts/related-field.png)

So I wandered if the query was something like 

![Filter by formula]({{site.baseurl}}/_posts/filterByFormula.png)

But it seems that is not the case, as the api always return this error mesage.
```json
{
  "error": {
    "type": "INVALID_FILTER_BY_FORMULA",
    "message": "The formula for filtering records is invalid: please check your formula text."
  }
}
```

I've posted an [issue](https://github.com/Airtable/airtable.js/issues/15) on airtable.js client to know more about it. But after trial and error, tryed with the name of the linked record (not it's id) and it worked. 

![Filter by formula 2]({{site.baseurl}}/_posts/filterbyformula2.png)

I am listing all projects of architects. I want to click on one architect name to have this list limited to only his projects. As we have just seen, I need his name to do the filtered projects request.

But now how to get the record name from the table query ? As I need it to make the query. Should I first hit a reuqest to get all architect information, before making a request for his projects. 

There seem to have a solution with the lookup fields ![lookup fields]({{site.baseurl}}/_posts/lookup.png)

Lookup fields allow to list in the projects query a field of a related field table. As we need architect's name, we gonna choose architect table and name field. 
And that's it we have both the id and the name of the architect in our first project call.

![Lookup airtable fields]({{site.baseurl}}/_posts/architect_architectNAme.png)

Great ! 

So now the question is is there a way to query directly a list limited by one of it's  related fields id ? Which would be much more natural fro a developer. 
Well I do no know yet :)



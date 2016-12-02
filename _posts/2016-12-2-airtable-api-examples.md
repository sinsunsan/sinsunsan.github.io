---
layout: post
title: How to use Airtable API
published: true
---
## Where to find documentation about Airtable API ? 



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

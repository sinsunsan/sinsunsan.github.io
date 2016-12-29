---
published: true
title: Tutorials to learn node.js
---
Node.js is quite straightforward and easy to learn once we have understood the basics. Though it is a huge ecosystem and there is a lot to learn to master it. The good thing is that it is in javascript. And the more you learn javascript for the backend, the more you master it in the front.

The module system for example has played an important role in the ES6 modules adoption. Indeed modules (require in node.js) are so convenient and natural to split the code in different files.

## Modules 

## Express

## Async 

[https://blog.risingstack.com/node-hero-async-programming-in-node-js/](https://blog.risingstack.com/node-hero-async-programming-in-node-js/)

## Error Handling

[https://www.joyent.com/node-js/production/design/errors](https://www.joyent.com/node-js/production/design/errors)

## Debug 

The node  debugger that use chrome debugger is available in latest version of node 
using the --inspect flag

```
$ node --inspect index.js
Debugger listening on port 9229.
Warning: This is an experimental feature and could change at any time.
To start debugging, open the following URL in Chrome:
    chrome-devtools://devtools/remote/serve_file/@60cd6e859b9f557d2312f5bf532f6aec5f284980/inspector.html?experiments=true&v8only=true&ws=localhost:9229/b4f005c7-caad-4e7c-b554-5746da12b549
Server listening on 3000
Debugger attached.
```

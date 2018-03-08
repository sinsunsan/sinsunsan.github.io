---
layout: post
title: ES6 functions to use as an alternative to lodash
published: true
---

Lodash is great, we have an article about [most useful lodash functions](http://dev.sebastienlucas.com/lodash-best-of/). But those function are pretty low level. They should be at the level of the language it self javascript. With ES6, javascript got more powerful, so it is time to stop using some of lodash function to use their ES6 equivalent. The advantage is that we could more easily tweak the function for our needs which is not possible with lodash. And get more knowledge and confidence about ES6

### array.reduce instead of _.keysBy

<script src="https://gist.github.com/sinsunsan/4b733d2e03fb77c6bb8cea160fbb8ef7.js"></script>


### Object.keys instead of _.keys

<script src="https://gist.github.com/sinsunsan/39c3573696e953fe075c317a77590c5a"></script>


### Object.assign or spread operator

<script src="https://gist.github.com/sinsunsan/4152a5c0fc6058fd876585792b611c3f.js"></script>
---
layout: post
title: Library of angular 2-4-5  code example and snippets
published: true
---

### http interceptor to add a token to all outgoing request 

To make json web token authentication, we need to pass  token to the server. It is convenient to make this token logic independant of each api call so that it is global. An interceptor intercept all request outgoing or ingoing to make modification to them. So we can create a service that deal with interception. 

<script src="https://gist.github.com/sinsunsan/adba1f200f6a34165ae6b8ae8ab2e09f.js"></script>
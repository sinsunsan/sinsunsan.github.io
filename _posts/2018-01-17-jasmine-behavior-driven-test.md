---
layout: post
title: Jasmine behavior driven test
published: true
---

Very good introduction to Jasmine https://codecraft.tv/courses/angular/unit-testing/jasmine-and-karma

Video explanation : talk about unit test, what is it, test in general...

### JASMINE before / after functions

Run before all test suite tests

* beforeAll 
* afterAll 

Run before each tests, before this test or after this test

* beforeEach
* afterEach


### Disable temporarly a test 

Put x in front of describe  (the test suite = group of tests) `xdesribe`
and x in front of it (the test) so `xit`

It allows to disable a test temporarly though still listing it and not commenting it 
To be able to see the test code.

put f in front of it to focus only on one test (only run one test)
so write 
`fit('the test to focus on')`


### The hiearchy of unit test 

* A test suite : a group of test (describe)
* A test spec : one individual test (it)
* A test expectation : what we are testing (expect)


### What do Karma do 

Karma is a test runner, it is not compulsary to use it. Though it is easier : 

* It rerun the tests when code change 
* It open a separate browser (headless)
* It get Jasmine result in the command line 

https://github.com/karma-runner/karma/releases


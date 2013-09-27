---
layout: post
title: Using EclEmma to write better unit tests
categories: []
tags:
- Code
- Code Coverage
- Java
- Testing
status: publish
type: post
published: true
meta:
  _edit_last: '1'
  _wp_old_slug: ''
  _wpas_skip_3189768: '1'
  _wpas_skip_3189772: '1'
  _wpas_skip_3189777: '1'
---
If you don't already write unit tests you should be. (Hey, why aren't you writing unit tests?) Unit testing has so many benefits and the upfront developer cost to write some unit tests can pay huge dividends later when you aren't spending time debugging broken code nor attempting to save face due to clueless mistakes. You can also use them as a contract to the expectations of your implementations.

So, assuming you have some unit tests, how useful are they if they don't test everything? At some level you will want to have a good idea that you're testing everything. (NOTE: I mean everything really important. Writing perfect 100% coverage like this would likely be too expensive for the entire codebase.) This is where [Emma][] comes in (and more importantly for us, [EclEmma][], an Eclipse plugin for Emma). Emma is a code coverage tool which lets you visual which parts of your code get executed during some execution (regular or JUnit).

[emma]: http://emma.sourceforge.net/
[eclemma]: http://www.eclemma.org/index.html

Lets walk through using EclEmma to ensure that we have adequate testing being done. Lets test the following two classes.

GuessTheNumber.java:

{% gist 760542 %}

And SequentialStrategy.java:

{% gist 760543 %}

Finally, we'll write up a basic StrategyTest.java:

{% gist 760545 %}

So the question is, how good is our test? If you installed EclEmma, you can right click on your Unit Test in Eclipse, head to "Coverage As" -> "JUnit Test"

<img src="/assets/using-eclemma-to-write-better-unit-tests/a.png" class="size-actual" />

This will run your unit test against your code and when complete, highlight the code green, yellow, or red for covered, partially-covered, and not-covered respectively.

According to EclEmma, our code coverage when running StrategyTest is:

<img src="/assets/using-eclemma-to-write-better-unit-tests/b.png" class="size-actual" />

Thats not too bad, lets take a look at the output for SequentialStrategy:

<img src="/assets/using-eclemma-to-write-better-unit-tests/c.png" class="size-actual" />

We may want to test the IllegalStateException since we currently don't and we are expecting it to happen if we've guessed everything between min and max and haven't solved the problem. This would ensure if someone else comes in behind us and changes this code, the unit test will fail if they take that out and change it to return, say, Integer.MIN_VALUE.

Lets also take a look at some of GuessTheNumber:

<img src="/assets/using-eclemma-to-write-better-unit-tests/d.png" class="size-actual" />

It appears we also want the contract to include an IllegalStateException being thrown if you have already solved the guessing game. It also looks like we don't ever call resetCount() and possibly retest after doing that. We also never check if getValue() fails prior to having a solution.

If we modify the test slightly to:

{% gist 760546 %}

And now our code coverage is:

<img src="/assets/using-eclemma-to-write-better-unit-tests/e.png" class="size-actual" />

I know this was a very basic example that really didn't test any complex logic or conditions, but I hope it gives you a good idea of how you can use code coverage to improve your unit tests.

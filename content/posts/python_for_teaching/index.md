---
title: "Overteaching - an error"
date: 2017-12-04T13:21:01Z
draft: false
tags: [teaching, code, python]
categories: []
author: ""
showToc: false
TocOpen: false
hidemeta: false
comments: false
description: "Choosing the right level of abstraction to work at is important."
canonicalURL: ""
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
cover:
  image: "ram_list.png"
  hiddenInSingle: false
---

### Teach one thing at a time.

An intuition that many have when teaching is to start at the foundation and strictly work upwards. In programming this translates to working with languages that reveal to you some aspects of the hardware, brick by brick, and doing things like putting stuff in memory.

The all-knowing-already teacher intuits that in order to understand one thing you should understand everything else holding it up. This is obviously untrue when you give it any thought. You don't need to understand the details of fluid dynamics to be an expert engine mechanic. You don't need to grep math proofs to manage global scale financial systems. We operate our whole lives almost exclusively in abstraction layers with no idea whatsoever about the scaffolding holding it up.

So... you don't need to know about memory addresses to loop through a list :)

Before the teacher puts pen to paper in the session, they'll probably say something really lovely and expressive like

_"We want to transverse a list of items in sequence, printing the value of each element as you go"._

This pretty much captures list iterating _and_ the task at hand in one easy to understand sentence. But then! (Go tobann!)

The common approach to teaching list iteration is some shit in C like:

```C
    for ( int i = 0; i < itemsSize; i += 1 ) {
      printf("%d\n", items[i]);
    }
```

Which, when you factor in the detritus needed to even set this up...

```C
    int items[] = {1, 2, 3, 4};
    int itemsSize = sizeof(items) / sizeof(items[0]);
```

... quickly turns in to quite a few things to remember for a new programmer. Remember as you read this that for new programmers even the decision to use [] vs {} is new info to be juggled and managed. They are remembering things about the sizes of items in arrays, and the return value of sizeof, and... what type was that again? What's a type?

But this all makes the teacher feel _oh so correct_. It feels like the _path is right_. It feels like by taking this approach, one step at a time, they are truly elevating the student. They're being true to them and true to the fundamental realities of the world behind the code.

**However it's little more than littering.**

The goal was to teach lists and list iteration, and look at the mess we've made.

### Some python to save the day.

```python
    items = [1, 2, 3, 4]

    for item in items:
      print(item)
```

It practically explains its self. It gets to the core concept so quickly and precicely it's unbelievable. The baggage involved is so minimal even ryanair won't blink twice.

Refer back to the simple sentence:

_"We want to transverse a list of items in sequence, printing the value of each element as you go"._

There it is in code. The student has truly learned something.

**They can digest the whole concept in one bite.**

There are of course other languages that are expressive like this, or even in their own uniquely lovely ways. But I mean come on. It's python.

And there are of course other areas this idea applies to. Do you need to know about elastic modulus to swap your steel tool for a carbide one? Or does "it's stiffer" suffice? Overteaching is bad :)

___

This is a rewrite of a ten year old much rantier post :)

---
layout: post
title:      "What is Hoisting?"
date:       2020-03-26 22:27:08 +0000
permalink:  what_is_hoisting
---


"Hoisting" refers to Javascript's default behavior of raising function and variable declarations to the top of a given scope. For example, you could invoke a function before defining it and it would still be carried out where it was invoked. This is because Javascript reads files in two phases: the compilation phase, and the execution phase. During the compliation phase, all invocations of functions and variables are skipped over while function and variable *declarations* are read and stored in memory, so when Javascript reads an invocation during the second phase, the declaration for that invocation has already been created. When declaring a variable using *var*, you might run into some hoisting issues. When a variable is declared, its value is *undefined* until it gets assigned one, which doesn't happen until the execution phase. Because of this, invoking that variable before it is declared will cause that variable's value to be *undefined* in that invocation, since at that point in time, that's what the variable's stored value is. Unlike with *var*, if you declare a variable using *let* or *const* after invoking it, you will get a "variable is not defined" error instead of that variable existing with a value of *undefined*. This is because Javascript doesn't allow *let* and *const* to be referenced before they are initialized. In either case, to be on the safe side you should try to always define your variables before they're invoked.

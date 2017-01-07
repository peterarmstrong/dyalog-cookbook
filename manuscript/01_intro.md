{:: encoding="utf-8" /}

# Introduction

You want to write a Windows[^win] application in Dyalog APL. You have already learned enough of the language to put some of your specialist knowledge into functions you can use in your work. The code works for you. Now you want to turn it into an application others can use. Perhaps even sell it. 

This is where you need professional programming skills. How to install your code into an unknown computer. Have it catch, handle and log errors. Manage the different versions of your software as it evolves. Provide online help. 

You are not necessarily a professional programmer. Perhaps you don't have those skills. Perhaps you need a professional programmer to turn your code into an application. But you've come a long way already. Perhaps you can get there by yourself - with _The Dyalog Cookbook_. Alternatively, you might be a professional programmer wondering how to solve these familiar problems in Dyalog APL. 

_The Dyalog Cookbook_ is about how to turn your Dyalog code into an application. We'll cover packaging your code into a robust environment. And we'll introduce some software development tools you've managed without so far, which will make your life easier.

You might continue as the sole developer of your application for a long time yet. But if it becomes a successful product you will eventually want other programmers collaborating on it. So we'll set up your code in a source-control system that will accommodate that. Even while you remain a sole developer, a source-control system will also allow you to roll back and recover from your own mistakes. 

Not so long ago it was sufficient for an application to be packaged as an EXE that could be installed and run on other PCs. Nowadays many corporate clients run programs in terminal servers or in private clouds. So we'll look at how to organise your program to run as tasks that communicate with each other. Many applications written in Dyalog focus on some kind of numerical analysis, and can have CPU-intensive tasks. We'll look at how such tasks can be packaged to run either in background or on remote machines. 


## Method

It's conventional in this context for authors to assure readers that the techniques expounded here have been hammered out, proven and tested in many successful applications. That is true of individual components here, particularly of scripts from the APLTree library. But the development tools introduced by Dyalog in recent years are still finding their places with development teams. Some appear here in print for the first time. This book is the first sustained attempt to combine all the current Dyalog tools into an integrated approach. 

Many of the issues addressed here are entangled with each other. We’ll arrive at our best solutions by way of interim solutions. Proposing some wickedly intricate 'complete solution' framework does little to illuminate the problems it solves. So we'll add features -- INI files, error handling, and so on -- one at a time, and as we go we'll find ourselves revisiting the code that embeds the earlier features. 

If you are an experienced Dyalog developer, you may be able to improve on what is described here. For this reason _The Dyalog Cookbook_ remains for now [an open-source project on GitHub](https://github.com/5jt/dyalog-cookbook). 

Working through book, you get to understand how the implementation issues and the solutions to them work. In Part 1 you will find ‘framework’ code for your application, growing more complex as the book progresses. You can find scripts for these interim versions in the `code` folder on the book website. Watch out: they are interim solutions. You are of course welcome to simply copy and use the last version of the scripts. But there is much to be learned while stumbling. 

Finally in Part 2 we'll introduce some professional writing techniques that might make maintaining your code easier – in what we hope will be a long useful future for it! 


## What you need to use the Dyalog Cookbook

* The Dyalog Version 15.0 Unicode interpreter or later.
* To know how to use namespaces, classes and instances. The utility code in the Cookbook is packaged as namespaces and classes. This is the form in which it is easiest for you to slide the code into your app without name conflicts. We recommend you use classes to organise your own code! But even if you don't, you need to know at least how to use classes. This is a deep subject, but all you need to know is the basics: creating an instance of a class and using its methods and properties, or just using the methods of a static class. See _Dyalog Programmer's Reference Guide_ for an introduction. 

We have not attempted to 'dumb down' our use of the language for readers with less experience. In a some cases we stop to discuss linguistic features; mostly not. If you see an expression you cannot read, a little experimentation and consultation of the reference material should show how it works. We encourage you to take the time to do this. Generally speaking -- not invariably -- short, crisp expressions are less work for you and the interpreter to read. Learn them and prefer them. 


## Acknowledgements

We are deeply grateful for contributions, ideas, comments and outright help from our colleagues, particularly from Gil Athoraya, Morten Kromberg, Nick Nickolov, and Paul Mansour. 

We jealously claim any errors as entirely our own work. 


Stephen Taylor & Kai Jaeger


[^win]: Perhaps one day you would like it to ship on multiple platforms. Perhaps one day we'll write that book too. Meanwhile, Microsoft Windows.
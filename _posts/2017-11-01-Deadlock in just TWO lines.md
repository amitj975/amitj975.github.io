---
layout: post
title: "Deadlock in just TWO lines"
date: 2017-11-01
---

#Deadlock in just TWO lines


This issue took my whole day. I never had an idea, that I would face a [deadlock](https://en.wikipedia.org/wiki/Deadlock) just by two lines of code in my real life coding scenario.

* Var x = async();
* Return X.result;


Now, look at this two lines of code.It seems to be very simple and straightforward right? That okay we are making an async call then we doing .result, to get our data from the async function.
And the funny part was, these lines are working fine in a console application and also when executed from the unit test cases.
But I don’t want any of these; I want to run it from a web application. And there it was halting at the second line. 

Now the research started, I was looking here and there. Not able to figure out what is the cause of the problem? Then in the meantime, I reach out to many people, but oh god, it felt like I was communicating via pigeons.
And finally, I was able to figure out that it is a deadlock issue, thanks to StackOverflow ;). 

You should never mix an async call and sync threads. As the programme executes UI thread come to the first line and made an async call then UI thread resume and start executing the next command; which is X.result but there it first requires x to complete.
Hence UI thread gets stop by this sync operation, and now it has resource X too. On the other side, eventually, the async call will complete and will require X to dump its data. 
But it can't get resource X until UI thread releases it and UI thread won't release X till it can perform X.result which require data that was coming from the async call. 

And hence DEADLOCK.
Solution was pretty easy=>

var result = Task.Run(() => asyncGetValue()).Result;
i.e. Using a sperate thread to get that result.

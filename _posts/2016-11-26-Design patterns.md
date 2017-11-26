---
layout: post
title: "Design patterns"
date: 2017-11-27
---

## Observer pattern
Instead of subject tracking the records of all the observer and making all the changes in code won’t be a good idea.
Subjects can have a list of observers then have a function like add remove and send the notification.

## Decorator pattern 
You’ll learn how to decorate your classes at runtime using a form of object composition.
You have a lot of topping for coffee. Now, you should have a topping which will extend the coffee class, and these topping will be extended by each topping. Now, these toppings are of coffee type only and have coffee object in it. Decorators are meant to add behavior to the object they wrap. When you need to peek at multiple layers into the decorator chain.

## Factory pattern
You’ll learn that instantiation is an activity that shouldn’t always be done in public and can often lead to coupling problems. And you don’t want that, do you? Find out how Factory Patterns can help save you from embarrassing dependencies. 
Ordering pizza function has to first decide the pizza then it is a very straightforward process like bake, cut and box.
Create pizza factory which will take the type of input and return pizza. Now many classes can inherit the pizza factory and new york and Chicago both will interpret cheese differently.
The Dependency Inversion Principle makes an even stronger statement about abstraction. It suggests that our high-level components should not depend on our low-level components; rather, they should both depend on abstractions.   

## Singleton Pattern:
Private constructor so that no one can initiate an object of it. And a static method which returns an instance of this class. Now the whole project will use this instance. Be careful when you are handling with the different thread which might create two objects if you are creating instance reactively.

## Command pattern:   
The Command Pattern allows you to decouple the requester of an action from the object that performs the action. So, here the requester would be the remote control and the object that acts would be an instance of one of your vendor classes.
The lightopen and GarageOpenDoor command will be used. OnCommand can have a light on and Off command can light off. And pressing each button it will execute the command.Execute() function.No command will use to initialize the remote if no command is provided.

Now, instead of creating LightOnCommand and LightOffCommand objects to pass to remoteControl.setCommand(),
we simply pass a lambda expression in place of each object, with the code from their respective execute() methods:

remotecontrol.setcommand(0, () -> {livingRoomOn();},() -> {livingRoomOff();})

Setcommand (int slot, command Oncommand, command Offcommand){
Oncommand[slot] =oncommand;
OffCommand[slot] =offcommand;
}
Or 
Command lighton = ()=> {lighton();}

The command that’s in slot 0 is a function object (created by the lambda expression). When we call execute() on the command, that method is matched up with the method defined by the
lambda expression, which is then executed.


## The Adapter and Facade pattern:
We will design a turkeyAdapter which will implement duck interface and have a turkey object. In this to make turkey fly, we will call turkey.Fly() 5 times in turkeyAdapter to make it like a duck.
Facades don’t “encapsulate” the subsystem classes; they merely provide a simplified interface to their functionality. The subsystem classes remain available for direct use by clients that need to use more specific interfaces. This is a nice property of the Facade Pattern: it provides a simplified interface while still exposing the full functionality of the system to those who may need it.

## Template pattern:
It is more like creating an abstract class for both coffee and tea.

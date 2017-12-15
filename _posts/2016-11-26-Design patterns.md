---
layout: post
title: "Design patterns"
date: 2017-11-27
---

## Observer pattern
>[![Observer](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8d/Observer.svg/500px-Observer.svg.png "Observer")](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8d/Observer.svg/500px-Observer.svg.png)  
*Let's say you want to build a system where there is N number of observers, who wants an update, whenever there is a change in state of the subject. All observer want to get the notifications as well as they can register and un-register from this service effortlessly. 
To do that job, there is a famous design pattern, in which, the subject can have [HAS-A](https://en.wikipedia.org/wiki/Has-a) relationship with the list of observers, and have functions like register and notifyObserver.
Now, every observer will inherit the Observer interface and then can register or unregister itself by calling function of the subject class. And, to notify all the observer, the subject just have to call notifyObserver which will iterate through all the observer list, and call notifies function which they have inherited from the observer interface.*


## Decorator pattern 
>[![decorator.gif](http://www.dofactory.com/images/diagrams/net/decorator.gif "Decorator")](http://www.dofactory.com/images/diagrams/net/decorator.gif)  
*You have a coffee shop(Component), and you want to have a function in you coffee class which will give you the price(Operation) of that coffee.
You sell different type of coffee with various toppings. Sometimes a combination of many topping. It will be a headache for you if you create classes for each combination. 
Decorator pattern is here for you!!
Assume you need to add a cream topping in cappuccino. Now you know the resultant thing will be a coffee again right. First, we create cappuccino class(ConcreteComponent) which inherit coffee class(component). Now we will add topping(ConreteDecoratorB) by making an object of it and pass the cappuccino class object in the constructor. As decorator has HAS-A relationship with Component. Now when you call price(operation) function, it will first call operation function of base price plus topping price(addedBehavior).*


## Factory pattern
>[![factory.gif](http://www.dofactory.com/images/diagrams/net/factory.gif "Factory")](http://www.dofactory.com/images/diagrams/net/factory.gif)  
*Now, Your coffee business is running great as you were using excellent decorator pattern and now you decide to open a pizza shop. 
Here the requirement is bit different, as here you need to bake a different type of pizza and then you need to perform various operation on it like cutting, packing and delivering to address.
Indeed, you don't want to do all this thing by just one class, as we all follow the [god rule for classes](https://en.wikipedia.org/wiki/Single_responsibility_principle). Here, we assign the task of pizza creation to a factory method, which will create your pizza(Product) based on the specification. And then we operate it in creator class. As, It suggests that our high-level components should not depend on our low-level elements; instead, they should both depend on abstractions.*


## Singleton Pattern:
>[![Singleton_pattern](https://www.tutorialspoint.com/design_pattern/images/singleton_pattern_uml_diagram.jpg "Singleton_pattern")](https://www.tutorialspoint.com/design_pattern/images/singleton_pattern_uml_diagram.jpg)  
*Every project uses database right! We make so many calls, and we keep on updating the database. We don't want that our database runs into concurrency issues. So we decide that database class should have only one object. Now, you can restrict someone from creating an object of a class. What if we make it constructor private ;). You heard me! We will make the class constructor private so that no one can create an object of this class except itself. We will create an object of this class and make that private too. And have a public static function to get an instance. Whoever needed will call this function to get the _loneInstance of the class. Cool right!*



## Command pattern:  
>[![Command.gif](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Command_pattern.svg/700px-Command_pattern.svg.png "Command")](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Command_pattern.svg/700px-Command_pattern.svg.png)  
*The Command Pattern allows you to decouple the requester of an action from the object that acts. 
Let's say your team building [FIFA](https://www.easports.com/fifa). You got a most important command to implement that is Shoot(execute). Now your [controller](https://compass-ssl.xbox.com/assets/d3/d8/d3d83d26-d0df-49b8-9ad2-f213425a091d.jpg?n=X1-Wireless-Controller-Black_Gallery_1056x594_02.jpg) doesn't need to know that whether you are operating Messi or Ronaldo. When user press shoot, we got to shoot with player's(state) precision and speed. Here all player will inherit the player class(Command). Once shoot(execute) command comes, we will shoot by player's skill set(receiver.action).*


## The Adapter pattern:
>[![Adapter](http://www.dofactory.com/images/diagrams/net/adapter.gif "Adapter")](http://www.dofactory.com/images/diagrams/net/adapter.gif)  
*Let's say your PM gives you a weird task. In your project, you have a bird class(target) and a turkey class(Adaptee). Now, we all know how turkey fly. Your pm is asking to perform all the task on the turkey class that you were performing on bird class. Here comes the need for an adapter, it will inherit the target interface. So this adapter class(Flying turkey) will be a bird as it is inheriting the target interface. But still, it will be a turkey. Now when someone the fly function(Request) of this bird object, we will call flap(Specificrequest) function five times of turkey class to give an effect like flying.*
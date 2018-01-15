---
layout: post
title: "Power of Actor model with Service fabric"
date: 2018-01-14
---
## Power of Actor model with Service fabric
[![profile.gif](/res/profile.gif)](res/profile.gif)  
>“In Actor model, Actors are the basic computation unit and they can interact with each other through messages. You can think an actor as a class containing receive and send message functions, and they can have their own private state and functions. Based on these they can take some action, send messages, or create more actors.”

Now a little bit of Azure Service Fabric:

[![service-fabric-overview.png](https://docs.microsoft.com/en-us/azure/service-fabric/media/service-fabric-overview/service-fabric-overview.png)](https://docs.microsoft.com/en-us/azure/service-fabric/media/service-fabric-overview/service-fabric-overview.png)  

>“Service fabric is a lightweight platform that helps you build application composed of micro-services. It is an abstraction layer over infrastructure which enables you to build and manage scalable and reliable applications. It has upgrade and fault domain to have a seamless experience of upgrading the application without affecting the customer experience and fault domain ensures the reliability of the application.”

Now try to think of **Architecture of Twitter**, I also don’t know how they have implemented it ;). Implementing Twitter is a big problem to solve in this post, we will do it on some other day. Right now, we just going to look at the advantages of using actor model with fabric service. We will be focusing on a very generic solution for generating news-feed in twitter.

Every actor is composed of two things; one is Actor Type and other is Actor ID. In this feature, one actor type will be User profile and its Id will be unique user Id. It will have all user tweets and information about the user. Another actor type will be for Generating news-feed.

Now, generate news feed will be an actor and its work will be getting back the new feed to the user actor. We will take Actor Id as new guid because a user can use multiple platforms at the same time. If we would have taken the Actor ID a user-specific, then every time generate news-feed request will go the same actor and can lead to delay.

Now you can feel the power of service fabric and actor model. As every second we are getting millions of requests to generate news-feed and if we would have created a simple micro-services for that feature. Billion users request would have been going to the same micro-service and if something breaks the whole news-feed feature will go down for all the users.

*Whereas in this, you know that every news-feed request is handled by new actor and reliability of each actor are in the good hands of service fabric.*

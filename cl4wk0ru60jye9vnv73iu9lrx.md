---
title: "What i learned from 1st Eazy Hack challenge"
seoTitle: "code engine using redis pubSub and node.js"
datePublished: Mon Jun 27 2022 09:45:21 GMT+0000 (Coordinated Universal Time)
cuid: cl4wk0ru60jye9vnv73iu9lrx
slug: what-i-learned-from-1st-eazy-hack-challenge
tags: redis, nodejs, pubsub

---

Hello All

In this blog i am going to discuss about the first challenge which consist of building a cli tool using redis pubSub pattern. Which is a fantastic way to learn new things on go and also to build some mini projects regarding the topic. So this weeks topic was Redis PubSub pattern you can find the [link here](https://www.linkedin.com/pulse/redis-beyond-caching-1-pubsub-eazyhack-swags-shrey-batra/?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_post_details%3BmMk22E5iQKq8fGQ2t21big%3D%3D) thanks for [Shrey Batra](https://www.linkedin.com/in/shreybatra/) for creating such challenges.

So firstly Redis is open source, in memory data store used as a database,cache and many more things. 

It's basically a key-value based database so we can use GET and SET methods to retrieve and store values in redis database. We can learn many more things in official [redis docs to know more.](https://github.com/redis/node-redis) but in this blog we are mainly going to discuss about the PubSub Pattern as it is the main part of the challenge.

So Redis PubSub stands for Publisher Subscriber it is a messaging pattern where different services can publish and subscribe as well to send data to each other in a reliable and efficient way.

Basically a Publisher publishes a message and a subscriber subscribes to publisher to recieve the messages from the message broker(here message broker is redis).

You can think of message broker as middleman which does all the heavy lifting like  handles all the routing of all messages from publisher to each connected subscriber.

Pub Sub pattern has a lot of applications like remote code engines, group chatting systems,zoom apps,notification based systems.


Aside from redis we have alternatives to redis that implement pub/sub pattern these are as follows:-

1. [Apache kafka](https://kafka.apache.org/)

2. [Rabbit MQ](https://www.rabbitmq.com/)

3. [Google PubSub](https://cloud.google.com/pubsub/)

Thanks for reading 😊😊😊.

Follow for more such content [@Siddharth9890](https://www.linkedin.com/in/siddharth-singh-563824202/).


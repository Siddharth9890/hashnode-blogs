---
title: "Introduction to MongoDb aggregations and Eazy develop challenge 2"
seoTitle: "Introduction to MongoDb aggregation"
datePublished: Mon Jul 04 2022 09:25:26 GMT+0000 (Coordinated Universal Time)
cuid: cl56je4g604tyg0nvfxdkhm4j
slug: introduction-to-mongodb-aggregations-and-eazy-develop-challenge-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1656909323748/-xykRJ7_d.png
tags: charts, javascript, mongodb, aggregation, pipeline

---

Hello All

In this blog i am going to discuss about the second challenge which consist of building MongoDB Charts using sample data and what i personally learned from it. So this weeks topic was [MongoDb aggregations](https://www.linkedin.com/pulse/mongodb-more-than-crud-introduction-aggregations-eazyhack-batra?trk=public_profile_article_view) thanks for [Shrey Batra](https://www.linkedin.com/in/shreybatra/) for creating such challenges.


**So what is aggregation?**

Aggregation is a way of processing a large number of documents in a collection by means of passing them through different stages. The stages make up what is known as a pipeline. The stages in a pipeline can filter, sort, group, reshape and modify documents that pass through the pipeline. It is similar to the basic aggregation available in SQL with the GROUP BY clause and COUNT, SUM and AVG functions. 

**How does the pipeline works?**

The input of the pipeline can be a single collection.The pipeline then performs successive transformations on the data until our goal is achieved.This way, we can break down a complex query into easier stages, in each of which we complete a different operation on the data. So, by the end of the query pipeline, we will have achieved all that we wanted. 
Or you can consider that we are passing the collection through various functions and each function will do some operations and give the result to next function.Hence it allows to check whether each function is working or not properly at every stage by checking it's input and output.


**Some of common pipeline stages are as follows**

[$match](https://www.mongodb.com/docs/manual/reference/operator/aggregation/match/)

[$count](https://www.mongodb.com/docs/manual/reference/operator/aggregation/count/)

[$group](https://www.mongodb.com/docs/manual/reference/operator/aggregation/group/)

[$limit](https://www.mongodb.com/docs/manual/reference/operator/aggregation/limit/)

[$sort](https://www.mongodb.com/docs/manual/reference/operator/aggregation/sort/)

[$unwind](https://www.mongodb.com/docs/manual/reference/operator/aggregation/unwind/)

[More are available here](https://www.mongodb.com/docs/manual/reference/operator/aggregation-pipeline/)


**Personal Learning's**

So this was the first time i was introduced to mongodb's aggregation pipeline and it was hard to understand at first what is going on. But seeing various examples,reading blog posts and some videos solved the problem quickly and the most important part was to actually create charts based on sample data.

Another problem was that in the data set that i used which was analytics data set it has a customers collection where it had basic customer info like name,address but also has the account tier and whether the account is active or not in a object with random id's i have attached a screenshot to understand it in a better way.


![Screenshot (8).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1656925791000/_-WQ7YMhl.png align="left")

So we can't use . operator as the id's are random hence it was way tough initially to access the details but later after googling and searching for it i found that we can use [$objectToArray](https://www.mongodb.com/docs/manual/reference/operator/aggregation/objectToArray/) to convert it into key value and then we can use $unwind to use the data .

So two major out comings of this challenge was i learned about mongodb aggregation and various stages in it(though a lot more practice is needed) and you also need to improve your googling skills as well.

Thanks for reading 😊😊😊.

Follow for more such content [@Siddharth9890](https://www.linkedin.com/in/siddharth-singh-563824202/).
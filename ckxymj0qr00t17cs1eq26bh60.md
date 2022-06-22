## Architecture of our web app CS-TRACKER

So recently we launched a group project which tracks your data structures and algorithms problems i.e you solve data structures and algorithms problems on leetcode along with videos for your help if you could not solve it + revision on questions using dates  [link of the website ](https://cs-tracker.pages.dev/) . We made this project using react ,tailwind css on frontend and nodejs for backend and mongodb for storing the data.If you want to look at the source code  [click here](https://github.com/Siddharth9890/cs-tracker-fontend) and for backend  [click here](https://github.com/Siddharth9890/cs-tracker-backend).

So in this blog we are going to talk about the general structure of app.

So first we have subjects like java,Data structures and algorithms, web development etc. It's the main start of the app.

Then we have the topic which is based on the subject you choose so for e.x:- if you choose Data structures and algorithms then we will show you all the topics under it like here it will be linked list,binary tree,arrays, strings and so on. So topics is based on subject i.e one-to-many mapping .

Then we have questions for that topics for e.x:- if you choose linked list then we will show you all the questions under the topic like reverse linked list, is cycle, is linked list palindrome and so on. So here also there is one-to-many mapping between the topics and subjects.

And finally we have a single question page structure where we show you the questions details also if you have submitted the question we will also show you your last completed date and revision date if you have set it. We have also provided you solution video and the leetcode link to solve the question.

Let's talk about our main feature of the app i.e revision tab. So if you select a revision date for a question while solving the question you feel like you need to do the question again to better grasp it and to do a revision of it for interview. Then when you go to the revision tab. There you will see all the questions where you have selected the revision date.

We will sort all questions based on nearest revision date and will show you in a neat format you can select any of the question and hit on click to revise button to revise it!
So that you don't need to remember which question to solve on which day our app will take care of it.

So hope you liked our app😊😊. If so thanks for your feedback.

If you feel there is any bugs or any security issues or any suggestion to help the app feel free to let us know you can contact any of us via email or can issue a request in github also.Since this is our first project we really don't know about any minor bugs that it has we have tried our best to resolve any bugs.
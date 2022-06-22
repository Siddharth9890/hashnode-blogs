## Coding Machine a online editor to write programs and to run it part 2.Let's discuss about problems and architecture of the app

So hello everyone 👋👋. Lets discuss about my project [coding-machine](https://coding-machine.pages.dev/) we have discussed about the [frontend](https://theuniquecoder.hashnode.dev/coding-machine-a-online-editor-to-write-programs-and-to-run-it-part-1) in part 1 if you have missed it i would highly prefer you to read it first before starting this one. So let's start with the backend and the problems now.

So first of all while making the online editor the problems are really important and should be taken into consideration before coding because it would help to take the right part. So there are 3 major problems that if feel:-
1. So the user could type code like time.sleep(1000) for example and it would hang the code execution engine and would not able to server rest of the clients still the code is not executed.

2. The user could try to access the file system and could try to delete the files of the server and hence the server can stop and cannot process the rest of the code executions.

3. Another problem is that user could write a program which could spawn multiple child process and could slow down the code execution engine.

So to solve all the problems the solution is to use docker which can help us to set hard limit on the number of process, set the ram, set the cpu, and the storage as well in advance. 

So with the help of docker we can also restart the server so if the server crashes we can easily restart it and all the files will be safe in place!. 

If you feel there are any problems or bugs that could occur please feel free to reach me and we can address it as well. Since i am a beginner there might be some bugs that i could not think of as of now😊.

Now as we have addressed all the major problems let's get back to coding on how i have designed the backend to try to protect from the above problems and to simplify the designing of the app as well. So let's start that 👋👋.

So let's start with designing of the app so we will having two servers one will be simple rest api server and other one will be the actual code execution engine which will do the hard work.


![Untitled Diagram.drawio(1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1649678935616/2T7Pm3AKw.png)


So as shown in diagram we have a simple rest api which the client talks to 
and then the rest api will add the request to queue we are using cloud amqp as it has a free tier available to help us to launch the queue. Then we have database you can take sql database as well but for simplicity i have taken mongodb to store all the codes and some metadata as well. And finally we have workers which will take one item from the queue and process it and then after processing it will update the result in database as well.

As you can see i have tried to simplify the whole architecture of the app in form of micro services and hence each service can scale easily and the whole code is decoupled as well. 

So in the [next blog](https://theuniquecoder.hashnode.dev/coding-machine-a-online-editor-to-write-programs-and-to-run-it-part-3lets-discuss-about-simple-rest-api-and-worker-code) we will discuss about the simple rest api and worker.

And the whole frontend code is available [here](https://github.com/Siddharth9890/coding-machine-frontend)

And the whole backend code is available [here](https://github.com/Siddharth9890/coding-machine-api)


Thanks for reading 🙂😉😊.








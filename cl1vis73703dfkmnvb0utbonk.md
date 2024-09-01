---
title: "Coding Machine a online editor to write programs and to run it part 3.Let's discuss about simple rest api and worker code"
seoTitle: "code engine, remote-code-execution, mern, coding-machine,ide"
datePublished: Tue Apr 12 2022 02:23:48 GMT+0000 (Coordinated Universal Time)
cuid: cl1vis73703dfkmnvb0utbonk
slug: coding-machine-a-online-editor-to-write-programs-and-to-run-it-part-3lets-discuss-about-simple-rest-api-and-worker-code
tags: ides, nodejs, backend, reactjs, mern

---

So hello everyone 👋👋. Lets discuss about my project [coding-machine](https://coding-machine.pages.dev/) we have discussed about the [problems and architecture](https://theuniquecoder.hashnode.dev/coding-machine-a-online-editor-to-write-programs-and-to-run-it-part-2lets-discuss-about-problems-and-architecture-of-the-app) in part 2 if you have missed it i would highly prefer you to read it first before starting this one. So let's start with the simple rest api and worker code.

So the rest api has 3 end points 

1. /submit

2. /check-status

3. /result 

So submit is a post endpoint which submits your code and selected language we simply store it in database and the unique id that we get back we store in the rabbit mq queue and we return the same id back to the user.

Then we have /check-status/id endpoint which will take the id and check after every 0.5 seconds about the status of the code in server whether the code is processing or completed if it is processing we still check again until it is done. 

And finally we have /result/id which will return you the output of code if any errors and some metadata like how much time taken and the file name. 

So there might be doubt regarding why /result endpoint as a seperate end point it is just to simplify the code and to keep it clean.
 
So that's it about the rest api Now let's move towards the worker code.

So worker does not exposes any end point instead it is connected to same queue as the rest api is connected so hence if there are any jobs present in the queue then worker will automatically fetch the job and then fetch the code details from the database and will execute the code and then will store the result i.e it can be output like Hello World or some error.

Note that to simplify the worker process the SYSTEM AUTOMATICALLY TERMINATES PROCESS RUNNING LONGER THAN 5 SECONDS that's by default so to save the rescources of the code execution worker.

We basically create a new file and copy the code in it and then we execute it so for that we need python,c++,java installed in the server. 

Note for java we always create Main.java and then we execute it we will add the logic to do anyClass.java in further update. 

That's it for this project if you find any bugs or any improvements to the system please feel free to contact me anytime!. 

And the whole frontend code is available [here](https://github.com/Siddharth9890/coding-machine-frontend)

And the whole backend code is available [here](https://github.com/Siddharth9890/coding-machine-api)


Thanks for reading 🙂😉😊.


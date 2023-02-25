# A Tale of Debugging: Debugging Chrome extension.

Hello everyone.

Today i share a very interesting problem that i personally faced during my internship time. Which really helped me to think about the solutions and to come up with best possible solutions.

# Problem statement

So during my internship, we were told to build a Chrome extension in which anytime the user downloads any image, let's say from Unsplash, we would get the same file and save it to our application using the Chrome extension. As always, there was code written to allow the user to "whitelist" (allow downloads from websites that the user wishes) and we were specifically looking for images as that was our main requirement.

So to implement, it as always, we read the Google documentation and I found out that Chrome API allows a [download listener](https://developer.chrome.com/docs/extensions/reference/downloads/#type-DownloadItem) which allows us to get the download information, the download link, and much more. So we used that to get the download link and send it to our servers. Our servers would then perform some async tasks using a queue in order to retrieve those images and upload it to S3.

But when we started testing it, we found out that we were getting the same link more than twice on our servers, and thus we have the same image duplicated more than twice. The exact number is not known but it could go as high as 6 times, so you can see the problem if I download one image and we are storing it 6 times(worst case). The exact reason is unknown, but while discussing it with my manager, we speculated that Chrome would download the image in various parts and then merge the file; it was the best reason we could think of, and it makes sense if we have a large file; downloading it in parts also makes sense if we have a large file. So let the debugging process start!

![](https://media.giphy.com/media/5zf2M4HgjjWszLd4a5/giphy.gif align="center")

# Finding the solution

So for the solution part, we know that Chrome is sending the link to us many times, and we can't store the image more than once for one user. So we started Googling how to prevent such cases, but unfortunately we were unable to find a proper solution.To be honest, finding extension code is a difficult task because almost everywhere the code is written using AJAX or follows Chrome Manifest Version 2, which is outdated and should not be used according to the [official documentations.](https://developer.chrome.com/docs/extensions/mv3/mv2-sunset/)

So, instead of letting Chrome send us the link multiple times, we thought, why not store it in [chrome extension storage](https://developer.chrome.com/docs/extensions/reference/storage/) and treat it like browser local storage? Sure, we can do it like this: store the user id and the link in browser local storage and check if they are the same link, then don't send the request to servers. We did the coding part as well but guess what it didn't work.

So, during testing, we discovered that the storage Chrome API is mostly an asynchronous task that takes time, be it less than 1 ms. In our case, as soon as we get the first link and store it in browser storage, the links are duplicated in our Backend servers.It was almost as if we were receiving the links on the Backend while Chrome was actually storing the data.

# The best solution is to use database index

![](https://media.giphy.com/media/Jt4sQOFEh29Ob8KAxg/giphy.gif align="center")

So then we were disappointed a lot, all the things we tried did not worked then for next 2-3 days, we started to discuss a lot on how to solve this problem so my friend actually suggested that rather than focusing on frontend i.e the extension why not we try to implement a solution in backend and deploy it to the servers any which ways we can't control the extension too much the API provided are great but the problem is everything is asynchronous so that was great idea so the next immediate idea was to create a hash using the link and the user id we can go with easiest hashing algorithm as we want speed nothing else and we used that hash as a unique key in our database and also modified the code a lot i.e whenever we get the link we first create the hash and try to store it in database if it succeeds we have a valid image if it fails i.e throws error then we know it is duplicated image. And when we tested it, it worked, finally 🥳🥳. We tested it several times, and we won!

![](https://media.giphy.com/media/a0h7sAqON67nO/giphy.gif align="center")

And finally this was a wrap I got to learn a lot by solving this bug and I was proud of myself solving something very interesting. So if you guys have any doubts or any suggestion please let me know in comments.

Thank You!
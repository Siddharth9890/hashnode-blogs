## Changes made in CS-Tracker and upgrade in tech-stack.

Hello everyone👋.

In today's blog we are going to discuss all changes that we made in [cs-tracker](https://cs-tracker.vercel.app/) and why we choose typescript,redux,Next.js,Sql server as the tech stack. So let's begin.

Why did we choose to upgrade to typescript?
So the simple answer is to improve code readability and understanding how the code works and also to reduce lot's of bugs like undefined is passed during runtime such awesome features comes with a typed system only hence typescript is used over plain javascript.

Why did we choose to go with Next.js over react?
As we all know Next.js has a lot's of features like [Pre-rendering](https://nextjs.org/docs/basic-features/pages) to improve performance and seo as well main goal of Next.js is to generate HTML files which can improve performance as each and every browser runs/render HTML much faster than javascript.

Also all the images used in Next.js with [Next/Image](https://nextjs.org/docs/basic-features/image-optimization) provides various image optimization features like image resizing converting jpg/png images to webp format and also reduces the size of image from megabytes to kilobytes.

Plus as a added bonus Next.js has in build page routing we don't need to add react-router as we do in react. It reduces code boilerplate and also allows more code segeration.

Why did we choose to go with Sql server over NoSql?
The only logical reason to move to sql server is that all  logical models used have more logical relation which can be elaborated and maintained in a sql server rather than using a noSql server and also main part to shift was to learn how to use node.js with sql server using a ORM like sequelize.

**
All the changes made are as follows**:-
**
Changes regarding Authentication Service:-**

1. Improved Authentication Service by implementing password less login/register service.

2. Improved user persistence once user has logged in by using axios interceptors.

3. Now user/developer cannot access react dev tools/ redux dev tools as it is disabled in production.

4. Added compulsory  2 Factor authentication for everyone to prevent unauthorized access to service.

5. Added hcaptcha service to prevent bots from spamming the service.

6. As there are no passwords to manage backend processing is faster has we are not encrypting or decrypting passwords any more.

7. We are now using access tokens and refresh tokens to manage whether user is valid or not.

**Changes regarding Question Page:-**

1. Added a custom notes taking editor so that users can write some notes to remember the question.

2. Change the whole question page layout for better readability.

3. Moved the revision date to a new modal so that the website remains responsive.

4. Loads latest notes written by user when the user revisits the question.

**Rest minor changes:-**

1. Improved profile page readability.

2. Minor layout changes in home,topics,questions pages.

Thanks for reading 😊😊😊.

Follow for more such content [@Siddharth9890](https://www.linkedin.com/in/siddharth-singh-563824202/).

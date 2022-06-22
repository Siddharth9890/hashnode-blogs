## A Complete List of Packages Used in CS Tracker App

Hello everyone👋.

Today i am exciting to announce that we have done a lot of changes to [cs-tracker](https://cs-tracker.vercel.app/) website. You can see the changes made [in this blog](Link). So in today's blog we are going to discuss the list of packages used to make the cs-tracker website we are going to discuss frontend as well as backend packages used and their usage in the app so let's get started.

All the packages are available on npmjs website as well

List of frontend packages:-

1. @fvilers/disable-react-devtools:- To the React Developer Tools addon to access your application so that the components in react devloper tools are disabled and can't be accessed in production.

2. @hcaptcha/react-hcaptcha:- To prevent bots from accessing the website. 

3. axios:- To make promise based requests to backend app. Along with interceptors.

4. next:- React Framework. 

5. qrcode.react:- Used to display qr code for 2 factor authentication.

6 . react:- JavaScript library for building user interfaces.

7. react-calendar:- Used to display calendar with advance features like custom date selection and much more.

8. react-dom:- React package for working with the DOM.

9. react-redux: To use redux in react it has official bindings.

10. react-spinners:- Standard loading spinner used in app comes from this package.

11. react-toastify:- To notify the user about messages like any errors.

12. react-trix-rte:- React wrapper for Trix rich text editor.

13. redux:- Used to create state and pass the state throughout the app without need of props.

14. redux-devtools-extension:- Wrappers for Redux DevTools Extension to analyze the store created by redux during development.

15. redux-thunk: Thunk middleware for Redux.

16. store2: Better localStorage for storing some metadata about user state.

17. @headlessui/react:- So all the modals,transitions comes from headless ui.

18. @heroicons/react:- Icon pack used in website.

19. @reduxjs/toolkit:- The official, opinionated, batteries-included toolset for efficient Redux development.

20. @tailwindcss/forms:- A plugin that provides a basic reset for form styles that makes form elements easy to override with utilities.

Rest packages are all dev dependencies which are mainly required during development like typescript, @types/node and much more which you can find in [source code](https://github.com/Siddharth9890/cs-tracker-fontend).


List of backend packages:-

1. express:- Web framework to make Rest api's.

2. express-rate-limit:- Use to limit public rest api endpoints by using middlewares.

3. helmet:- help secure Express/Connect apps with various HTTP headers.

4. dotenv:- Load all the environment variables from .env file.

5. cors:- To configure cors options for node.js like origin and methods to be accessed.

6. cookie-parser:- Parse HTTP request cookies which is send by axios interceptor.

7. jsonwebtoken:- JSON Web Token implementation for creating jwt for user auth.

8. nanoid:- Create backup code and otp's for account management better than UUID.

9. node-mailjet:- Mailjet node.js service is used to send mails to new user's account creation. 

10. pg:- PostgreSQL client to do postgres database connections and manage database.   

11.  sequelize:-It is a promise-based Node.js ORM tool.

12. speakeasy:- Two-factor authentication for Node.js.

13. validator:- String validation and sanitization.

14. xss-clean:- middleware to sanitize user input.

15. zod:- Custom middleware to sanitize input.

So these are all the packages we mainly use to make full stack web application like cs-tracker.

Thanks for reading 😊😊😊.

Follow for more such content [@Siddharth9890](https://www.linkedin.com/in/siddharth-singh-563824202/).




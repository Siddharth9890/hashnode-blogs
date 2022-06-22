## Why we shifted from cloudflare pages to vercel for our website cs-tracker

So our website [cs-tracker](https://cs-tracker.vercel.app/) which was initially made using react was hosted on cloudflare pages. It was working perfectly fine. But from last month we started to restructure the whole codebase and rebuild the website using typescript,redux and Next.js as frontend tech stack(I write a seperate blog regarding why we choose the tech stack and working in detail). We did build the website but the problem was in hosting part. 

As of today (20-June-2022) cloudflare pages does support Next.js  deployment but the catch is it does **Next.js Static Html export ** which means it uses next export to deploy the app i.e it only allows you to export your Next.js application to static HTML, which can be run standalone without the need of a Node.js server. In short it is good if the website you are deploying does not have dynamic content. 

![Screenshot (33).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1655727583031/itKksDaaP.png align="left")


But our website has a lot of dynamic content like questions which keep getting added, same for topics and subjects hence it cannot work in cloudflare pages it will **show a 404 error and will not load even if fallback is set to true as it is using next export **.

I will attach the official documentation as well where you can read more.

Hence we moved our hosting from cloudlfare pages to vercel.

If there is any update i update this blog as well.

Thanks for reading 😊😊😊.

Follow for more such content [@Siddharth9890](https://www.linkedin.com/in/siddharth-singh-563824202/)

Official Docs regarding [static html export](https://nextjs.org/docs/advanced-features/static-html-export)
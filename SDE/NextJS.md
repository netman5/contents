# [[NextJS]] Tutorial

## What is NextJS?
- Is a React Framework for Production according to the NextJS website
- A full stack framework for React
	- React is a JS library for building complex User Interface
	- A Library one can add to JavaScript project 


### [[React]] VS NextJS
- To build a bigger app in React that has multi-pages other libraries such as React-Router Dom is required
- NextJS Framework instead is bigger and has more features than a Library that focuses on more thing that just a User Interface and gives clear rules & guidance on how to write code, structure your application files
- It makes building large scale React App easier
- NextJS is build on React, uses React features such as components, props, state and context, basically you'll still write React code, build components etc.
- NextJS solves common problems and makes building React App easier
	- Has a lot of built-in features such as routing

### NextJS - Key Features: Core
- Server-side rendering
	- Preparing the content of the website on the server instead from the client
	- Automatic page pre-rendering: Great for SEO and initial Load
	- Blending client-side & server-side: Fetch data on the server & render finished pages
- File-based Routing
	- In traditional React app you don't have a router
	- Get rid of in code route definitions i.e No need to write any code for routing or install any package
	- It defines pages & routes with files and folders
	- Less code, less work
	- folders that you created in pages in pages folder also act as path
	- It advisable to user nested folder if we're creating a nested routes
	- for adding dynamic pages in nextjs we use [].js for different values in app path
	- The above tells NextJS that the page will be loaded for different values
	- Use useRouter from nextjs router to get the params of page for fetching 
- Full Stack Capabilities
	- Allow us to write backend code for our app using NodeJS
	- Storing data, getting data, authentication etc.
- Requirements to run & start using NextJS
	- NodeJS
- Then run 
	`npx create-next-app@latest`
- Follow the prompt by pressing y & give the project name
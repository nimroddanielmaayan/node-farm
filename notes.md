# Node Farm - a Basic Node.js Practice Project

> This project is part of Jonas Schmedtmann's node.js course on Udemy

<!-- Add image later -->
<!-- <img src="./frontend/public/images/screens.png"> -->

## Node.js Basics

### General

- Remember, that it's possible to use the \_\_dirname variable to get the current directory, no matter where the file is located. This can sometimes be better than using relative paths (like ../ or ./)

- I have to get used to console.logging things to the command line console instead of to the browser console

- In node.js, every file is automatically a module

- The nodemon package - remember to use it in every node project

- Reminder: Dev dependencies, which are needed only for development but not for production, should be installed with the --save-dev flag. It makes sense to install all the dev dependencies globally, so that we don't have to install them for every project. To install a package globally, we need to use the -g flag

- Reminder: We can't call dev dependencies directly from the command line. We need to use scripts that we define in the package.json file

- A word about version control: NPM package versions look like this: 1.2.3 with the last being bug fixes, the second being minor updates\feature updates, and the first being major version updates. Note, that only major version updates might break our code, and minor updates are always supposed to be backwards compatible. To make sure that we don't get any breaking changes, we can use the ^ symbol before the version number. This is recommended, and it will make sure that we get all the bug fixes and minor updates, but not the major updates. If we want to get all the updates (at our own risk...), we can use the asterix symbol before the version number, or only bug fixes using the ~ symbol (if we want to be extra careful)

- The npm updated command can list all the packages that have updates available

- More info on node version management: https://www.sitepoint.com/quick-tip-multiple-versions-node-nvm/

- It's technically possible to use JS\node in order to program many things, like robots, IOT devices, desktop applications, etc. Like many programming languages, it can compiled to the native machine code of different platforms

- A web application's back end is usually built of a server and a database. A server usually has 3 components: An HTTP server, an application and files. More information in Jonas's slides

- Almost all modern web applications are "dynamic". This means that they are generated on the server right before they are sent to the client, according to relevant data

- "True full stack" developers are getting more and more rare today. Usually, developers specialize in either front end or back end, though it's always good to understand both

- The concept of SSR: Server Side Rendering happens, for example, in an online store where not all items are in stock. The server will check the stock, then render the page based on a template, and then send the page to the client

- API based web apps\CSR: Client side rendering. A more recent approach\architecture that's made possible by the high capabilities of modern web browsers and FE frameworks. In this approach, the server only sends data to the client and the client renders the page. This is the approach that we usually use in React (with the exception of Next.js SSR). This approach is based on creating, sending and consuming JSON data rather than sending entire web pages

- It's important for a good back end dev to know how to build both APIs and SSRs

- An important note: If we want to build a server that will supply the same data to different types of clients (like a browser and also a native mobile app), we need to build an API, not an SSR, since only browsers can render HTML

- Some companies\people don't even have a front end, and only build APIs in order to sell access to their data to others. This is called a "headless" approach

### Command Prompt

- Node REPL: To enter REPL (Read Evaluate Print Loop), go into the terminal and write "node"

- To exit REPL, press CTRL+D

- Use underscore to access the previous output

- Use TAB to check the available methods. It's also possible to use TAB to check available sub-methods, for example: string.(TAB)

### Modules

- Modules are like libraries. They are pieces of code that we can use in our application. We can use modules that are built-in in node.js or we can use modules that are built by other developers

- Modules in node are similar to modules in frontend

- See later if the require() syntax is the common way for modules, or import

- It's good practice to first import the core modules, then the third party modules, and then our own modules

### How Node.js Works

- Node uses single thread and uses async code to handle multiple requests and balance the load. This is why there are a lot of callbacks in node.js. On the contrary, other server-side languages like PHP use multi-threading - a separate thread for each request\user

- We will almost always use the async version of the node methods, for example: readFile() instead of readFileSync()

### The File System Module

- The file system module is a built-in module in node.js. It allows us to work with the file system on our computer\server, and do things like create, read, update, delete, and rename files

### The HTTP Module

- The first method of the http module is the createServer() method. It takes a callback function as it's single argument. This callback function will be called every time a new request hits the server. The callback function takes two arguments: req and res. req is the request object, and res is the response object

- The node application will not end when an http server is created. It will keep running until we explicitly stop it. To stop the server, we can use CTRL+C. In the background, an endless loop is running, listening for incoming requests

- If possible, it's always better to read data files\template files once, and save them as a variable, outside of the server callback function. This way, the files will be read and stored in the server's memory only once when the server starts, and not every time a request is made

- It's recommended to use synchronous loading at the beginning of the server application (to make sure that all neccessary data is loaded before continuing), and then use asynchronous loading for the rest of the application

### HTML Templating

- It's recommended to use a pattern, like {%VARIABLENAME%} in order to mark variables in the HTML that will later be replaced by real time data from the back end

### Back End Development - Behind the Scenes

- The first file that is sent from the server to the client is the index.html file. The browser then parses the HTML file, and if it finds any links to other files, it sends additional requests to the server for those files. This continues until all the files are sent

- In the dev tools "network" tab, we can see all the requests that were sent to the server, and also see who initiated the request

### Node.js - Behind the Scenes

- The heart of node.js is the event loop. But heavy tasks that might block the main thread (like file system actions, compresion etc.) are automatically offloaded to the thread pool, which by default has 4 threads but can be set to a maximum of 128

- Node is based on "event driven architecture". This means that everything that happens in node is a response to an event, that usually triggers a callback function

- The event loop works in "ticks" or loops. There's a detailed explanation about how a loop happens, in Jonas's slides

- One of the most important things to keep in mind when working with node is that we should never block or slow down the event loop

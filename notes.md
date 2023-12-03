# Node Farm - a basic node.js practice project

> This project is part of Jonas Schmedtmann's node.js course on Udemy

<!-- Add image later -->
<!-- <img src="./frontend/public/images/screens.png"> -->

## Node.js basics

### General

- Remember, that it's possible to use the \_\_dirname variable to get the current directory, no matter where the file is located. This can sometimes be better than using relative paths (like ../ or ./)

### Command prompt

- Node REPL: To enter REPL (Read Evaluate Print Loop), go into the terminal and write "node"

- To exit REPL, press CTRL+D

- Use underscore to access the previous output

- Use TAB to check the available methods. It's also possible to use TAB to check available sub-methods, for example: string.(TAB)

### Modules

- Modules are like libraries. They are pieces of code that we can use in our application. We can use modules that are built-in in node.js or we can use modules that are built by other developers

- Modules in node are similar to modules in frontend

- See later if the require() syntax is the common way for modules, or import

### How node.js works

- Node uses single thread and uses async code to handle multiple requests and balance the load. This is why there are a lot of callbacks in node.js. On the contrary, other server-side languages like PHP use multi-threading - a separate thread for each request\user

- We will almost always use the async version of the node methods, for example: readFile() instead of readFileSync()

### The file system module

- The file system module is a built-in module in node.js. It allows us to work with the file system on our computer\server, and do things like create, read, update, delete, and rename files

### The http module

- The first method of the http module is the createServer() method. It takes a callback function as it's single argument. This callback function will be called every time a new request hits the server. The callback function takes two arguments: req and res. req is the request object, and res is the response object

- The node application will not end when an http server is created. It will keep running until we explicitly stop it. To stop the server, we can use CTRL+C. In the background, an endless loop is running, listening for incoming requests

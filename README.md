# Getting Started with Axios

- Axios is an HTTP client library that allows you to make requests to a given endpoint.
- The API could be any external or your own backend Node.js server.
- It helps us to make requests such as retrieve, create, update, and delete data from API.

## Fetch API Syntax

const baseURL = "mock-api-url";
fetch(baseURL)
.then((res) => {
res.json();
})
.then((data) => {
console.log(data);
});

## Why Use Axios in React

- Five reasons why you should use Axios as your client to make HTTP requests:

1. It has good defaults to work with JSON data. Unlike alternatives such as the Fetch API, you often don't need to set your headers.
2. Axios has function names that match any HTTP methods. To perform a GET request, you use the .get() method.
3. Axios does more with less code. Unlike the Fetch API, you only need one .then() callback to access your requested JSON data.
4. Axios has better error handling. Axios throws 400 and 500 range errors for you. Unlike the Fetch API, where you have to check the status code and throw the error yourself.
5. Axios can be used on the server as well as the client. If you are writing a Node.js application, be aware that Axios can also be used in an environment separate from the browser.

## Set Up Axios with React

> npm install axios

and then import in project:

```
import axios from "axios";
```

## Make a GET Request

- To fetch data or retrieve data, make a GET request.
- Syntax

```
import axios from "axios";

const baseURL = "mock-api-url";

axios.get(baseURL)
.then((response) => {
    console.log(response.data);
});
```

- Note: You can always find the requested data from the .data property in the response.

## Make a POST Request

- To create new data/ add new data/ submit any data, make a POST request.
- Syntax

```
import axios from "axios";

const baseURL = "mock-api-url";

axios.post(baseURL, {
    property: value,
    title: "Hello World!",
    body: "This is a new post"
})
.then((response) => {
    console.log(response.data);
});
```

- To make that POST request with Axios, you use the .post() method. As the second argument, you include an object property that specifies what you want the new post to be.
- then, we use a .then() callback to get back the response data and replace the first post you got with the new post you requested.

## Make a PUT Request

- To update a given resource, make a PUT request.
- Syntax

```
import axios from "axios";

const baseURL = "mock-api-url";

axios.put(baseURL, {
    property: value,
})
.then((res) => {
    console.log(res.data);
});
```

- like the POST method, you include the properties that you want to be in the updated resource.
- you are using the `.then()` callback, to update the JSX with the data that is returned.

## Make a DELETE Request

- Finally, to delete a resource, use the DELETE method.
- Syntax

```
import axios from "axios";

const baseURL = "mock-api-url";

axios.delete(baseURL)
.then(() => {
    alert("Data deleted!");
    console.log(null);
});
```

- In most cases, you do not need the data that's returned from the .delete() method but .then() callback is still used to ensure that your request is successfully resolved.

## Handle Error with Axios

- Syntax

```
import React from "react";
import axios from "axios";

const baseURL = "mock-api-url";

function App() {
axios.get(baseURL)
.then((res) => {
    console.log(res.data);
})
.catch(err => {
    console.error(err);
});

    return();
};

export default App;
```

## Create an Axios Instance

- If you look at the previous examples, you'll see that there's a baseURL that you use as part of the endpoint for Axios to perform these requests.
- However, it gets a bit tedious to keep writing that baseURL for every single request. Couldn't you just have Axios remember what baseURL you're using, since it always involves a similar endpoint?
- In fact, you can. If you create an instance with the .create() method, Axios will remember that baseURL, plus other values you might want to specify for every request, including headers:

```
const client = axios.create({
    baseURL = "mock-api-url";
});

client.get()
.then((res) => {
    console.log(res.data);
});
```

- Thus, in the future, you can use all the same methods as you did before, but you don't have to include the baseURL as the first argument anymore. You just have to reference the specific route you want, for example, /, /1, and so on.

## Use the Async-Await Syntax with Axios

- Async-Await is used to handle promises in JavaScript.
- Async makes a function return a Promise, Await makes a function wait for a Promise.
- Async-Await allows you to write much cleaner code without `then` and `catch` callback functions.
- The await keyword can only be used inside an async function.
- The await keyword makes the function pause the execution and wait for a resolved promise before it continues.
- Syntax

```

```

## Create a Custom useAxios Hook

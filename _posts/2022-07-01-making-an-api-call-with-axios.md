---
layout: post
title: Making an GET Call with Axios
summary: A quick introduction to Axios and making a get request.
categories: jekyll update
---

Axios is a promise-based HTTP client that is used to make HTTP requests. It is a powerful tool and has some advantages over similar tools such as Fetch API such as the ability for request and response interception and streamlined error handling. In this blog post I will explain how to make an GET request using Axios.

The first step will be to make Axios available to the code. this is done using the require() function built into JavaScript.
```javascript
const axios = require('axios');
```

Now that we have access to Axios we simply neeed to create our request. To do this we need to supply our get request with a URL and an optional config. This is an example of a basic axios request to GET information on a user:
```javascript
const axios = require('axios');

axios.get('/users/123);
```

This allows us to make a GET request for the user with an ID of 123. However, this is a very basic example and not how we would write it in actuality. If you wanted to write a function that could make a GET request for any user we can add a little bit more to our code to achieve this:
```javascript
const axios = require('axios');

const getUser (id) => {
  axios.get(`/users/${id});
}
```

We now have a function that we can pass an id to and make the GET request for specific users. However, currently the data that is sent back in the response is not being used. We can edit our function to be able to store the response and use it for whatever purposes we might need. Here is an example of logging out the response.
```javascript
const axios = require('axios');

const getUser (id) => {
  const data = axios.get(`/users/${id});
  console.log(data);
}
```
An important note needs to be made here. Axios is promise-based, which means for this code to properly run we need to have it run asynchronously for it to run properly. This is a simple fix as shown here:
```javascript
const axios = require('axios');

const getUser async (id) => {
  const data = await axios.get(`/users/${id});
  console.log(data);
}
```
Finally we can add in error handling and we have a successful Axios GET request.
```javascript
const axios = require('axios');

const getUser async (id) => {
  try{
    const data = await axios.get(`/users/${id});
    console.log(data);
  } catch (error) {
    console.log(error);
  }
}
```

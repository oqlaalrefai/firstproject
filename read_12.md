# Status Codes Based On REST Methods

- In your own words, describe what each group of status code represents:

  - **100’s =** the request has been received and the server will try to comply with a transmission demand of the client. 

  - **200’s =** tell the client that its request was accepted. its work

  - **300’s =** the resource they are requesting isn’t available at the expected location

  - **400’s =** There are several causes to this, timeouts, wrong URI, missing authentication, etc. A client is sending incorrect input and should confirm the input parameters are correct before retrying the request.

  - **500’s =**  problems with overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server.

- What is a status code 202?
 request met all validation requirements at the time of sending
- What is a status code 308?
 request was valid, but its processing will finish sometime in the future.
- What code would you use if an update didn’t return data to a client?
 204 No Content
- What code would you use if a resource used to exist but no longer does?
 410 Gone
- What is the ‘Forbidden’ status code?
403 Forbidden


# Build A REST API With Node.js, Express, & MongoDB - Quick


- Why do we need to pull our MongoDB database string out of our server and put it into our .env?
we will need to use some other other server than localhost, so we need to remove it to enviroment variable.
- What is middleware?
 essentialy code that runs when the server gets a request but befor it gets passed to my routes
- What does app.use(express.json()) do?
This lets our server accepts JSON as a body instead of post element or get element.
- What does the /:id mean in a route?
This is an ID for the each route we have, and with the colon infront of it this means that it's a parameter that we can access by typing in request requset.params.id and this would give us access to whatever they pass after the first slash.
- What is the difference beween PUT and PATCH?
They are both for updating routes, BUT we used PATCH for updating only what the user passes and we use PUT if we want to update all the information.
- How do you make a defalut value in a schema?
We can simply use default and set it to the default value.
- What does a 500 error status code mean?
It means that the actual server (DataBases in crud apps) had some kind of error which caused the actual transaction not to work and it had nothing to do with the actual user using the API.
- What is the difference between a status 200 and a status 201?
201 => object is successfully created and it's more specific then the default status code 200 => means everything was successful.
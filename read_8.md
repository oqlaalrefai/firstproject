# API Design Best Practices

### What does REST stand for?
Representational State Transfer (REST).

REST APIs are designed around resources, which are any kind of object, data, or service that can be accessed by the client.


### What is an identifer of a resource? Give an example.
A resource has an identifier, which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:https://adventure-works.com/orders/1

### What are the most common HTTP verbs?
- get, post, put, patch, and delete.

### What should the URIs be based on?
URIs should be based on nouns (the resource) and not verbs (the operations on the resource).

Give an example of a good URI.
https://adventure-works.com/orders

### What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
Another factor is that all web requests impose a load on the web server. The more requests, the bigger the load. Therefore, try to avoid "chatty" web APIs that expose a large number of small resources.

### What status code does a successful GET request return?
HTTP status code 200 (OK).

### What status code does an unsuccessful GET request return?
HTTP status code 404 (Not Found).

### What status code does a successful POST request return?
HTTP status code 201 (Created).

### What status code does a successful DELETE request return?
HTTP status code 204
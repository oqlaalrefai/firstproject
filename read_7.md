# What Google Learned From Its Quest to Build the Perfect Team
we already take it in 201 course

# How I explained REST to my brother

### Who is Roy Fielding?
Some guy. He's smart. He helped write the first web servers, that sent documents across the internet… and then he did a ton of research explaining why the web works the way it does. His name is on the specification for the protocol that is used to get pages from servers to your browser.

### Why don’t the techniques that we use today work well when we need to be able to talk to all of the machines in the world?
There's this concept that people are calling “Web Services” or "APIs". It means a lot of different things to a lot of different people but the basic concept is that machines could use the web just like people do.

### What is the HTTP protocol that Fielding and his friends created?
is all about applying verbs to nouns. For instance, when you go to a web page, the browser does an HTTP GET on the URL you typed in and back comes a web page.

### What does a GET do?
It is. Especially when you're using a web browser because browsers pretty much just GET stuff. They don't do a lot of other types of interaction with resources. This is a problem because it has led many people to assume that HTTP is just for GET'ing. But HTTP is actually a general purpose protocol for applying verbs to nouns.

### What does a POST do?
If one system needs to add something to another system, it would use an HTTP verb of POST.

### What does PUT do?
If one system needs to add something to another system, it would use an HTTP verb of POST.

### What does PATCH do?
to do a partial update, we use PATCH

REpresentational State Transfer (REST) is an architectural style that defines a set of constraints to be used for creating web services. REST API is a way of accessing web services in a simple and flexible way without having any processing.

A REST API (Representational State Transfer Application Programming Interface) is a set of rules and conventions for building and interacting with web services. It leverages standard HTTP methods to make calls between machines and services in a scalable and flexible manner. Here’s a breakdown of its key concepts and components:

### Key Concepts of REST API:

1. **HTTP Methods**: REST APIs use standard HTTP methods to handle the interaction with resources:
   - **GET**: Retrieve data from a server at the specified resource.
   - **POST**: Send data to the server to create a new resource.
   - **PUT**: Update a resource with new data.
   - **DELETE**: Remove a resource.

2. **Statelessness**: Each HTTP request from a client to server must contain all the information the server needs to fulfill the request (i.e., the server stores no session state).

3. **Cacheability**: responses from the API can be stored by clients or intermediaries (like browsers or proxy servers) for reuse in future requests. This helps improve performance, reduce server load, and decrease latency

4. **Layered System**: A client cannot ordinarily tell whether it is connected directly to the end server, or to an intermediary along the way.

5. **Uniform Interface**: To obtain the uniformity throughout the application, REST has defined four interface constraints: Identification of resources, manipulation of resources through representations, self-descriptive messages, and hypermedia as the engine of application state (HATEOAS).
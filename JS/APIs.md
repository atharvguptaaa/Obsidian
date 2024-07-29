API stands for **Application Programming Interface.** It enables the exchange of information and functionality between different systems, such as between a website and a server or between different software applications.
### Endpoints

An API endpoint is a URL that acts as the point of contact between an API client and an API server. API clients send requests to API endpoints in order to access the API’s functionality and data.
 e.g. - **API Base URL**: `https://api.weatherapi.com`
	 ==**Endpoint**==: <font color="#9bbb59">/v1/current.json</font>
	 **Full URL**: `https://api.weatherapi.com/v1/current.json`
	 **Purpose:** This endpoint retrieves the current weather conditions. You would need to provide additional parameters like the location (city name or coordinates).
	 **Example Request:** `https://api.weatherapi.com/v1/current.json?key=your_api_key&q=London`
	 **Method:** GET

### Fetch Interfaces

`fetch()`
The fetch() method used to fetch a resource.

`Headers`
Headers are an essential component of HTTP requests and responses. They are used to pass additional information between the client and the server.

`Request`
Represents a resource request.

`Response`
Represents the response to a request.
### Types of HTTP Requests

We use various `HTTP` request methods, such as `get`, `post`, `put`, and `delete`, to get and store data in our database. But the most common requests made are the `get` and `post` requests.
Let's discuss the meaning of these `HTTP` request methods:

- **GET:** This method retrieves data from a specific endpoint. Think of it as asking for information.
- **POST:** This method sends data to a specific endpoint. For example, you can send a message or submit a form. The information will be added to the database.
- **PUT:** This method is used to <font color="#9bbb59">update</font> a record or data value at a designated endpoint. You're making changes to existing information.
- **DELETE:** This method erases data from a specific endpoint. It's like discarding unnecessary things.
### What are Headers?
Headers in an API are key-value pairs sent in HTTP requests and responses. They provide essential information about the request or the response, such as content type, authentication, caching policies, and more. Headers can be categorized into request headers(e.g. Accept, Authorization, User-Agent), response headers(e.g. Content-Type, Content-Length, Set-Cookie), and entity headers.

![[Pasted image 20240729001933.png]]

## *[[fetching an API]]*


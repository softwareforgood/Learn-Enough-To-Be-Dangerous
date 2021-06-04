## How the Web Works, HTTP Request/Response Cycle

#### Learning Goals
- Define the ‘Vocabulary’ of the web
- Describe the Request/Response Cycle at a high level
- Describe the parts of a URL
- Explain Verb/Path combinations
- Describe the 5 common HTTP verbs

#### Vocabulary
- Client
- Server
- URL
- URI
- User
- Request
- Response
- HTTP
- Verb
- Path

#### What is the Internet?
The internet, which for most people is the web…how does that work?

The basis of all web interactions is someone asking for information, and receiving information. In order to ask for and receive any information, we need two players - the asker and the producer. In basic web interactions, the ‘asker’ is a **client** and the ‘producer’ is a **server**. Clients send **Requests** to Servers asking for some kind of information. Upon receiving a **Request**, Servers send **Responses** back to the Client.

The **Internet** is the network between devices that allows clients and servers to exchange this information. **HTTP** is a set of rules for how this exchange of information happens. Clients and Servers adhere to these rules to ensure that they understand each other’s Requests and Responses.

In the web development world, a client is a web browser, not an individual person. The person using the browser is referred to as a **user**.

### The Request and Response Cycle
The HyperText Transfer Protocol gives us rules about how messages should be sent around the Internet. The system that initiates a connection sends a “request”, and the system the answers sends a “response”.

#### HTTP Request
When a “client” (like a web browser) retrieves information, it sends a payload of data to a server as a “request”. This request has many parts, but for now we are going to focus on the **verb** and **path**.

#### Verb and Path
Every request needs to be able to tell a server what information is requested and how that information is being requested. The what is the path (also know as a URI), indicating what resource this request is referencing.

Examples of a path:
- `/tasks`
- `/tasks/4`
- `/items/6/reviews`

The how is the verb, indicating what actions the server should take regarding the requested resource. While the path can vary greatly based on the application, the verbs follow common patterns. There are 5 common HTTP verbs:
- GET - retrieve some information to be READ by the client/user
- POST - CREATE a new resource with information contained in the request
- PUT - UPDATE an entire resource with information contained in the request
- PATCH - UPDATE a part of a resource with information contained in the request
- DELETE - DESTROY a resource, typically indicating that it is removed from the database

With these 5 verbs, we send requests that allow us to perform all CRUD functions (create, read, update, destroy) for resources in a database!

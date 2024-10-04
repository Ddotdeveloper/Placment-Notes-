#### Explain what an API endpoint is?
- Acts as the entry point to the service it is a url
- client application intract with the server by sending request on the api end point 
#### Can you explain the difference between SQL and NoSQL databases?
##### Sql 
- Predefined Schema is there 
- Follow a patricular format 
- Vertically scalable, meaning you scale by adding more resources
- Use a Query Language 
- Suitable for applications where data integrity, consistency, and complex querying
- **SQL**: MySQL, PostgreSQL, Oracle, SQL Server.
##### NoSql 
- There is no predefined schema 
- does not have a format
-  Horizontally scalable, meaning you scale by adding more servers to the database cluster, making it more suited for large-scale distributed systems
- Does not use a query language
-  for large-scale applications requiring high availability, scalability, and handling unstructured or semi-structured data (e.g., social networks, real-time analytics).
- **NoSQL**: MongoDB, Cassandra, Redis, Couchbase.

#### What is a RESTful API, and what are its core principles?
- follows the REST guidelines
-  follow a client-server architecture also followed by http 
######    Provide a uniform interface (some rules )
- way to identify resources from each other by the url's
- should be a way to modify resources through their representation
- way to modify resources through their representation.
- Messages should be self descriptive, meaning that each message should provide enough information to understand how to process
***
- It needs to be stateless. contain all information to process the request
- Resources should be cacheable either by client or by server
- Optionally, the server could send code to the client for it to execute (known as “Code on Demand”


 
## What is HTTP

HTTP = Hypertext Transfer Protocol

An application layer protocol that allows web-based applications to communicate and exchange data.
It is a TCP/IP based protocol to deliver contents i.e. texts, images, videos.

### 3 HTTP properties
- HTTP is connectionless: after making the request, the client disconnect from the server, then when the response is ready the server re-establish the connection and deliver the response.
- HTTP can deliver any data, as long as the two computers are able to read it.
- HTTP is stateless: the client and server know about each other just during the current request. If it closes, and the two computers want to connect again, they need to provide information to each other anew.

HTTP was designed mainly to fetch HTML documents and sends it to the client. However, it is being continually improved with features added to it.

### Process
1. The user type in the URL of the server, but they must first be connected first physically through the Internet.
2. When connection is established, the client sends the request as HTTP message to the server.
3. The server sends the response as HTTP message to the client.

### Request HTTP message
1. Start line, containing Method, URI, and HTTP version
2. Headers, containing Host, Accept, and Accept-language. The headers specify the rules of the HTTP message.

### Response HTTP message
1. Start line, containing http/version and status code
2. Headers, contains rules specifications similar to request HTTP message.
3. Response body, containing the requested files


source: https://www.youtube.com/watch?v=eesqK59rhGA
# What Happens When You Type https://www.google.com in Your Browser?

When you type the website address https://www.google.com in your browser and press enter something cool happens.

The browser sends a message to the website https://www.google.com.

This message says "hey I want to see the website https://www.google.com".

Then the website https://www.google.com sends back all the information that it has.

This information is like a package that has all the words and pictures that you see on the website https://www.google.com.

The browser then takes this package. Puts it all together so you can see the website https://www.google.com.

You can then look at the website https://www.google.com. Even click on things to see more.

The website https://www.google.com is an useful tool that can help you find answers, to your questions.

You can use the website https://www.google.com to learn things and have fun at the same time.

## Introduction

When you type a website address into your browser and press Enter a lot of things happen. This is something software engineers really need to know about.

This blog post will go through the process one step at a time. It will talk about things like what happens with DNS requests and TCP/IP.

It will also cover firewalls and how HTTPS and SSL work.

You will also learn about load balancing and the role of web servers and application servers and databases.

The blog post is, about what happens when you type a URL into your browser and press Enter.

## 1. DNS Request

So the first thing we need to do is take the website address that people can read, like https://www.google.com and turn it into something that computers can make sense of, which's an IP address. This process has a parts, to it:

When you try to go to www.google.com your browser looks at the stuff it has stored on your computer. It wants to see if it already has the internet address for www.google.com. This is called the browser cache. The browser checks its cache first to find the IP address, for www.google.com.

So when the browser cache does not have what you are looking for it will ask the Operating System Cache for help. The Operating System Cache is like a storage place that the Operating System uses to keep track of things. In this case the browser will check the Operating System Cache to see if it has the record it needs. The Operating System Cache is also where the Operating System stores information, about the websites you visit like the websites address. This is called the DNS record. So the browser will look at the Operating System Cache to find the DNS record it is looking for.

So when your computer looks for a website and it does not find the address in its memory it sends the query to a special kind of resolver. This resolver is called a Recursive Resolver. The Recursive Resolver gets the query from your computer when the Operating System cache does not have the answer. Then the Recursive Resolver sends the query to a resolver that your Internet Service Provider gives you or to a service like Google Public DNS. The Recursive Resolver is, like a helper that finds the address of the website you want to visit.

So we have the Root and the Top Level Domain and the Authoritative Name Servers. When we want to find the internet address of Google, our computer talks to the Root server first. Then it talks to the Top Level Domain server, which's the.com server in this case. After that it talks to the Authoritative Name Server, for Google. This is how we get the internet address of Google. The Root and the Top Level Domain and the Authoritative Name Servers all work together to help us find the internet address of Google.

When the internet address is figured out the browser knows where to send the information. The browser knows where to send the request to the IP address. The IP address is used by the browser to send the request.

## 2. TCP/IP

The browser sets up a connection, with the server that has www.google.com using the Transmission Control Protocol over the Internet Protocol. This process involves:

* the browser
* the server that has www.google.com
* the Transmission Control Protocol
* the Internet Protocol

The browser and the server that has www.google.com need to talk to each other using the Transmission Control Protocol and the Internet Protocol. The Transmission Control Protocol and the Internet Protocol help the browser and the server that has www.google.com communicate with each other.

### Three-Way Handshake:

The client sends a SYN packet to the server. This is how the client starts talking to the server. The client needs to send this SYN packet so that the server knows the client wants to connect to it. The SYN packet is a kind of message that says "hello I want to talk to you" to the server. When the client sends the SYN packet to the server it is the step in setting up a connection, between the client and the server.

The server sends back a packet that says SYN-ACK. This packet is like a confirmation that the server's ready to talk to the computer that sent the request. The server is saying okay I got your message and I am ready to start talking this is what the SYN-ACK packet, from the server does.

The client sends an ACK packet which completes the handshake, for the client. The client is now done with the handshake.

The handshake makes sure that the connection is good before any data is sent. This is important for the data transfer to work properly. The handshake is what ensures a connection.

## 3. Firewall

Firewalls are used on the client side and the server side. The job of these firewalls is to check the packets that come in and go out. They make sure these packets are what they are supposed to be. The firewalls check to see if the packets follow the security rules. If the packets do not follow the rules the firewalls can stop them. Firewalls can block requests that seem suspicious or that are not allowed. This helps keep the client and the server safe from things. The firewalls, on the client side and the server side do this job all the time.

## 4. HTTPS/SSL

When you see a website address that starts with https it means that the website is using a connection. This secure connection is what happens when the website uses something called SSL/TLS.

This involves:

### Certificate Verification:

The browser checks the servers SSL certificate to make sure the SSL certificate is okay. It was given by a trusted Certificate Authority. The browser does this to make sure the SSL certificate is valid. The Certificate Authority has to be trusted for the browser to be happy, with the servers SSL certificate.

### Key Exchange:

The client and server use a secure method (like Diffie-Hellman) to exchange encryption keys.

### Session Encryption:

The client and the server will talk to each other in a code, from now on. This way the client and the server can be sure that what they say to each other is private and cannot be changed by someone. The client and the server want to keep their conversations safe so they use this code to protect themselves.

## 5. Load Balancer

The request may first go to a load balancer. This load balancer is really important because it helps with the traffic. It makes sure the traffic is spread out across servers. This is good because it means the system is always available and can handle a lot of users. The load balancer does a things it might:

* Route traffic based on geographic location.
* Check server health and direct traffic only to healthy servers.
* Terminate SSL/TLS connections to reduce the load on backend servers.

## 6. Web Server

The load balancer sends the request to a web server, like Nginx or Apache. The web server:

* gets the request
* does what it needs to do

The web server is like the brain of the operation it knows what to do with the request so it handles it. The web server, such, as Nginx or Apache is very important.

* Parses the request headers.
* Determines the type of content requested (static files like images or dynamic content).
* Either serves static content directly or forwards the request to an application server for dynamic content.

## 7. Application Server

When we talk about requests the web server needs to work with an application server. This application server can be something, like Node.js, Django or Flask. The application server:

* Processes the request logic.
* Runs backend code to generate a response.
* Often queries a database to fetch or update data.

## 8. Database

The application server works with a database, like MySQL or PostgreSQL or MongoDB to get or put away data. This is what it does:

* Executing SQL queries or NoSQL commands.
* Ensuring data consistency and integrity.
* Returning the requested data to the application server.

## 9. Response to the Browser

The application server sends the generated response, like an HTML page back to the web server. The web server then forwards this response, to the load balancer. The load balancer sends this response to your browser. This completes the request-response cycle of the application server and the web server and the load balancer.

The browser:

* Parses the HTML.
* Makes additional requests for resources (CSS, JavaScript, images).
* Renders the page for the user.

## Conclusion

This sequence of events showcases the complexity of a seemingly simple action. Each step involves multiple technologies and systems working together to deliver a seamless user experience. Mastering these concepts can set you apart in technical interviews and help you build robust software systems.
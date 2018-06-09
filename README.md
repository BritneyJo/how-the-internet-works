# <img src="https://cloud.githubusercontent.com/assets/7833470/10899314/63829980-8188-11e5-8cdd-4ded5bcb6e36.png" height="60"> How the Internet works

### Learning Objectives

- Explain in general terms how a client machine locates and connects to a server.
- Understand the difference between a domain name and an IP address.
- Identify the critical components of HTTP requests/responses.

### Prerequisite Knowledge

- Navigate to a website in a web browser.
- Connect a computer to a network in order to access the Internet.

## The Internet is Serious Business

The Internet is a complex system with a lot of moving pieces. As web developers, it's important for us to understand how certain pieces interact with one another, and where our "code" fits into the ecosystem. We will not be learning everything there is to know about Internet infrastructure, but this is an important topic.

## What is the Cloud?

When you connect to a website, you're really just connecting to another computer out there somewhere.

When we talk about "the Internet" and "the cloud", we often mean the same thing: billions of computer systems connected to one another to provide a wide variety of content and services. We more typically say "Internet" when we're talking about looking at websites and "cloud" when we're talking about back-end services and APIs (e.g. storing data online, using someone else's data services like image recognition, etc). No matter what you call it, you're ultimately connecting your computer to some other computer out there.

### The Internet is a Big Collection of Computers and Cables

The Internet is named for "interconnection of computer networks". It is a massive hardware combination of millions of personal, business, and governmental computers, all connected like roads and highways.

No single person owns the Internet. No single government has authority over its operations. Some technical rules and hardware/software standards enforce how people plug into the Internet, but for the most part, the Internet is a free and open broadcast medium of hardware networking.

### The World Wide Web

The World Wide Web, or "Web" for short, is a massive collection of digital pages: that large software subset of the Internet dedicated to broadcasting content in the form of HTML pages. The Web is viewed by using free software called web browsers. Born in 1989, the Web is based on hypertext transfer protocol (HTTP), the language which allows you and me to "jump" to any other public web page. There are over **1.5 billion** websites on the W3 today.

[Wires, Cables, and Wifi](https://www.khanacademy.org/partner-content/code-org/internet-works/v/the-internet-wires-cables-and-wifi)


## What is this client/server magic?

The internet comes down to requests and responses - you send information out to the web, and based on the info you send, you get information back. When two computers connect over the Internet, they establish a server-client relationship.

A **server** is a computer that is set up to accept requests and respond to them. We often say these systems host or serve webpages. They share their resources with clients.

A **client** is a computer that initiates a request from a server. When you open a webpage, your computer is the client, initiating the request on your behalf. We can also call your web browser (Chrome, Edge, Firefox, etc) the client, since it is the program on your computer that handles making the request and displays the response.
  > Ex: web browsers, terminals, SQL clients

![](https://cloud.githubusercontent.com/assets/4304660/23087118/80f5e464-f526-11e6-8f74-6bde3cdaa66c.png)

The key here is that two computers get connected in a server-client relationship. The client initiates a request and the server responds. The client handles the response in some way that is useful for the user, like displaying the webpage on screen.

Note that it is possible for the same computer to play the role of server and client. It is common for a developer to set up their own computer to play the role of server while they're building a webpage. Then they can preview the site they're building while they're building it.


## IP Addresses and Domains

We know that our computer needs to establish a connection with a server, but how does it know which computer and where to find that computer?

Every computer has a location on the Internet called their IP address. Traditionally, IP addresses are composed of four bytes of data separated by periods. Since four bytes *only* offer around 4.3 billion unique IP addresses, they've all but run out. A migration is underway to IPv6 that uses 16 bytes - or 4.3 billion to the power of 4 - that would provide an absurd 42 undecillion unique combinations.

IPv4  `99.53.226.231`
IPv6  `[2001:db8:85a3:8d3:1319:8a2e:370:7348]`


So we can connect to a particular computer using its IP address, but that's not very easy to remember. Instead, people type in something simple like `www.google.com` or `en.wikipedia.org`. This human-readable address is called a domain.

When you enter a domain like `www.google.com` into your web browser, it goes and finds the IP address of the appropriate computer. We call this lookup process **Domain Name Resolution**.

### Domain Name System (DNS)

Domain Name System, or **DNS servers**, act as information redirectors that will direct your search for a certain website to it's actual physical server location.  When we enter `https://www.google.com` into our browser, what happens is a "DNS Lookup" of that particular domain's IP address, so your computer can actually connect to it. DNS is the way that Internet domain names are located and translated into Internet Protocol addresses.

The Process:  

1. Type www.google.com into your browser address bar.

2. Your browser sends an HTTP Request to a DNS server.

3. The DNS server looks for a server that has a big list of all `.com` websites and sends us the IP address of that server.  An IP address is a series of digits that act just like a physical street address.

4. Now that we're in the `.com` server, they send us to yet *another* server that will send us to a more specific DNS server that, for example, maybe contains only websites that start with the letters `E` through `K`.

5. We have finally been taken to the DNS server that knows where Google.com is! The final DNS server gives us the specific IP address of Google.com (139.130.4.5).

6. Our browser finally goes to the address given by the last DNS Server and we see the beautiful Google landing page of the day!

<img width="698" alt="screen shot 2017-02-18 at 10 25 37 am" src="https://cloud.githubusercontent.com/assets/4304660/23095784/a542df90-f5c4-11e6-8c19-0909f77d6b9d.png">

[IP Addresses and DNS](https://www.khanacademy.org/partner-content/code-org/internet-works/v/the-internet-ip-addresses-and-dns)


## HTTP

**HyperText** - jump or hyperlink   
**Transfer** -  transfer of data  
**Protocol** - standard way of doing things, a stateless protocol

HTTP stands for "Hyper Text Transfer Protocol" - because it's a protocol, it allows for communication between a variety of different computers and supports a ton of different network configurations. To make this possible, it assumes very little about a particular system, and does not keep state between different message exchanges. A stateless protocol does not require the server to retain information or status about each user for the duration of multiple requests.

### What are Protocols?

In computer networks, communication occurs between entities in different systems. An entity is anything capable of sending or receiving information. However, two entities cannot simply send bit streams to each other and expect to be understood. For communication to occur, the entities must agree on a protocol.

A protocol is a set of rules that governs data communication. A protocol defines what is communicated and how it is communicated. There are 3 key elements of a protocol:

**Syntax** - structure and format of the data, meaning the order in which they are presented. For example, a simple protocol might expect the first 8 bits of data to be the address of the sender, the second 8 bits to the address of the receiver, and the rest of the stream to the message itself.

**Semantics** - refers to the meaning of each section of bits. How is a particular pattern to be interpreted, and what action is to be taken based on that interpretation? For example, does an address identify the route to be taken or the final destination of the message?

**Synchronization/Timing** -  Timing refers to two characteristics: when data should be sent and how fast it can be sent. For example, if a sender produces data at 100 Megabits per second (Mbps) but the receiver can process data at only 1 Mbps, the transmission will overload the receiver and data will be largely lost.

### What is TCP/IP?

Transmission Control Protocol/ Internet Protocol

TCP/IP defines how electronic devices (like computers) should connect over the internet, and how data should be transmitted. They complement each other so you will often hear them referred to together.

**TCP** is responsible for breaking data down into packets and assembling them back together again. TCP provides reliable, ordered, and error-checked delivery of a stream of octets between applications running on hosts communicating over an IP network.

**IP** is responsible for addressing, sending, and receiving of the data packets.

All client-server protocols operate in the application layer. The application-layer protocol defines the basic patterns of the dialogue.

![](https://s3.amazonaws.com/one-month-rails-production/assets/images/000/000/075/original/image01.png?1412885329)

A server may receive requests from many different clients in a very short period of time. Because the computer can perform a limited number of tasks at any moment, it relies on a scheduling system to prioritize incoming requests from clients in order to accommodate them all in turn.

To prevent abuse and maximize uptime, the server's software limits how a client can use the server's resources. Even so, a server is not immune from abuse. A denial of service attack exploits a server's obligation to process requests by bombarding it with requests incessantly. This inhibits the server's ability to respond to legitimate requests.

[Packets, Routers and Reliability](https://www.khanacademy.org/partner-content/code-org/internet-works/v/the-internet-packet-routers-and-reliability)

### Elements of a URL

URL stands for Uniform Resource Locator, and it's just a string of text characters used by Web browsers, email clients and other software to format the contents of an internet request message.

Let's breakdown the contents of a URL:

```
    https://www.google.com/search?q=puppy+gifs#footer
    \____/  \____________/ \____/ \__________/ \____/
   protocol   host/domain   path   querystring  hash
```

Element | About
------|--------
protocol | the most popular application protocol used on the world wide web is HTTP. Other familiar types of application protocols include FTP, SSH, GIT, HTTPS
host/domain name | the host or domain name is looked up in DNS to find the IP address of the host - the server that's providing the resource
path | web servers can organize resources into what is effectively files in directories; the path indicates to the server which file from which directory the client wants
querystring | the client can pass parameters to the server through the querystring (in a GET request method); the server can then use these to customize the response - such as values to filter a search result
hash/fragment | the URI fragment is generally used by the client to identify some portion of the content in the response; interestingly, a broken hash will not break the whole link - it isn't the case for the previous elements

## HTTP Communication

On the internet, clients send **HTTP requests** and servers reply with **HTTP responses**. HTTP is HyperText Transfer Protocol, is just an agreed-upon set of rules about what these requests/responses look like.

Every HTTP Request includes the **HTTP method** and **path** (what is being requested), **HTTP Headers** (extra details about the request), and possibly a **body** (a file needed to process the request, only included for certain HTTP methods).

Every HTTP Response includes a **response status code** (was the request successful), **HTTP Headers** (extra details about the response), and probably a **body** (a file being sent in response).

Here are the possible HTTP Methods, in order from most common to most rare:
- **GET**
- **POST**
- **PUT**
- **DELETE**
- OPTIONS
- CONNECT
- TRACE
- HEAD

We will learn more about the different HTTP Methods later, but for now just try to recognize them when you look at things in the browser's Dev Console.

HTTP Headers are typically used for providing extra information about requests and responses. Common examples are dates, time stamps, content type, encoding options, caching details, language, user/login information, security details, verification information, etc. The best way to understand HTTP Headers is to start looking at them in your Dev Console, recognize patterns, and look up more information whenever you're curious about a particular header.

HTTP responses include status codes. These codes can be very useful for developers working with request/response cycles. They come as three digit numbers and dictate whether a specific HTTP requests has been successfully completed. Responses are grouped in five classes, with the first digit determining the higher-level categorization:

- 1xx Informational
- 2xx Success
- 3xx Redirection
- 4xx Client Error
- 5xx Server Error


#### Server-side vs. Client-side

Once the request <--> response cycle has been executed, the web browser is in charge of interpreting the data received and showing it to the user.  Looking more closely at the types of computer languages and markup that's involved:

![](http://image.slidesharecdn.com/html-css-presentation-131023112801-phpapp02/95/html-csspresentation-7-638.jpg?cb=1383133015)

The server contains code - Ruby, PHP, Java, even JavaScript - that processes your request.  Depending on the contents of your request, the server will execute different files on the server that contain code.  Then, the server will return a particular set of information and data.

The information and data received is usually packaged in an HTML document with some CSS and JavaScript files. You may also get a PDF, image, and/or other file types. The location of the resource is specified by the user using a URI (Uniform Resource Identifier).

The way the browser interprets and displays HTML files is detailed in the HTML and CSS specifications. These specifications are maintained by the W3C (World Wide Web Consortium) organization, an important standards organization for the web. The JavaScript language specification is published by a technical committee (TC39) at the ECMA organization.

[HTTP and HTML]( https://www.khanacademy.org/partner-content/code-org/internet-works/v/the-internet-http-and-html)

## Review of Internet Fundamentals - Independent Practice

Answer and discuss the following questions with a partner:

- What does HTTP stand for?
- What is used to resolve a domain name to an IP address?
- How do clients compare to hosts?
- Compare different HTTP status codes.
- Draw your own diagram of a request/response cycle and label where the following would come into play: client, host/server,  client-side languages, server-side languages, data
- T/F: Every HTTP request has a domain and a path.
- T/F: Email uses the HTTP Protocol.

BONUS VIDEO - [How much does the Internet weigh?](https://www.youtube.com/watch?v=WaUzu-iksi8)

## Resources

* <a href="https://www.youtube.com/watch?v=GlZC4Jwf3xQ" target="_blank">Awkward but lovable guy gives technical description of DNS Servers</a>
* <a href="http://searchnetworking.techtarget.com/definition/client-server" target="_blank">A tangible article on TCP/IP Protocols</a>
* <a href="https://en.wikipedia.org/wiki/Domain_Name_System" target="_blank">Name Servers - A main component of DNS Servers</a>
* <a href="https://en.wikipedia.org/wiki/Name_server" target=

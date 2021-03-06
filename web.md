# Web

* What are the three primary Fielding constraints? (Bonus if you can say who Fielding is!)
    * Roy T Fielding is the originator of REST. wrote the PhD dissertation "Architectural Styles and the Design of Network-based Software Architectures
    1. Network must be made of clients and servers
    2. Stateless
        * Client does not need need to keep track of each other's state.
        * each request is treated as a standalone
    3. Uniform interface
        * common language between servers and clients that allows each part to be swapped out or modified without breaking the entire system
* What sub-constraints make up a Uniform Interface
    1. indentification of resources
        * each resource must be uniquely identified by a stable identifier
            * "stable" means does not change across interactions and does not change when state of resource changes
                * should return that request is bad if so
    2. manipulation of resources
    3. self-descriptive messages
    4. hypermedia
        * data sent from server to client that contains info about what client can do next aka further requests it can make
* Walk through an arbitrary example of a RESTful request/response cycle, and describe what makes it RESTful

*  What happens when you type in www.google.com and hit enter?
    1. browser checks cache for DNS record to find corresponding IP address
    2. if IP not found, ISP's DNS server inititates a DNS query to find ip address of server that hosts destination
    3. Browser initiates a TCP connection with server
        * TCP/IP three-way handshake
    4. Browwser sends an HTTP request to the web server
    5. Server handles the request and sends back an response
    6. Server sends out an HTTP request
    7. browser displays HTML content

* Why do we need a DNS?
    * Domain Name System is architure for pairing domain name with the IP address. Browser will usually request from the DNS resolver and then store the address in memory to reference it quicker next time

* Explain TCP, and why it is a necessary protocol
    * part of the transport layer, talks to application layer and will make the request to the appropriate address in the network lawyer
* What is a datagram?
    * basic transfer unit associated with a packet-switch network 
* What are the benefits of UDP over TCP? What are the shortcomings?
    * UDP
        * pros
            * smaller packets
            * no connection to create/maintain
            * more control over what data is sent
        * cons
            * data corruption is often, and no error recovery. either keeps corrupted data or discards all
            * no compensation for lost packets
            * packets can be out of order
            * no congestion control
    * TCP  
        * three-way handshake. delivery acknowledgement and retransmission available
        * in-order delivery, can/will arrange properly
        * cons
            * bigger header
            * data doesn't always get sent out immediately
            * bigger overhead
* What are the common HTTP methods? When are they used, and what do they accomplish? (This is a big one)
    * GET
        * retrieves data from a URI
    * HEAD
        * same as get but transfer status line and header section only
    * POST
        * sends data, like information, html form
    * PUT
        * replaces all current representation of target resource with uploaded content
    * TRACE
        * message loopback test along the path of the target resource
    * DELETE
        * removes all current represntation of target resource
    * CONNECT
        * established tunnel to server ID by given URI
    * OPTION
        * describe the communication option for target resource
* What is the difference between HTTP and HTTPS
    * Https requires handshake which is both asymmetrical and symmetrical crypto
* What is the difference between localStorage and sessionStorage?
    * sessionStorage persists for the duration of browser session and is removed when tab/window is closed. can survive page reload
* Why is it important that users cannot modify their cookies?
    * xss. you can also change data to pretend you are another user who's authenticated
* When are cookies sent to the server?
    * every request to the same domain
        * original page request, ajax, img, styles, scripts, fonts
* What is the danger of an XSS
    * access to same objects
    * read/make arbitrary modifications to browser's DOM
    * use XMLHttpRequest to send HTTP request with arbitrary content to arbitrary destination
    * leverage HTML5 APIs and specific files from user's file stystem
* What is a CSRF Attack?
    * attack that tricks a victim into performing actions on behalf of the attacker
* How can you prevent CSRF Vulnerabilities?
    * anti-csrf tokens, which require having tokens when state changing form.
        * changing password, user info, etc
* What is an XMLHttpRequest?
    * API in form of an object. can send and receive info, mainly json, xml, html, and text files
* When are two pages considered to have the same origin?
    * same protocol and host
* How might you allow cross-origin resource sharing?
    * you would want to allow CORS which gives permission to load content to load content from server
* What is CORS?
    * uses http headers to tell a browser to allow a web app running one origin to have permission to access server
* What are the advantages and disadvantages of NoSQL databases vs. SQL databases?
    * pros
        * data is close to english
        * big data tasks
    * cons
        * not user friendly
        * not good for real time data
* What is Round Robin DNS binding?
    * 
* What issue arises regarding sessions when implementing a Load Balancer?
  * 
* What is striping when talking about writing to a Hard drive?
  * 
* What is RAID and what functionality can it give you?
  * 
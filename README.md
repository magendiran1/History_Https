# History_https
<!--  -->

Evolution of HTTP
# HTTP
(HyperText Transfer Protocol) is the underlying protocol of the World Wide Web.
Developed by Tim Berners-Lee and his team between 1989-1991, 
HTTP has seen many changes,
keeping most of the simplicity and further shaping its flexibility.

# Invention of the World Wide Web.

In 1989, while he was working at CERN, Tim Berners-Lee wrote a proposal to build a hypertext system over the Internet. Initially calling it the Mesh, it was later renamed to World Wide Web during its implementation in 1990. Built over the existing TCP and IP protocols, it consisted of 4 building blocks:

A textual format to represent hypertext documents, the HyperText Markup Language (HTML).
A simple protocol to exchange these documents, the HypertText Transfer Protocol (HTTP).
A client to display (and accidentally edit) these documents, the first Web browser called WorldWideWeb.
A server to give access to the document, an early version of httpd.

The HTTP protocol used in those early phases was very simple, later dubbed HTTP/0.9, and sometimes as the one-line protocol.

# Version History
# HTTP-- Version--0.9--The one-line protocol
------------------------------------------------------
* Initial version of HTTP had no version Number.
* It has been later called 0.9 to differentiate it from the later versions.
*  HTTP/0.9 is extremely simple: requests consist of a single line and start with the only possible method GET followed by the path to the resource (not the URL as both the protocol, server, and port are unnecessary once connected to the server).
* GET /mypage.html
* <HTML>
A very simple HTML page
</HTML>

*There were no HTTP headers, meaning that only HTML files cloud be transmitted. no other type of documents.
*There  were no status or error codes.
* In case any problem in the HTML file it will sent back with Description  problem having in the File.
--------------------------------------------------------

# HTTP/1.0 – Building extensibility

HTTP/0.9 was very limited and both Browser and Server are quickly extended more versatile.

*version Information sent now in all each request(HTTP/1.0 is appended to the GET Value).
* A Status code also sent beginning of the response.Allowing the browser itself to understand sucess or Failure of the Request.
* The Notion of HTTP  headers has been introduced for both request and Responses allowing metadata to be transmitted and Making the Protocal extremely flexible and extensible.
* New HTTP headers  is ability to transmit other documents than plain HTML Files has been added. using of [Content-Type]
#                                                  [Request and Response for Plian text.]

#              Request part.
      GET/mypage.html HTTP/1.0
      User-Agent :NSCA_Mosaic/2.0(Window 3.1)

#              Response

200 OK
Date:SAT ,7 Aug 1994 08:12:35 GMT
Server: CERN/3.0 libwww/2.17
Context-Type: text/html
<HTML>
  A Page with a Image
  <IMG SCR="/myimage.gif">
  </HTML>


-------------------------------
#                                         HTTP/1.1 – The standardized protocol
  * HTTP/1.1 More Features was published on 1997.
  * HTTP/1.1 clarified ambiguities
  * [A connection can be reused], saving the time to reopen it numerous times to display the resources embedded into the single original document retrieved.
  * Pipelining has been added, allowing to send a second request before the answer for the first one is fully transmitted, lowering the latency of the communication.
  * Additional cache control mechanisms have been introduced
  * 
                                                GET /en-US/docs/Glossary/Simple_header HTTP/1.1
                                                Host: developer.mozilla.org
                                                User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:50.0) Gecko/20100101 Firefox/50.0
                                                Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
                                                Accept-Language: en-US,en;q=0.5
                                                Accept-Encoding: gzip, deflate, br
                                                Referer: https://developer.mozilla.org/en-US/docs/Glossary/Simple_header

                                                200 OK
                                                Connection: Keep-Alive
                                                Content-Encoding: gzip
                                                Content-Type: text/html; charset=utf-8
                                                Date: Wed, 20 Jul 2016 10:55:30 GMT
                                                Etag: "547fa7e369ef56031dd3bff2ace9fc0832eb251a"
                                                Keep-Alive: timeout=5, max=1000
                                                Last-Modified: Tue, 19 Jul 2016 00:59:33 GMT
                                                Server: Apache
                                                Transfer-Encoding: chunked
                                                Vary: Cookie, Accept-Encoding
  
  ------------------------------------------------------------------------------------------
  
#                                 Using HTTP for secure transmissions
  
  * The largest change that happened to HTTP was done as early as end of 1994. Instead of sending HTTP over a basic TCP/IP stack, Netscape Communications created an additional encrypted transmission layer on top of it: SSL. SSL 1.0 was never released outside the company, but SSL 2.0 and its successor SSL 3.0 allowed for the creation of e-commerce Web sites by encrypting and guaranteeing the authenticity of the messages exchanged between the server and client. SSL was put on the standards track and eventually became TLS, with versions 1.0, 1.1, 1.2, and 1.3 appearing successfully to close vulnerabilities.
    * During the same time, the need for an encrypted transport layer raised: the Web left the relative trustiness of a mostly academic network, to a jungle where advertisers, random individuals or criminals compete to get as much private information about people, try to impersonate them or even to replace data transmitted by altered ones. As the applications built over HTTP became more and more powerful, having access to more and more private information like address books, e-mail, or the geographic position of the user, the need to have TLS became ubiquitous even outside the e-commerce use case.
  
  
#                                                   HTTP/2 – A protocol for greater performance
  * Over year the web page become more Complex , even the application  in thier own right.
  *The amount of visual media displayed, the volume and size of scripts adding interactivity, has also increased
  * HTTP/1.1  connections  need requests sent in correct order.
  *Theoretically , serveral parallel connections  cloud be used(typically between 5 and 8), bringing considerable overhead and complexity. For example, HTTP pipelining has emerged as a resource burden in Web development.
   * In The First half of google was introduced  a alternative way of exchanging the data btw client to server.That is called protocol [SPDY]
  *This amassed interest from developers working on both browsers and servers. Defining an increase in responsiveness, and solving the problem of duplication of data transmitted, SPDY served as the foundations of the HTTP/2 protocol.
  
  #                          Difference of HTTP/1.1 VS HTTP/2
  
* It is a binary protocol rather than text. It can no longer be read and created manually. Despite this hurdle, improved optimization techniques can now be implemented.
* It is a multiplexed protocol. Parallel requests can be handled over the same connection, removing the order and blocking constraints of the HTTP/1.x protocol.
* It compresses headers. As these are often similar among a set of requests, this removes duplication and overhead of data transmitted.
*  It allows a server to populate data in a client cache, in advance of it being required, through a mechanism called the server push.
  
  
  

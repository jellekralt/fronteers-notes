# Pushing the web forward

## The past
### Plugins
* Stuff like flash, java, etc
* Not so great..

### Polling
* Short polling
	* Bad stuff
	* Not really real time
* Long polling
	* Problem with request duration
	* Browsers cut off long requests
* JSONP GET polling
* JSONP POST polling
	* Both JSONP invoke loading indicators, which is bad for obvious reasons
	* Crazy solution for this is creating and removing an iframe
* XHR
* XDomainRequest

Long polling should only be done onload, otherwise the browser will think its part of the request and the will wait until its finished.

**Caching is a major problem** 
*Especially back-foward cache*

## Now
### Websockets
* Browser support is an issue
	* Especially with IE (no support until IE10)
* Specification is quite complex
* It's very optimised though
* Simple and understandable API
* Sending binary is possible

#### Bugs
* HTTP Proxy settings in your network settings can cause a full browser crash
	* Only on Mac only though
	* Only solution, browser sniffing...
* Writing to a closed web socket connection can crash your phone
	* Mobile Safari when returning to the page fro ma different tab or retrieving Safari from the background
	* Fixable by adding a small timeout before sending over the socket
		* Which you probably only want to do on mobile
* Pressing Esc in Firefox closes the connection
	* Fixed in FF 20
	* Fixable by intercepting the ESC key
* Firefox can create ghost connections
	* When you connect during ws.close()
* Mobile providers are horrible because of caching
	* Caching proxies don't support websockets
	* Falling back on mobile is an option, but a horrible one.
* Virus scanners block web sockets
	* For instance AVG and Norton
	* But also extensions
	* User environments are hostile
* User & Network server firewalls
	* Same thing as virus scanners
* Out of date load balancers 
 
### Server sent events
* Only allows sending data from the server to the client, not the other way around
* Human readable protocol
* Simple API
* Not cross domain
	* Later versions support CORS though
	* Another iframe hack to fix this
		* Done by passing messages to iframe which relays it to the parent browser frame

#### Problems
* Firewalls
* Reconnect is something that can't be trusted 
	* No notifications
* Inactive connections on Mac
 
### Access control
* When done right, its really powerful

### Reconnect
* When your server goes down, all your clients will try to reconnect
	* Which will probably take down your server again.
	* Reconnect should be randomised
### Heartbeat
Should be used to check if the connection is still alive

### Offline
* Listen for offline and online events to handle connection loss
	* Fallback is possible by polling a random image
 
### Per browser connection limit
* Possible fix: connect to different subdomain per connection
* Intertab communication: Setup one realtime system in a tab and check if there are new tabas openend to the same URL and use the connection from the first tab
	* Shared workers 
 
### HTTPS & WSS
**Always** use encrypted connection to increase connectivity

## Q&A with Jake
Socket.io doesn't protect you against browser crashes / system level crashes
There are still open bugs in Chrome that cause crashes on disconnected sockets
Browser connectivity is one of the most vital parts of the browser but it seems like they just didn't test it enough.
Using web sockets highly depend on the type of application/game you are building. 

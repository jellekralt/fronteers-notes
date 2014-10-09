# WebRTC A front-end perspective
World wide web changed communications for ever

Emergence of mobile phones
* People very remote, able to communicate with people far away
 
## WebRTC
Seen very few **web people** talk about it

**Biggest barrier to WebRTC adoption?**
* Lack of awareness
* Not supported by MS
* Not supported by Apple
* Other
 
But... WebRTC is for *Web* developers

## getUserMedia()
### Webcam
CSS masks, filter and bled modes with the Webcam in real-time [Demo]

### Audio
Sound powered actions and navication
Pocketsphinx.js (speech recognition in js)

### Possible usage
* Motion Detection 
* Hotspots
* Gesture recognition
* Emotion recognition
* Sound detection / visualisation
* Voice / sound activated controls
* Capture video (kind of) (whammy.js)
 
### Broken error handling
In the future: 
* naviator.mediaDevices.getUserMedia()
* Promises proposal
* This is still up for debate
	* Some are eager to just ship v1.0 and add support for promises in gUM at a later stage
 
* Impossible for a gUM app to use the device flash for low-light
* Doesn't offer any advanced features
	* focus
	* flash
	* zoom

### Mediastream Image-Capture
* White balance 
* ISO
* Red Eye Reduction
* Exposure
* Brightness
* Contrast
* Saturation
* Sharpness
* Zoom
* takePhoto();
 
Focus? Flash?

### Getting permissions is not easy
* Some users dont seem to notice the permissions dialog in certain browsers.
* Permission dialogs are different on different browsers / platforms / devices
* If the app is on HTTPS then the browser will remember the last granted permission
 

## RTCPeerConnection
As a dev with no communications background it is a bit discomforting because people sometimes assume you have knowledge of communication systems
So many acronyms in RTC.. So many acronyms!

### Free ICE project
https://github.com/DamonOehlman/freeice

### The WebRTC signalling process
WebSocket || XHR || SIP || Carrier Pigeon

Lots of connection will generate lots of CPU load because each connection will have to be encrypted

### Debugging
opera://webrtc-internals
chrome://webrtc-internals
about:webrtc

the getStats() method

http://callstats.io

### Data channels
Data Channels provide
* High Performance
* P2P
* Low Latency
 

#### Working with data
datachannel
.onopen
.onclose
.onerror
.onmessage
.send
 
SCTP Transport Protocol
DTLS Encryption
UDP

#### Options
**ordered**
send data packets in ordered fashino or not
**maxRetransmitTime**
max time to try to send a failed message

**maxRetransmits**
Max number of tries to deliver failed message before it gives up

#### IN the wild
* Peerflix
	* @mafintosh 
* PeerCDN
* WebTorrent
	* @feross
 
### IsWebRTCReadyYet.com 
Apple: Nope
Microsoft: 
	* gUM: working on it
	* WebRTC: not yet
 
### ORTC
* WebRTC 1.1
* SDP exchange not req
* Advanced stuff like simulcast
* More low level than WebRTC
* Shim for WebRTC to work on top of ORTC
* mportant goal is compat. Existing apps should not be affected
 
### Communication
End user doenst really care about what technology you use

## Q&A with Jake
A lot of the stuff WebRTC does hides the complexity of the communication
Doing stuff with the camera and canvas is expensive


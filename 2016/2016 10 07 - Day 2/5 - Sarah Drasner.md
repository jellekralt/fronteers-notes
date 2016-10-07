# Functional Animation

* @sarah_edo | twitter
* @sdras | codepen

---

* Saccade
* Growth-hacking

## **Invisible animations** *vs* **immersive animations **

### Invisible animations

* Mental maps
    * Context-shifting in UX
* Interuption
* Spacial maps
    * Smoothstate.js
* Prevent / reduce cognitive leaks
* Revealing
* Style and branding: not one size fits all

> "If animation just feels like the sugar on top, thats because you treated it that way"

* Spacial awareness
* Right tools for the job

#### Perfomance
* Opacity
* Transofrms
* Hardware accelerations


* Debugging keyframe animations
* High performance animations

### Immersive animations

#### Dom/Virtual Dom
Pros
* Great for UI/UX anims
* Greate for SVG that is resolution independent
* Easier to debug

Cons
* Tanks with a lot of objects
* Because of this you have to care about the way you animate

#### Canvas
Pros
* Dance, pixels, dance!
* Great for really impressive 3d or immersive stuff
* Movement of a tons of objects

Cons
* Harder to make accessible
* Not resolution independent **out of the box**
* Breaks to nothing

#### SVG!
* Crisp on any dispaly
* Less HTTP reqs to handle
* Easily scalable for responsive
* Small filesize if design for perf
* Easy to animate
* Easy to make accessible

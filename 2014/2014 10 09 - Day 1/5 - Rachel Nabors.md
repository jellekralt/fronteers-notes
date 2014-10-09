# State of the Animation
Flash may be gone, but the era of **Web animation** has just begun.
Animation is a visual representation of a rate of change over time and space.

## Kinds of animation
* Static animations
	* Run from start to finish
	* For instance: loading indicator
	* Doable with CSS
* Stateful animations
	* Starts with a default state
	* Moves to a (pre)defined state
	* Appear a lot in mobile app environments
* Dynamic animations
	* Starts with a current state
	* Next state is defined dynamically
 
**Multiple states v.s. Dynamic animation**
For instance: 
**Statefull** Loading bar could have 100 states (a state for each percent of the bar) 

## Animation library developers
Animation library developers usually build for their own processes

Animation libraries are mostly developed inhouse, which often prevents them being published open source, because of:

* No time
* Not wanting people interfering with their library
* Bosses who don't like giving their stuff away

## ~~The greatest~~ an API You've Never Heard of: The web animation API
Does it have:

* Performant animations
* Motion paths
* callbacks
* nesting & sequencing
* pause, play, reverse, seek

**It does!**

Polyfill: https://github.com/web-animations

It has shit performance though

* Web animation API animations get their own thread*
	* So long as the animation doesnt tie into any things happening on the main thread
 
* Reflows are a rendering engine problem
* opacity & trnasform remain safe
	* dont trigger layout reflows
	* coming soon! color, motion in paths
 
* Th ecss property will-change is a start
	* promotes things to their own layer
	* The end of translateZ(0)

## Pushing the web (animations) forward
Everybody wants something different
* Tools!
* Browser support and performance!
* The standardistas need to come down from their ivory towers!
* Show them how well it performs!
 
## Animation is coming, wether we're ready or not

### User interface designers
* Don't be afraid of JavaScript
* Take time to play around with it
 
### Interaction designers
* Check out the polyfill's page
* Give feedback

### Animation library developers
* Go read the spec
* Give feedback

### Animation spec authors & implementors
* Find better ways of taking feedback
* Meet the people you're building this for
* Designers don't want to come and play with you on IRC

### Everyone
* Respect each other
 
### We are not our tools, we build tools, together...


http://rachelnabors.com/waapi


## Q&A with Jake
Abobe's Edge animate has some problem

* You have to conform to our ideas
* You're building an animation in something that is not a browser
* Should't we build animations in a browser?
 
Q: What parts do you like about the web animations spec
A:
* Havent read the whole spec
* I like a lot of the polyfill
* Gives a lot of people what they want
* Not unhappy with it
* There are probably not so great things about it but we need to start giving feedback about that.
 
Q: Is 60fps the endgoal?
A: 60fps is overrated 
	When you go to see a movie, that's 24 fps. 
	You can add motion blur yourself
 
Q: If you click on a link on a page. Currently you get a white screen while everything is loading. Should we add loading / transitions into the page?
A: API for that would be great
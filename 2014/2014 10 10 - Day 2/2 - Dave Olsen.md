# Optimizing web performance

* Quick intro about she we should car about web perf
* Diagnosing Perf Problems
* Easy web perf optimization wins
* Tools to help test & automate perf optimizations
* Setting up a device lab
 
## Why should we care
Shift to resp webdesign is just the tip of the iceberg

* We tend to develop stuff on desktop
* Web pages today are very bloated
* Just using Responsive Design is not a cure-all
* Bounce rate is hugely influenced by load time
* Massive implications
* Almost 4% drop in conversion (sales)

**"Mobile first means performance first"**

### Primary performance issues for RWD
* Over downloading
	* Download & Hide
	* Download & Shrink
	* Download & ignore
* Poor networks
	* High latency
	* Variable Bandwidth
	* Packet Loss
 Try to think about things you absolutely can't overcome

Current Dev practices + Desktop First RWD > Web performance blues

## Diagnosing web performance issues

1. The basics: Pagespeed insights
	* http://developers.google.com/spee/pagespeed/insights 
2. Next steps: chrome dev tools
	* Dev tools is more than just the elements view!
3. Next steps: Chrome dev tools course
	* http://udacity.com/course/ud884
4. Deep cuts: Webpagetest
	* http://www.webpagetest.org

### Webpagetest features
* Test real browsers from mult. locations
* Modify connection speeds
* Video capture
* Content blocking
* Script the session
* Use with CI
* Collect tests over time
* Free

## Easy web optimization wins
* Web performance budget
	* A budget is a guide, not a hard & fast limit
	* Performance tweaks are compromises
	* http://timkadlec.com/2013/01/setting-a-performance-budget
	* For clients: look at their competitors, look at there pagespeed insights
		* Make sure your site is 25% of the competitors
* Mobile optimization tenets
	* Reduce requests
	* Reduce asset size
	* Speed-up page render
* Web perf & server-size: Easy wins
	* Browser cache
		* Try redbot.org to see if you're caching
	* Compress HTML & CSS
		* If you're using Apache make sure to use mod_deflate
	* Avoid AJAX requests
		* Think criticaly about how you use AJAX
* Web perf & images: easy wins
	* Try to avoid images
		* When possible think about avoiding images
	* Image compression
		* Choose appropriate image formats
	* Responsive images
		* Use srcset to server regular images
	* Avoid dark matter
		* display: none; hides content. It doesnt stop loading it.
* Web perf & images: tools
	* Grunt & Gulp tools
		* imagemin
		* image-resize
		* spritesmith
		* svgmin
	* On the web
		* kraken.io
		* smushit.com
		* spriteme.org
		* imigix.com
* Web perf & JS: easy wins
	* MicroJS or even better, Vanilla
		* Avoid bulky frameworks
		* Try microjs.com to find small libs
	* Avoid DOM reflows & repaints
		* By modding the dom you can cause (unnecessary) reflows & repaints
		* Drains battery
	* Use Touch of FastClick
		* Speed up user interactions by 300ms
	* CDNs
 * Web perf & JS: tools
	* Grunt & Gulp tools
		* uglify
		* concat
		* closure-compiler
		* google-cdn
	* On thw web
		* Microjs.com
		* developer.mozilla.org
		* developers.google.com
* Web perf & 3rd party code: easy wins
	* Beware the SPOF
		* Be careful with 3rd party code. Downtime for them can mean slow loading for you.
		* Try using spof-o-matic
	* Avoid SM widgets
 * Critical rendering path: easy wins
	* Dever loading of JS
		* Place script elements just above body tag
		* Otherwise use HTML4's script defer & async to avaoid blocking the parser
	* Inline Critical CSS & Defer rest
		* Place critical CSS directly within doc and laod the rest after nload with JS
		* Use service like penthouse to find critical CSS
	* Same DNS origin
		* Above the fold elements should be on the same hostname
		* Reduces DNS look-ups
### More web perf tools
* Perf tool list: http://perf-tooling.today
* Google analytics' site speed
* Speedcurve: http://speedcurve.com
* Perfmap (alpha): https://github.com/zeman/perfmap
* Real user testing: https://yahoo.github.io/boomeran/doc/
* mod_pagespeed: perf automation: https://developers.google.com/speed/pagespeed/mod

## Devices
* Remote debugging
* Slowing things down
	* Charles
	* NLC 
* Getting your hands on real devices
	* eBay
	* MobileKarma.com
	* Opendevicelab.com
 
## Q&A with Jake
Q: How http2 change things
A:
* Massively
* Short term: focus on the old tech
* Get basiscs right first

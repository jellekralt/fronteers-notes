# Making Twitter UI infrastructure

Dotfiles
FlightJS
SUITCSS

## A brief history
Lots of apps at twitter
mobile / tweetdeck / analytics / ads / vine

* Web apps at scale are complex adaptive systems
* Web engineering at scale can be expensive
	* Lots of rerepeating
	* Buggy products
	* Everything is connected to everything else
	* Engineering is part of a larger whole
	* Needs are always changing
* Web apps are being commodified at Twitter
* Why are we building apps from scratch* every time
	* *Or cloning parts of each other's apps
* What can we do to enhance expertise?
	* Not only how we build but also how we support
* A project to create a web **UI infrastructure**
 
## 7 guiding principles
1. Solve a **known problem**
	* browser tests
	* unit tests
	* generators
2. Focus on outcomes and process, not tool
3. Design for adaptability, not perfection
	* make it easy to pull stuff and and replace it
4.  Components are the primary unit of scale
	* avoiding to know the entire application
	* Code deletion should be easy
5. Ready-made, not tailor-made
	* When faced with equally great stuff / tools, consistency is key
6. Make skillful use of what is at hand
7. Documentation & ownership over institutioal knowledge
	* Shift away from concept of internal consusltant
	* Docbird
 
> "If HP knew what HP knows, we would be 4 times more profitable" 
> -- Lew Platt, former CEO of HP


## System overview

Node.js
 
* UI components & automatic gallery
* Browser unit/e2e testing
* Asset deploy pipeline
* Localization
* Simple developer workflow
 
Each task is quite huge

```
web-client
|- package.json
|- config
|- lib
|- node_modules
|- script
|- src
```

## UI components
Tweetbox has no specific code, based on a pile of existing components

``` 
web-client/src/web_modules/
|- character-counter
|- product-data-store
|- ui-Button
|- ui-HomePage
|- ui-Icon
|- ui-ProductPage
|- ui-ProgressBar
|- ui-Replybox
```

``` 
web-client/src/web_modules/ui-Icon/
|- OWNERS
|- README
|- index.css
|- index.js
|- index.soy
|- IconView.scala
|- lib
|- test
```

* Owners files are really good
	* Responsibility
	* Mentoring
	* Review tools can use

**Karma** for unit tests
```*.spec.unit.js```

**The intern** for e2e tests
```*.spec.e2e.js```

### Webdriver API

```
this.remote
	.get(homepageUrl)
	.findByClassNmae('Signup-name')
	.click()
	.type('necolas')
	.end()
```

### Component Object Design
```
Homepage.signup = Signup

Homepage.signup.username('necolas');
Homepage.signup.password('****')
Homepage.signup.submit()
```

## Asset pipline
**Webpack** module bundler
Allows you to do a lot of custom work on asset graph
Webpack builds a dependency graph of all your front end assets
Common chunk: Pull out all common code to provide caching on common file
Support for localization 

## Developer workflow
Creat habits across teams

```
make install
make build
make test
make start
make client-start
make client-ui-module name="Icon"
```

## Recap
1. Solve a known problem
2. Focus on outmoces and processes
3. Design for adaptability
4. Components as the unit of scale
5. Ready-made
6. Use what is at hand
7. Documentation & ownership

## Blackboxing
Scientific and technical work is made invisible by its own success -- Bruno Latour, philosopher and sociologist of science

## Q&A with Jake
How do we share these components between applications
* Very difficult
* Versioning
* How to property encasuplate it

* Linter checks for scoping in JS to prevent problems when combining different components
* We use BEM to provide component root structure with modifiers 
* For our scale of the apps we cant have comments marking op structure
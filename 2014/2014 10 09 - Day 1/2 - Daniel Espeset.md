# Making maps, the role of Frontend Infrastructure at Etsy
Resources available at: http://talks.desp.in/fronteers2014

Engineering at Etsy
* **Anybody** can touch **anything**
	* Any engineer at Etsy can change anything about everything
* **Blameless** postmortems 
	* Leads to better
		* Alerts
		* Quality
		* etc
* **Everyone** deploys
	* Designers are included

Works because of continues deployment

First one to join is the driver in deploy
Deployinator

Supergrep++ watches deploy logs on the fly

The smallest possible change that can be pushed, should be pushed

## Continuous Experimentation
Data driven products
Keep refining after A/B tests until good for release
Adding experiments gets really easy
Common to run dozen experiments at the same time

## TL;DR
* Engineers are trusted and have massive access
* The production codebase is contstantly changing
* That codebase is filled with experiments
 

* Deleting code is often scary
* Testing changes is difficult

## Frontend infastructure

## Builda
* Node.js
* Wraps RequireJS AMD compiler
* Parallelizes work across CPU cores
* Servers fully compile assets on development VMS
*Takes about 2 minutes*

Techniques for severing build assets in dev
* ~~build on the fly in respons to HTTP requests for assets files~~
* ~~Watch FS for any changes and rebuild everything~~
* Watch FS for any changes and only rebuild affected targets
**This is.. complicated**
 
Something valuable:The set of file that **aren't used**

# Shrinkray
* Script that analyses client side CSS
* Pick a stylesheet loaded on the page
* Randomly pick 50 selectors via CSSOM
* search for matches with document.querySelector
* send results to server
* Aggregate data with Map reduce
 
## Moving to SCSS
### Currently
* Existing preprocessor inlines @import versions images
* Linted for synax (sorta) 
	* Super tolerant atm
 
### Resricting SCSS func
* No @extends ever
* No @mixins (for now)
* Nesting leven < 4
* Lints to enforce these

### Converter script
* @import statements needed changed
* Converterr fixes 171,244 scss lint errors
* Had to resolve hundreds of invalid CSS
 
* Browsers don't care about errors
* SCSS does care
* Will fixing these errors break something?
 
## Whats next?
Shrinkray for Javascript
Error handling
Will be open sourcing a lot
Want to make more better style guides

## Q&A with Jake
One of the reason to doubt the implementation of SASS is the emphasis on the accessibility for everybody to change anything.

"We don't merge branches out of pull requests"





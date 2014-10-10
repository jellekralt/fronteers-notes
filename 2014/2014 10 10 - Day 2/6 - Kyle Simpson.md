# Choose your own JS adventure
Devs: "Hell is other people's code."
Kyle: "Hell is not understanding my own code."

http://YouDontKnowJS.com

* We often blame the toolset
* "less" standards, better tools
 
What if your team didn't have to agree?
* [configurable 2-way code formatting](https://github.com/getify/esre)

> What if you could customize JS to your own liking?

As a developer: Figure out the toolset

## Sweetjs.org
*JS Macros*

## Beyond macros
* Block scoping
 
> Please do not find & replace all var's by let's, that's incredibly stupid.

* Promiscuous this binding
* hard this binding
* soft this binding
 
## Team collaborating?
* Inversible transforms
	* All examples have two way bindings
	* Two different rulesets
	* Code shows different based on rulesets for every other developer
 
## Existing tools
* Esprima / acorn (parser)
* Escodegen (code generator)
* escope / eslevels (scope analyzer)
* istanbul (code coverage)
* estraverse (analyze AST)
* eslint (pluggable code linting rules)
* plato/jscomplexity.org (complexity)
 
## You could
* Auto-correct misspellings
* safely re-arrange scope
* consolidate delcarations
* automatically reduce complexity
* refactor boolean traps
* optimize performance
 
* restrictmode.org
 
## Q&A with Jake
Q: How debuggable is it?
A:
* Depends on how great the tool is
* Sourcemaps

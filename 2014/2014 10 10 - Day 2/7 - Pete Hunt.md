# Scaling up & down: Evolving your testing strategies

Authbox

> Functional quality means that the software correctly performs the stasks it's intended to do for its users -- David Chappell

> Structural quality means that the code itself is well structured -- David Chappell

** Improve process quality to improve functional quality**

## The three Questions
* Is there a defect (bug, missing feature, etc)?
* How bad is the defect?
* How can we fix this defect?
 
## Agile development

```
+-------------------------------------------------------------------------------->
Unknown								Known
Concept -> Prototype -> Feature development -> Production
```

## How can we answer The Three Questions?
* System design
* Code review (pre-commit)
* Audits (post-commit)
* Static analysis (type systems, linting, etc)
* Runtime assertions
* Production monitoring
* Unit tests
* Integration tests
* Manual QA
 
## How do these fit in with agile development?
* Premature unit tests yield lots of false positives
* Reliance on integration tests yield lots of false negatives

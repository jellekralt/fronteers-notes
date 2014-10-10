# Animating SVGs with CSS and SMIL
* Using CSS
* Using SVG animations (SMIL)
* Using JavaScript
 
## CSS'ing SVGs
Before CSS: SVG persentation attrs
```
<polygon fill= "#000000" stroke = "#CCCCCC" 
```
In SVG2, more presentation attributes will be added

* Inline styles (style="")
* Embedded styles (```<style/>```) inside SVG
* Embedded styles (``` <style/> ```) outside SVG
* External Style Sheet
 
## Animating SVGs with CSS
HTML has box model, SVG does not know the element box model

### LImitations
* Animations of attrs such as pos and dimension attrs, among others
* Animations along arbitrary paths (http://dev.w3.org/fxtf/motion-1)
* Morphing paths / shape tweening.
 
## Embedding SVGs
* src="mysvg.svg"
* url(mysvg.svg)
* object
* embed
* iframe
* ```<svg></svg>```
 
## Animating SVG with SMIL
Synchonized Multimedia Integration Language
* Define an XML based language that allows auths to write interact multimedia presos
 
### Why?
SMIL has some advantages over CSS and JS
* Can anim attrs that CSS can't
* Event handling & animi sync capabilities
* Anims work when SVG is embedded as <img> or as backgr image in CSS
 
SVG SMIL anims work in **all browsers** except IE and Opera Mini

[Right about here i gave up trying to note down all the technical implementation details]







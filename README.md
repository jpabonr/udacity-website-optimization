## Getting Started
Access the website here: https://jpabonr.github.io/udacity-website-optimization/


## Optimization Procedures Applied to The Website

### Part 1: PageSpeed Insights score optimization for index.html

1. Inlined all redender-blocking CSS code (relevant to above-the-fold-content).
2. Added asynchronous web font loading by using async attribute and implementing a web font loader.
3. Added asynchronous loading of non-critical scripts (perfmatters.js, Google Analytics) by using async attribute.
4. Minimized index.html


### Part 2: Animation optimization of views/js/main.js (for pizza.html)

1. Decoupled animation loop from scroll event handler.  

   Instead of firing up the updatePositions function (which includes the animation loop) every time there's a scroll event, 
   the last scroll position is stored and the function is managed by rAF.  This known design pattern for handling animations 
   triggered by scroll events was sourced from https://developer.mozilla.org/en-US/docs/Web/Events/scroll.

2. Replaced getElementById with getElementsByClassName to fetch DOM elements faster.

3. Limited the number of pizza images being animated to those visible on screen (from 200 to 30).
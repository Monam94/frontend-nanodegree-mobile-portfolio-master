# Website Performance Optimization portfolio project

This was the fourth project in the _Front-End Web Developer Nanodegree_. The objective was to 1) optimize the critical rendering path for the existing [main index.html] page and 2) optimize the browser rendering for the existing [Cam's Pizzeria page]

## Getting Started

### What You'll Need

A Web browser.

### Running the Site
you can run the files locally by doing the following:

1. Download the .zip file using the **Download ZIP** button located in the GitHub sidebar (or clone the repository).
2. Unzip the file
3.  Point your browser to **index.html** in the **src** folder to run the same files found on the live site.

## CRP Optimizations

The [main page] was optimized to achieve a PageSpeed Insights speed score of at least 90/100 for Mobile and Desktop. The current iteration achieves a 95/100 for Mobile and a 97/100 for Desktop running on GitHub Pages, and a 99/100 for Mobile running on a server that accepts .htaccess modifications for caching.

## Browser Rendering Optimizations

The goal was to optimize the [Cam's Pizzeria page] (views/pizza.html) to maintain 60 FPS or higher during scrolling of the page (as tested in Chrome DevTools) and to reduce the time for the pizza slider to resize the pizza in the pizza list to under 5ms.

### Optimizations

Following is a list (as required for the project) of optimizations made to **views/pizza.html**—specifically to js/main.js in that same folder. These changes are all commented in the source code (src/) preceded with "OPTIMIZATION:".

*changePizzaSlices* - This function updates the size of the pizza in the pizza list on change of the slider.

* Stored the results of document.querySelectorAll() so it doesn't have to be called in each iteration of the subsequent loop.
* Moved setting of style.width to a separate loop following the loop doing calulations using offsetWidth, to avoid layout thrashing.

*updatePositions* - This function updates the positioning of the pizzas in the background during scroll.

* Replaced style.left with style.transform and used translate3d to remove the need to do layout and paint for those elements
* Removed pizzas that we never see from the Render Tree, and only calculated transforms for those we do see.
* Moved a calculation using body.scrollTop out of a loop and used a var containing that value in the loop instead to avoid having to recalculate layout through each iteration.
* Replaced use of querySelectorAll() with getElementsByClassName()
* Replaced expression using modulo operator with a simple counter var

*other changes*

* stored a few location values in custom properties in the pizza elements, to avoid having to calculate layout to get them
* created a new PNG for the background pizzas that matched the size at which they were being used



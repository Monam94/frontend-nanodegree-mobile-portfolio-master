# frontend-nanodegree-mobile-portfolio-master
The goal was to optimize a given website so that each page reaches a page speed of at least 90 measured with Page Speed Insights.

Optimizations made in main.js for pizza.html:

1-replaced querySelectorAll with getElementsByClassName for better performance.

2-moved "document.body.scrollTop / 1250" outside the for loop.

3-reduced the amount of animated pizzas from 200 to 20.

4-moved calculation of "dx" and "newwidth" outside the for loop in function "changePizzaSizes" and assigned all the elements from "document.getElementsByClassName("randomPizzaContainer")"" to a variable "pizzaContainers"

5-dynamically calculate the total amount of animated pizzas dependent on window width

6-replaced "querySelector(..)" with "getElementById(..)"

# CSS Box Model
## Understanding how to calculate the total width & height of an element using the Box Model.

CSS Box Model is a very important topic that need to be understand correctly as it is established that html elements are in boxes and understanding how the CSS box model works is crucial to getting the exact height and width of an element and is also a vital key in creating complex layout with CSS.

It is said that everything in CSS is surrounded with box, as a beginner I struggled to understand this concept and I'm certain there might be people starting out with CSS and having tough time grasping this concept, it might also be that you needed a quick refresher I hope this short article will be useful.

My believe is that you have a basic CSS knowledge since this article is not about CSS  

## A quick refresher on Block & Inline

- The box model consist of the margin, border, padding and the content
		- When a width is set, it is always for the content and not for the total width
		- To get the total width of an element, the summation of
			- width
			- left & right padding
			- left & right border
			- left & right margin
		- To get the total height of an element, is the summation of 
		- height + top & bottom padding + top & bottom border + top & bottom margin
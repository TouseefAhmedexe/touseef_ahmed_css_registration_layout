# Registration Page Layout

An intern registration page with a form and a schedule table, built with HTML and CSS
(traditional layout, no Flexbox, no Grid, no JavaScript).
Task 7 of my Bloomrix internship.

## Files
- index.html - the page
- style.css - all the styling

## Why box-sizing: border-box is used on every element
With the default content-box, the width of an element does not include its padding and
border. A field with width: 100% plus padding was wider than its parent and stuck out of
the fieldset. With border-box the width includes the padding and border, so the width I
write is the width I get.

## Problems found with DevTools
1. Box model: the form fields and the container were wider than their parents. In the
   Computed tab the box-model diagram showed width plus padding plus border. Fixed with
   * { box-sizing: border-box; }
2. Float: the dashed box around the two columns collapsed to a thin line because floated
   children take no space in the parent. The Elements panel showed a height of 4px.
   Fixed with a ::after rule that uses clear: both.
3. Positioning: the status badge was not on the card. It was positioned against the page
   because no parent was positioned. Fixed with position: relative on .info-card.

## display: none and visibility: hidden
display: none removes the element and its space. visibility: hidden hides the element but
keeps its space, so a gap stays in the page.

## z-index
The navigation (z-index 100) stays above the page content while scrolling. The status
badge (z-index 2) is above the info card. In the stacking demo, the first box (z-index 2)
stays above the second box (z-index 1) although the second comes later in the HTML.

## How to run
Open index.html with Live Server in Visual Studio Code, or in any web browser.
# Uncommon HTML Bug: Race Condition in innerHTML

This repository demonstrates a subtle bug related to setting the `innerHTML` property of an HTML element before the element has been fully parsed by the browser. This can lead to unexpected behavior or errors, especially when dealing with images or other resources that require additional processing.

## The Bug

The `bug.html` file contains a simple HTML page with a div element. A JavaScript script attempts to modify the `innerHTML` of the div.  However, because the script executes before the browser has fully parsed and rendered the DOM, setting the `innerHTML` may not have the desired effect.

## The Solution

The `bugSolution.html` file demonstrates a corrected approach.  The JavaScript code is placed within a `DOMContentLoaded` event listener which ensures the script executes only after the entire document is loaded and parsed.

## How to reproduce

1. Clone this repository.
2. Open `bug.html` in a web browser.
3. Observe that the second paragraph is not correctly displayed and the image is not loaded due to race conditions.
4. Open `bugSolution.html`. Note that the content is now loaded correctly, and the image displays if the image path is correct. 

This example highlights the importance of understanding the browser's rendering process and timing considerations when manipulating the DOM.
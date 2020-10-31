# <%= EJS %> :

What is the "E" for? "Embedded?" Could be. How about "Effective," "Elegant," or just "Easy"? EJS is a simple templating language that lets you generate HTML markup with plain JavaScript. No religiousness about how to organize things. No reinvention of iteration and control-flow. It's just plain JavaScript.

## Features :

* Fast compilation and rendering
* Simple template tags: <% %>
* Custom delimiters (e.g., use [? ?] instead of <% %>)
* Sub-template includes
* Ships with CLI
* Both server JS and browser support
* Static caching of intermediate JavaScript
* Static caching of templates
* Complies with the Express view system

## Get Started :

`$ npm install ejs`

`let ejs = require('ejs');`
`let people = ['geddy', 'neil', 'alex'];`
`let html = ejs.render('<%= people.join(", "); %>', {people: people});`

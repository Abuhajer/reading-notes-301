# Regex 

![Regex](https://res.cloudinary.com/practicaldev/image/fetch/s--O0siYdEi--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/i/dbnauyuy7y1o3k839iny.png)
Regular expressions (regex or regexp) are extremely useful in extracting information from any text by searching for one or more matches of a specific search pattern (i.e. a specific sequence of ASCII or unicode characters).
Fields of application range from validation to parsing/replacing strings, passing through translating data to other formats and web scraping.
One of the most interesting features is that once you’ve learned the syntax, you can actually use this tool in (almost) all programming languages ​​(JavaScript, Java, VB, C #, C / C++, Python, Perl, Ruby, Delphi, R, Tcl, and many others) with the slightest distinctions about the support of the most advanced features and syntax versions supported by the engines).

## Flags
We are learning how to construct a regex but forgetting a fundamental concept: flags.
A regex usually comes within this form /abc/, where the search pattern is delimited by two slash characters /. At the end we can specify a flag with these values (we can also combine them each other):
g (global) does not return after the first match, restarting the subsequent searches from the end of the previous match
m (multi-line) when enabled ^ and $ will match the start and end of a line, instead of the whole string
i (insensitive) makes the whole expression case-insensitive (for instance /aBc/i would match AbC)



# Grid
![Grid](https://xd.adobe.com/ideas/wp-content/uploads/2020/04/css-grid-layout-tutorial.jpg)
CSS Grid Layout is the most powerful layout system available in CSS. It is a 2-dimensional system, meaning it can handle both columns and rows, unlike flexbox which is largely a 1-dimensional system. You work with Grid Layout by applying CSS rules both to a parent element (which becomes the Grid Container) and to that

Defines the element as a grid container and establishes a new grid formatting context for its contents.
`.container {`
  `display: grid | inline-grid;`
`}`
Defines the columns and rows of the grid with a space-separated list of values. The values represent the track size, and the space between them represents the grid line.
`.container {`
  `grid-template-columns:  ... |   ...;`
  `grid-template-rows:  ... |   ...;`
`}`
Defines the columns and rows of the grid with a space-separated list of values. The values represent the track size, and the space between them represents the grid line.

`.container {`
  `grid-template-columns: [first] 40px [line2] 50px [line3] auto [col4-start] 50px [five] 40px [end];`
  `grid-template-rows: [row1-start] 25% [row1-end] 100px [third-line] auto [last-line];`
`}`
# Common Responsive Layouts with CSS Grid

CSS grid is now supported in Samsung internet v6.2 and many other modern browsers and has been the answer to many a prayer of web developers everywhere. In the same way that flexbox gave us a way to layout block elements next to each other, CSS grid lets us not only arrange elements in a row or a column, but in multiple rows and columns. Finally two dimensional layouts are becoming simpler!
When I was learning CSS and HTML the way that I learnt best was by copying layouts written by others and then changing bits, deleting bits and playing around with them until I understood what was going on. With that in mind, I’ve composed a few common responsive website layouts for you to copy, edit, mess around with. I’ll go over my thinking with each layout and will outline a few tricks from each one. (NB, you may have noticed that I’m not a designer, so I hope you like cats!). I’ve moved the CSS in each demo that is relevant to the layout up to the top of the CSS file in comment blocks so that you can see the important parts easily, don’t write your CSS like this.

This is a responsive template that you’ll see all over the web, a large intro image followed by smaller images, buttons or articles. Have a look at the code from the glitch link above.
The smaller images (in a grid!) are in the perfect layout to get you started with CSS grid. Grid gives us control over how wide or narrow each of the ‘grid cells’ get. This allows us to maintain a sensible aspect ratio to their height. In this example I’ve used:

grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));

`column-count: 2;`
`column-gap: 20px;`


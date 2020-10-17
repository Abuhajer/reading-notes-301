## CSS Responsiveness
With the advancement of mobile phones, people started to access web pages through the mobile phones more often. It was really important to come up with a way to make the web pages adaptable with all screen sizes so it will give the user the best experience.
Responsive web design is broken down into three main components, including *flexible layouts*, *media queries*, and *flexible media*.
1.The first component is flexible layout which means that instead of specifying width and height using the pixels, they are specified using the `percentages` and `em`. So it will be relative to the parent element and to the width of the screen.
The problem with this component is that sometimes the element becomes too small to read so they use other components for this purpose.
2.The second component is the media queries which are linked to the css files. You can include the media queries using two ways; the @media rule inside of an existing style sheet, or by linking to a separate style sheet from within the HTML document. Each media quire includes a media type which might be `all`, `screen`, `print`, `tv`, and `braille`. If the media type is not specified, the default type will be `screen`. Media values follow the type and they could be true or false. If they allocate to be true, the media quire is applied.
**Logical Operators in Media Queries**
`and` all of the media queries are applied.
`not` any quire can be applied except for the one specified.
`only` applies the specified quire only.
When the media queries are separated by a comma, then an `or` is implied and only one is applied.
**Media Queries Height and Width Features**
Within responsive design the most commonly used features include `min-width` and `max-width`. These help build responsive websites on desktops and mobile devices equally, avoiding any confusion with device features.
**Orientation Media Feature**
Orientation media feature is very important when it comes to mobile devices. It can be landscape oriented which means that the height is less that the width. Or it is portrait; the width is less than the height.
**Aspect Ratio Media Features**
You can specify the minimum and maximum of the width and height of pixels.
**Mobile First**
This method uses styles targeted to smaller devices and then applies the necessary styles for bigger viewports and that’s the optimal option for websites to be light when are used on mobiles.
**Viewport**
When mobile phones display websites, they sometimes need the assistance of identifying the viewport. You can specify the size, scale, and resolution of a viewport. In the head of the HTML file, we use the `meta` tag to identify the viewport as the default *width and height* of the device.
3.the second component is *flexible media*.
Images, videos, need to be scalable, changing their size as the size of the viewport changes. This can be done by giving the media a `max-width` of 100% so that the media will be relative to its container.
## Floats
Originally, the float property is used for print layouts where there is an image and a text wrapped around it.
When we change the size of the image when using the float property, the text will change its position to wrap around the image. This does not happen when we use relative and absolute positioning.
The float property now has a wider range of uses and it can be used to create an entire page layout.
You can clear the float for other elements so they are not affected by it using `clear: both`.
When a container contains floated elements, it usually collapses and its height becomes small but it can be fixed by clearing the float before the close of the container.
There are different techniques to *clear the float* of an element other than using clear: both property.
**The Empty Div Method**
**The Overflow Method**
**The Easy Clearing Method**
### Problems with Floats:
Pushdown
Double Margin Bug
3px Jog
Bottom Margin Bug
## Grids
While many programmers think that the grids are complicated and they try not to get into it, it is very simple but you need to know what it means first.
To create a web layout using the grid, you need to give the container a 100% width and then divide its child elements using percentages as well. Then, you will need to clear the float from the parent so its height is not zero. After that, we need to deal with the gutters, we don’t necessarily need percentages we can give it `box-sizing: border-box` and then give the children padding-right.
## SMACSS (Scalable and Modular Architecture for CSS)
This is a guide from the writer’s experience in designing websites using CSS and the best ways to organize you webpage when you use CSS.
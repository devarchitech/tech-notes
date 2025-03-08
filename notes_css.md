/*
***************************************************** 
1. CSS Selectors
CSS selectors are used to target HTML elements for styling. They range from simple to advanced selectors that can target specific elements or groups of elements based on various criteria. 
*****************************************************
*/

/* Basic Selectors
Universal Selector (*)
Targets all elements on a page. This is often used for resets or applying universal styles. */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Type (Element) Selector
Targets all instances of a specific element (e.g., all <p> elements). */

p {
    font-family: Arial, sans-serif;
    color: blue;
}

/* Class Selector (.)
Targets elements with a specific class attribute. A class can be applied to multiple elements. */

.button {
    background-color: #4CAF50;
    padding: 10px 20px;
    border-radius: 5px;
}

/* ID Selector (#)
Targets an element with a specific id attribute. IDs are unique, so they should only appear once per page. */

#header {
    background-color: #333;
    color: white;
}

/* Attribute Selector
Targets elements based on the presence or value of an attribute. */

input[type="text"] {
    width: 200px;
    padding: 10px;
}

/* Combinators
Descendant Selector (space)
Selects all elements that are descendants of a specific parent. */

.nav ul li {
    display: inline-block;
}

/* Child Selector (>)
Selects only direct children of an element, not deeper descendants. */

.container > p {
    font-size: 18px;
}

/* Adjacent Sibling Selector (+)
Targets an element immediately following a specific element. */

h2 + p {
    margin-top: 0;
}

/* General Sibling Selector (~)
Selects all sibling elements that follow a specific element, not just the immediate sibling. */

h2 ~ p {
    color: grey;
}
/* 
*****************************************************
2. CSS Box Model
The CSS box model describes the rectangular boxes generated for elements, which consist of content, padding, border, and margin. It’s vital to understand this model for spacing and layout control.
***************************************************** */

/* Components of the Box Model
Content: The actual content inside the box (e.g., text or an image).
Padding: The space between the content and the border. Padding is inside the box.
Border: Surrounds the padding (if any) and content.
Margin: The outermost layer, separating the element from others. */

.box {
    width: 300px;
    padding: 20px;
    border: 1px solid #ccc;
    margin: 15px;
}

/* box-sizing Property
The default value for box-sizing is content-box, meaning the width and height only apply to the content, not padding or border. If you want the width and height to include padding and borders, use box-sizing: border-box. */

* {
    box-sizing: border-box;
}

/* *****************************************************
3. CSS Flexbox
Flexbox is a one-dimensional layout model for distributing space along a row or column. It allows for more flexible and dynamic layouts.
This rule makes it easier to manage dimensions of elements, especially in responsive layouts.
***************************************************** */

/* Creating a Flex Container
To activate flexbox, you need to set display: flex on a container. This turns its direct children into flex items. */

.container {
    display: flex;
}

/* Aligning Items in Flexbox
Flexbox provides several properties to align and justify items within the container.

justify-content: Aligns items along the main axis (horizontal by default). Options: flex-start, flex-end, center, space-between, space-around. */

.container {
    justify-content: center;
}

/* align-items: Aligns items along the cross axis (vertical by default). Options: flex-start, flex-end, center, stretch, baseline. */

.container {
    align-items: center;
}

/* flex-direction: Defines the direction of the flex items along the main axis. Options: row, column, row-reverse, column-reverse. */

.container {
    flex-direction: row-reverse;
}

/* flex-wrap: Defines whether flex items should wrap or stay on one line. Options: nowrap, wrap, wrap-reverse. */

.container {
    flex-wrap: wrap;
}

/* Flex Item Properties
flex-grow: Defines how much a flex item should grow relative to the other items (default is 0). */

.item {
    flex-grow: 1;
}

/* flex-shrink: Defines how much a flex item should shrink relative to others (default is 1).
flex-basis: Sets the initial size of a flex item before any growing or shrinking occurs.
flex: A shorthand for flex-grow, flex-shrink, and flex-basis. */

.item {
    flex: 1 1 100px; /* grow, shrink, basis */
}

/* *****************************************************
4. CSS Grid
CSS Grid Layout provides a two-dimensional grid-based layout system, which allows for both rows and columns.
***************************************************** */

/* Creating a Grid Container
To create a grid container, use display: grid. */

.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* Three equal columns */
    grid-gap: 10px;
}

/* Grid Template Columns and Rows
You can define the number of columns and rows:
grid-template-columns: Defines the columns of the grid.
grid-template-rows: Defines the rows of the grid. */

.grid-container {
    grid-template-columns: 200px auto 200px;
    grid-template-rows: 100px 200px;
}

/* Placing Grid Items
You can place items on specific grid lines using grid-column and grid-row: */

.item {
    grid-column: 1 / 3;  /* Spans across columns 1 to 3 */
    grid-row: 1 / 2;     /* Spans across row 1 to 2 */
}

/* Common Grid Properties
grid-gap: Defines the space between rows and columns.
grid-auto-rows: Sets the row size for automatically generated rows. */

/* *****************************************************
5. CSS Transitions
CSS transitions allow you to gradually change property values, adding smooth effects.
***************************************************** */

/* Basic Syntax
You define a transition on a property, and when it changes, the transition effect takes place. */

.box {
    transition: background-color 0.5s ease-in-out;
}

.box:hover {
    background-color: red;
}

/* transition-property: Specifies which property should transition (e.g., background-color).
transition-duration: How long the transition lasts.
transition-timing-function: Specifies the speed curve (e.g., ease, linear, ease-in-out).
Multiple Transitions - You can transition multiple properties at once: */

.box {
    transition: all 0.3s ease-in-out;
}

/* *****************************************************
6. CSS Animations
CSS animations allow you to animate properties over time, creating more complex effects.
***************************************************** */

/* @keyframes - Define the intermediate points of the animation. */

@keyframes move {
    0% {
        left: 0px;
    }

    100% {
        left: 100px;
    }

}

/* animation-name: The name of the animation.
animation-duration: How long the animation lasts.
animation-timing-function: The speed curve.
animation-iteration-count: Number of times the animation runs (infinite for endless). */

.box {
    animation: move 2s ease-in-out infinite;
}

/* ****************************************************
7. CSS Media Queries
Media queries enable you to apply different styles for different screen sizes or devices.
max-width: Styles will apply when the viewport width is 600px or less.
**************************************************** */

/* Basic Media Query Syntax */
@media screen and (max-width: 600px) {
    .container {
        display: block;
    }

}

/* ****************************************************
8. CSS Pseudo-Classes
Pseudo-classes style elements based on their state or position.
**************************************************** */

/* Common Pseudo-Classes
:hover: Applied when an element is hovered over. */

a:hover {
    color: red;
}

/* :first-child, :last-child: Selects the first and last child of a parent element.
   :nth-child(): Selects elements based on their position in the parent. */

li:nth-child(odd) {
    background-color: lightgray;
}


/* ****************************************************
9. CSS Pseudo-Elements
Pseudo-elements allow you to target specific parts of an element's content.
**************************************************** */

/* Common Pseudo-Elements
::before: Inserts content before an element’s content. */

h1::before {
    content: ">> ";
    color: blue;
}

/* ::after: Inserts content after an element’s content. */

h1::after {
    content: " <<";
    color: red;
}

/* ****************************************************
10. CSS Variables (Custom Properties)
CSS variables allow you to store values in reusable custom properties, making your stylesheets more maintainable.
**************************************************** */

/* Declaring and Using Variables */
:root {
    --primary-color: #3498db;
    --secondary-color: #2ecc71;
}

/* --primary-color is a variable that can be reused throughout the CSS. */

.button {
    background-color: var(--primary-color);
    color: var(--secondary-color);
}

/* ****************************************************
11. CSS Color
The color property in CSS is used to set the color of the text or text-related content of an element.

You can specify color in multiple formats, such as:
Named colors (e.g., red, blue, green)
RGB (e.g., rgb(255, 0, 0))
Hexadecimal (e.g., #ff0000)
HSL (e.g., hsl(0, 100%, 50%))
**************************************************** */

/* Using named color */
p {
  color: red;
}

/* Using RGB */
h1 {
  color: rgb(0, 128, 0);
}

/* Using Hexadecimal */
div {
  color: #0000FF;
}

/* Using HSL */
span {
  color: hsl(120, 100%, 25%);
}

/* ****************************************************
12. CSS Background
The background property is a shorthand for setting multiple background-related properties, including background-color, background-image, background-position, background-size, and background-repeat.
**************************************************** */

/* Setting background color */
body {
  background-color: lightblue;
}

/* Setting background image with other properties */
div {
  background: url('image.jpg') no-repeat center center / cover;
}

/* ****************************************************
13. CSS Float
The float property is used to position an element to the left or right of its container, allowing text and inline elements to wrap around it. Float is commonly used for layouts.
**************************************************** */

/* Floating an image to the left */
img {
  float: left;
  margin-right: 15px;
}

/* Floating an element to the right */
div {
  float: right;
  margin-left: 20px;
}

/* ****************************************************
14. CSS Overflow
The overflow property controls what happens if content overflows an element's box. It can have the following values:

visible (default): Content is not clipped and may overflow.
hidden: Content that overflows is hidden.
scroll: Always shows scrollbars, whether content overflows or not.
auto: Shows scrollbars only when the content overflows.
**************************************************** */

/* Hidden overflow */
div {
  width: 200px;
  height: 100px;
  overflow: hidden;
}

/* Scrollable overflow */
section {
  width: 300px;
  height: 150px;
  overflow: auto;
}

/* ****************************************************
15. CSS Display
The display property controls the box model behavior of an element. Common values include:

block: The element takes up the full width available and starts on a new line.
inline: The element only takes up as much width as necessary and does not start on a new line.
inline-block: Behaves like inline but allows setting width and height.
none: The element is not displayed (i.e., removed from the document flow).
**************************************************** */

/* Block element */
div {
  display: block;
}

/* Inline element */
span {
  display: inline;
}

/* Inline-block element */
button {
  display: inline-block;
  width: 120px;
  height: 40px;
}

/* Hiding an element */
header {
  display: none;
}

/* ****************************************************
16. CSS Borders
The border property defines the style, width, and color of an element's border. It is shorthand for border-width, border-style, and border-color.
**************************************************** */

/* Full border */
div {
  border: 2px solid black;
}

/* Border with different properties */
section {
  border-width: 3px;
  border-style: dashed;
  border-color: red;
}

/* Rounded corners */
p {
  border: 1px solid gray;
  border-radius: 10px;
}

/* ****************************************************
17. CSS Box Shadow
The box-shadow property is used to add shadow effects around an element’s box. It can include values for horizontal and vertical offsets, blur radius, spread radius, and color.
**************************************************** */

/* Basic box shadow */
div {
  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.5);
}

/* Inset shadow (shadow inside the element) */
input {
  box-shadow: inset 0 0 5px gray;
}

/* Multiple shadows */
article {
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3), -2px -2px 5px rgba(255, 0, 0, 0.5);
}

/* ****************************************************
18. CSS @font-face
The @font-face rule allows you to define custom fonts that can be used on your website, even if the font is not installed on the user's system. It specifies the location of the font file.
**************************************************** */

/* Defining a custom font */
@font-face {
  font-family: 'OpenSans';
  src: url('OpenSans-Regular.ttf');
}

/* Applying the custom font */
body {
  font-family: 'OpenSans', sans-serif;
}

/* ****************************************************
19. CSS Pagination
CSS pagination is used to manage how content is divided and presented across multiple pages. Although CSS alone can't handle actual pagination logic (like in databases), you can style pagination elements for a more organized display.
**************************************************** */

/* Styling pagination links */
.pagination {
  display: flex;
  justify-content: center;
}

.pagination a {
  padding: 8px 16px;
  margin: 0 4px;
  text-decoration: none;
  background-color: #f0f0f0;
  border: 1px solid #ccc;
}

.pagination a:hover {
  background-color: #ddd;
}

.pagination .active {
  background-color: #4CAF50;
  color: white;
}

/* ****************************************************
20. Responsive Pagination
Responsive pagination ensures that pagination links are displayed in an optimal way across different screen sizes. Typically, this involves adjusting the layout or the number of links shown on smaller screens.
**************************************************** */

/* Pagination for large screens */
.pagination {
  display: flex;
  justify-content: center;
}

.pagination a {
  padding: 10px 20px;
  margin: 0 5px;
  background-color: #ddd;
  text-decoration: none;
}

/* Adjustments for smaller screens */
@media (max-width: 600px) {
  .pagination {
    flex-direction: column;
    align-items: center;
  }

  .pagination a {
    margin: 5px 0;
  }
}

/* ****************************************************
21. Hover, transitions and shadows

/* psuedo class */
selector:hover {
  property value to change the behaviour of the selector
  transition : speed at which the change should occurs
  box-shadow : x y blur color rgba(r, g, b, opacity)
}


**************************************************** */
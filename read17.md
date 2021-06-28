# HTML & CSS
## layout
- CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or an inline box.
  - Block-level elements start on a new line
  - Inline elements flow in between surrounding text
- Containing Elements :If one block-level element sits inside another block-level element then the outer box is known as the containing or parent element
  - It is common to group a number of elements together inside a `<div>`
- CSS has the following positioning schemes that allow you to control the layout of a page: 
  - normal flow:Every block-level element appears on a new line, causing each item to appear lower down
  - relative positioning:This moves an element from the position it would be in normal flow, shifting it to the top, right, bottom, or left of where it would have been placed.
  - absolute positioning:This positions the element in relation to its containing element (it does not affect the position of any surrounding elements).
- **box offset** properties to tell the browser how far from the top or bottom and left or right it should be placed.
  - Fixed Positioning : Elements with fixed positioning do not affect the position of surrounding elements and they do not move when the user scrolls up or down the page.
  - Floating Elements : Floating an element allows you to take that element out of normal flow and position it to the far left or right of a containing box
- The *z-index* property allows you to control which box appears on top.
- Relative positioning moves an element in relation to where it would have been in normal flow.
- When the position property is given a value of absolute,the box is taken out of normal flow and no longer affects the position of other elements on the page.
  - Fixed positioning is a type of absolute positioning that requires the position property to have a value of fixed
- we can Use Float to Place Elements Side-by-Side
- float values :
  - clear: to say that no element should touch the left or righthand sides of a box.
  - left: The left-hand side of the box should not touch any other elements appearing in the same containing element.
  - right: The right-hand side of the box will not touch elements appearing in the same containing element.
  - both: Neither the left nor right-hand sides of the box will touch elements appearing in the same containing element.
  - none: Elements can touch either side.
- parents of Floated Elements Problem :
  - If a containing element only contains floated elements, some browsers will treat it as if it is zero pixels tall
- solution :
  - adds two CSS rules to the containing element :
    - The overflow property is given a value auto.
    - The width property is set to 100%.
- Many web pages use multiple columns in their design. This is achieved by using a `<div>` element to represent each column. The following three CSS properties are used to position the columns next to each other:
  - width This sets the width of the columns.
  - float This positions the columns next to each other.
  - margin This creates a gap between the columns.
- Different visitors to your site will have different sized screens that show different amounts of information, so your design needs to be able to work on a range of different sized screens.
- **Resolution**: refers to the number of dots a screen shows per inch
- the higher the resolution, the smaller the text appears.
- designers assumed that users would see the top 570-600 pixels of a page without having to scroll and some tried to fit all of the key messages in this area
- The area of the page that users would see without scrolling was often referred as being “above the fold”
- **Liquid layout**: designs stretch and contract as the user increases or decreases the size of their browser window. They tend to use percentages.
  - The liquid layout uses percentages to specify the width of each box so that the design will stretch to fit the size of the screen.
- To create a fixed width layout,the width of the main boxes on a page will usually be specified in pixels

- Many designers use a grid structure to help them position items on a page, and the same is true for web designers
- Grids set consistent proportions and spaces between items which helps to create a professional looking design.
- CSS Frameworks :aim to make your life easier by providing the code for common tasks, such as creating layout grids, styling forms, creating printer-friendly versions of pages and so on. 
  - You can include the CSS framework code in your projects rather than writing the CSS from scratch
  - ADVANTAGES :
    1- They save you from repeatedly writing code for the same tasks.
    2- They will have been tested across different browser versions
  - disadvantages :
    1- They often require that you use class names in your HTML code that only control the presentation of the page
    2- In order to satisfy a wide variety of needs, they often contain more code than you need for your particular web page
- **960.gs ** :provides a style sheet that you can include in your HTML pages
- The 960.gs style sheet has taken care of the layout, creating the correct width for the columns and setting the spaces between them.
***960.gs rule*** :
  - Control the font and the position of the text in the boxes
  - Set the background colors for the boxes
  - Set the height of the feature and article boxes
  - Add a margin to the top and bottom of each box

- There are two ways to add multiple style sheets to a page:
  - use the @import rule to import other style sheets.
  - you can use a separate `<link>` element for each style sheet.
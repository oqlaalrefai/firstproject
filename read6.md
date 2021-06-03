# css
+ its stand for Cascading Style Sheets
+ is a language for specifying how documents are presented to users — how they are styled, laid out, etc.
+ allows you to create great-looking web pages
+ you can control exactly how HTML elements look in the browser, presenting your markup using whatever design you like.

CSS can be used for very basic document text styling,create layout,and It can even be used for effects

### **CSS syntax**
CSS is a rule-based language — you define rules specifying groups of styles that should be applied to particular elements or groups of elements on your web page

html-tag {property : value;}
**The rule opens with a selector**:
ex : h1 {
    color: red;
    font-size: 5em;
	} '''
A CSS stylesheet will contain many such rules

**CSS Modules**
the language is broken down into modules. You'll see reference to these modules

#### CSS Specifications :
CSS is developed by a group within the W3C called the CSS Working Group

#### **Getting started with CSS**

+ **external file** :
Create a file in the same folder as your HTML document and save it as styles.css
To link css file to html file:
<link rel="stylesheet" href="styles.css">

+ **inline style** :inside opening tag
ex : <p style="color:red;to add another styling">content</p>

+ **internal style**
we put in the head:
<style>p{add styling features}</style> 

+ **css color** 
The color property specifies the color of text.
we can add the color value using:
  - hsl value : body {color: hsl(89, 43%, 51%);}
  - rgb value :body {color: rgb(201, 76, 76);}
  - rgba value :body {color: rgba(201, 76, 76, 0.6);}
  - HEX value :body {color: #92a8d1;}
  - HSLA value:body {color: hsla(89, 43%, 51%, 0.6);}  

### CSS Tools: Reset CSS
The goal of a reset stylesheet is to reduce browser inconsistencies in things like default line heights, margins and font sizes of headings, and so on
+ appear in CSS frameworks, and the original "meyerweb reset" found its way into Blueprint, among others.


+ **syntax cases**
  + Grouping selectors
Selector list A, B
Specifies that both A and B elements are selected.
  + Combinators
Combinators are selectors that establish a relationship between two or more simple selectors, such as "A is a child of B" or "A is adjacent to B."
  + Adjacent sibling combinator A + B
Specifies that the elements selected by both A and B have the same parent and that the element selected by B immediately follows the element selected by A horizontally.
  + General sibling combinator A ~ B
Specifies that the elements selected by both A and B share the same parent and that the element selected by A comes before—but not necessarily immediately before—the element selected by B.
  + Child combinator A > B
  B is the direct child of the element selected by A.
  + Descendant combinator A B
  B is a descendant of the element selected by A,
  + Column combinator A || B
  B is located within the table column specified by A

### Pseudo
+ Pseudo classes :
Specifies a special state of the selected element(s).
+ Pseudo elements ::
Represents entities that are not included in HTML.



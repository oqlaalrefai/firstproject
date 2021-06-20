How People Access the Web:
  + Browsers: People access websites using software called a web browser.
  + Web Servers: When you ask your browser for a web page, the request is sent across the Internet to a special computer known as a web server which hosts the website.
  + Screen readers: Screen readers are programs that read out the contents of a computer screen to a user. They are commonly used by people with visual impairments.

When you are looking at a website, it is most likely that your browser will be receiving HTML and CSS from the web server that hosts the site.
Small websites are often written just using HTML and CSS.
Larger websites — in particular those that are updated regularly and use a content management system (CMS), blogging tools, or e-commerce software — often make use of more complex 
technologies on the web server, but these technologies are actually used to produce HTML and CSS that is then sent to the browser.
Since the web was first created there have been several versions of HTML and CSSAt the time , HTML5 & CSS3 were still being developed.
###How the Web Works:
When you visit a website, the web server hosting that site could be anywhere in the world. In order for you to find the location of
the web server, your browser will first connect to a Domain Name System (DNS) server.



## HTML 
+ stands for HyperText Markup Language The HyperText part refers to the fact that HTML allows you to create links that allow visitors to move from one page to another
+ describes the structure of a web page
The use of headings and subheadings in any document often reflects a hierarchy of information.
The HTML code (in blue) is made up of characters that live inside angled
### **HTML elements**
The HTML code (in blue) is made up of characters that live inside angled brackets
Each HTML element tells the browser something about the information that sits between its opening and closing tags.
made up of two tags: an opening tag and a closing tag.
<opening tag>info</closing tag>
Tags act like containers. They tell you something about the information that lies between their opening and closing tags.
<html> tag indicates that anything between it and a closing tag is HTML code </html> 
<body> tag indicates that anything between it and the closing tag should be shown inside the main browser window.</body>
<h1>main heading </h1>
<h2>This is a Sub-Heading</h2>
<p>is the paragraph</p>
**The characters in the brackets indicate the tag's purpose.**
#### Attributes 
  + Tell Us More About El ements
  + They appear on the opening tag of the element and are made up of two parts: a name and a value,separated by an equals sign.
	Here an attribute called lang is used to indicate the language used in this element.
	ex:	<p lang="en-us"> *lang is attribute name and "en-us" is Attribute Value*
The attribute name indicates what kind of extra information it should written in lowercase
The value is the information or setting for the attribute. It should be placed in double quotes.
a few attributes (such as lang) can appear on any element.
+ <head>
Before the <body> element you will often see a <head> element.
This contains information about the page (rather than information that is shown within the main part of the browser
+ <title>
The contents of the <title> element are either shown in the top of the browser, above where you usually type in the URL
  + You will usually find a <title> element inside the <head> element.
*** to create a webpage on pc :
open notepad and type the code that you want then go to save as and type the name with html extension(file_name.html)
### Content Management System
+ The tools provided in the administration sections of these sites usually allow you to edit parts of the page rather than
	the entire page, which means you will rarely see the <html>, <head>, or <body> elements.
The advantage of this approach is that people who do not know how to write web pages can add information to a website
and it is also possible to change the presentation of something in the template, and it will automatically update every page
that uses that template.

+ Some content management systems offer tools that also allow you to edit the template files.

Text editors usually have controls a little like those on your word processor, giving you different options to style text, add links or insert images.

### Looking at How Other sites are Built
just go to the page you want and then right click then click on view source and you'll see the source code
its way to learn about HTML and discover new tips and techniques was to look at the source code

each web page should begin with a DOCTYPE declaration to tell a browser which version of HTML the page is using
<!DOCTYPE html>
##### Comments in HTML 
<!-- --> that will not be visible in the user's browser
It is a good idea to add comments to your code because,no matter how familiar you are with the page at the time of writing it, when you come back to it later comments will make it much easier to understand

#### ID Attribute
- Every HTML element can carry the id attribute
- It is used to uniquely identify that element from other elements on the page. Its value should start with a letter or an underscore
- giving an element a unique identity allows you to style it differently than any other instance of the same element on the page.
- id attributes can be used to allow the script to work with that particular element.
- The id attribute is known as a global attribute because it can be used on any element.

#### Class Attribute
- to identify several elements as being different from the other elements on the page
- does not affect the presentation of an element. It will only change their appearance if there is a CSS rule that indicates it should be isplayed differently.

#### Block Elements
- Some elements will always appear to start on a new line in the browser window. These are known as block level elements.

#### Inline Elements
Some elements will always appear to continue on the same line as their neighbouring elements.

#### Grouping Text & Eleme nts In a Block
- <div> element allows you to group a set of elements together in one block-level box.
- it easier to follow your code if you have used <div> elements to hold each section of the page.

- CSS style rules to indicate how much space the <div> element
should occupy on the screen and change the appearance of all the elements contained within it.

#### Grouping Text & Eleme nts Inline
- **<span>** It is used to:
  - Contain a section of text where there is no other suitable
element to differentiate it from its surrounding text
  - Contain a number of inline elements
  - the reason why people use <span> elements is they can control the appearance of the content of these elements using CSS.
  - You will usually see that a class or id attribute is used with <span> elements

#### IFrames
- <iframe>
  - An iframe is like a little window that has been cut into your page — and in that window you can see another page.
  - The term iframe is an abbreviation of inline frame.
  - There are a few attributes that you will need to know to use it :    - src:the URL
	    - height:height of the iframe in pixels.
	    - width:the width of the iframe in pixels.
	    - scrolling:The scrolling attribute will not be supported in HTML5,It can take one of three values: yes (to show scrollbars), no (to hide scrollbars) and auto (to show them only if needed).
	    - frameborder:not be supported in HTML5 it indicates whether the frame should have a border or not A value of 0 indicates that no border should be shown. A value of 1 indicates that a border should be shown.
	    - seamless:can be applied to an iframe where scrollbars are not desired.does not need a value,Older browsers do not support the seamless attribute.

#### Information About Your Pages
##### <meta> :
- lives inside the <head> element and contains information about that web page.
- It is not visible to users but fulfills a number of purposes such as telling search engines about your page, who created it, and whether or not 
- it is time sensitive.
- its empty element so it does not have a closing tag. It uses attributes to carry the information
- The most common attributes are the name and content attributes,These attributes specify properties of the entire
page 
- The value of the name attribute can be anything you want it to be. Some defined values for this attribute that are commonly used are:
  - description:This contains a description of the page.
  - keywords:This contains a list of comma separated words that a user might search on to find the page.

  - robots:This indicates whether search engines should add this page to their search results or not.A value of noindex can be used if this page should not be added.A value of nofollow can be used if search engines should add this page in their results but not any pages that it links to.
- The <meta> element also uses the http-equiv and content attributes in pairs:
  - author: This defines the author of the web page.
  - pragma: This prevents the browser from caching the page.
  - expires: Because browsers often cache the content of a page, the expires option can be used to indicate when the page
should expire. Note that the date must be specified in the format shown.

#### Escape Characters
When using escape characters,it is important to check the page in your browser to ensure that the correct symbol shows up. This is because some fonts do not support all of these characters
*ex:*
< => &lt;&#60;
& => &amp;&#38;
HTML5 introduces a new set of elements that allow you to divide up the parts of a page. The names of these elements indicate the kind of content you will find in them. They are still subject to change, but that has not stopped many web page authors using them already
The point of creating these new elements is so that web page authors can use them to help describe the structure of the page.

- The <header> and <footer> elements can be used for:
The main header or footerthat appears at the top orbottom of every page on the site.
- A header or footer for an individual <article> or <section> within the page
- **The <nav>** element is used to contain the major navigational blocks on the site such as the primary site navigation.
  - some of the developers that were already using HTML5 decided to use the <nav> element for the links that appear at the bottom of every page
- **The <article> element** acts as a container for any section of a page that could stand alone and potentially be syndicated.
  - The <article> elements can even be nested inside each other.
- **The <aside> element** has two purposes:
  - When the <aside> element is used inside an <article> element, it should contain information that is related to the article but not essential to its overall meaning.
  - When the <aside> element is used outside of an <article> element, it acts as a container for content that is related to the entire page.
- **The <section> element** groups related content together, and typically each section would have its own heading
  - it may contain several distinct <article> elements that have a common theme or purpose
  - if you have a page with a long article, the <section> element can be used to split the article up into separate sections.
- **Heading Groups <hgroup>**is to group together a set of one or more <h1> through <h6> elements so that they are treated as one single heading.
- **Figures <figure> <figcaption>** 
  - <figure> It can be used to contain any content that is referenced from the main flow of an article (not just images).
  - Examples of usage include:
Images
Videos
Graphs
Diagrams
Code samples
Text that supports the main
body of an article
  - The <figure> element should also contain a <figcaption> element which provides a text decription for the content of the <figure> element
- anything that lies outside of the <header>, <footer> or <aside> elements can be considered as the main content.
- **Linking Around Block-Level Elements <a>**
  - allows you to turn an entire block into a link.

- Older browsers that do not know the new HTML5 elements will automatically treat them as inline elements.
- IE9 was the first version of Internet Explorer to allow CSS
rules to be associated with these new HTML5 layout elements.
- Every website should be designed for the target audience—
- Your content and design should be influenced by the goals of your users.
#### Key Motivations :
  - entertainment or do they need to achieve a specific goal
  - specific goal
  - spending time on this activity as essential or a luxury
- be able to list every reason why someone visits your site but you are looking for key tasks and motivations. This information can help guide your site designs
- You know who is coming to your site and why they are coming, so now you need to work out what information they need
#### Key Information
  - Will visitors be familiar with your subject area / brand
  - Will they be familiar with the product / service / information you are covering
  - What are the most important features of what you are offering
  - What is special about what you offer that differentiates you from other
  - Once people have achieved the goal that sent them to your site, are there common questions people ask about
- Some sites benefit from being updated more frequently than others. Some information (such as news) may be constantly changing, while other content remains relatively static
### Site Maps
The aim is to create a diagram of the pages that will be used
to structure the site. This is known as a site map and it will
show how those pages can be grouped.
#### card sorting:
technique To help you decide what information should go on each page
#### WireFrames:
a simple sketch of the key information that needs to go on each page of a site. It shows the hierarchy of the information and how much space it might require.
- The primary aim of any kind of visual design is to communicate. Organizing and prioritizing information on a page helps users understand its importance and what order to read it in
- **visual hierarchy**
Attention is immediately drawn to a picture that shows the
service this company offers and a headline to explain it.
  - refers to the order in which your eyes perceive what they see.
  - It is created by adding visual contrast between the items being displayed. Items with higher contrast are recognized and processed first
- Larger elements will grab users'attention first.
- Foreground and background color can draw attention to key messages.
- An element may be the same size and color as surrounding
content but have a different style applied to it to make it stand out.
#### Grouping :
When making sense of a design, we tend to organize visual elements into groups. Grouping related pieces of information together can make a design easier to comprehend.
  - Proximity:When several items are placed close together, they are perceived as more related than items that are placed further apart.
  - Closure:When faced with a complicated arrangement of items, we will often look for a single or recognisable pattern or form
  - Continuance:When elements are placed in a line or a curve then they are perceived to be more related than those that are not following the same direction.
  - White Space:Placing related items closer together and leaving a bigger gap between unrelated items
  - color:A background color placed behind related items to emphasize their connection
  - Borders:A line can be drawn around the border of the group or between it and its neighbors.
#### similarity
We naturally observe similarities in design, and things that are similar are perceived to be more related than things that are dissimilar. Repetition of similar color, size,orientation, texture, font, or shape, suggests that matching elements have similar importance or meaning.
#### Designing Navigation
Site navigation not only helps people find where they want to go, but also helps them understand what your site is about and how it is organized. 
- Good navigation principles:
  - Concise
  - Clear
  - Selective
  - Context
  - Interactive
  - Consistent
































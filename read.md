## object
- Objects group together a set of variables and functions to create a model of a something you would recognize from the real world
- If a variable is part of an object, it is called a property.
- If a function is part of an object, it is called a method.The value of a method is always a function.
- **key** properties and methods name and a value An object cannot have two keys with the same name.
- Objects consist of a set of name/value pairs
- define object :
``` objectame = {
		name:values
	fullName : function() {
    return this.firstName + " " + this.lastName;
		} ```
- You can access object properties in two ways:
  - objectName.propertyName

  - objectName["propertyName"]
## The Document Object Model (DOM)
- specifies how browsers should create a model of an HTML page and how JavaScript can access and update the contents of a web page while it is in the browser window
- The DOM is called an object model because the model (the DOM tree) is made of objects.
- DOM als o called an Application Programming Interface (API).
- **THE DOM TREE ** IS A MODEL OF A WEB PAGE
- Every element, attribute, and piece of text in the HTML is represented by its own **DOM node**.
- At the top of the tree a document node is added; it represents the entire page
- To access the DOM tree, you start by looking for elements.
- Each node is an object with methods and properties
- The opening tags of HTML elements can carry attributes and these are represented by attribute nodes in the DOM tree.
- **TEXT NODES** :Once you have accessed an element node, you can then reach the text within that element.
- Accessing and updating the DOM tree involves two steps:
  1. Locate the node that represents the element you want to work with.
  2. Use its text content, child elements, and attributes
- common ways to select an individual element :
  - getElementByld():Uses the value of an element's id attribute
  - querySe1ector(): Uses a CSS selector, and returns the first matching element
  - 
- common ways to select multiple elements:
  - getElementsByClassName():Selects all elements that have a specific value for their class attribute.
  - getElementsByTagName() :Selects all elements that have the specified tag name 
  - querySelectorAll():Uses a CSS selector to select all matching elements
- You can move from one element node to a related element node:
  - parentNode :Selects the parent of the current element node 
  - previousSibling / nextSibling:Selects the previous or next sibling from the DOM tree.
  - firstChild / lastChild: Select the first or last child of the current element.
- To access the text node above:
  1. Select the <l i >element
  2. Use the fi rstChi l d property to get the text node
  3. Use the text node's only property (nodeValue) to get the text from the element,**nodeValue** This property lets you access or update contents of a text node
- One property allows access to child elements and text content: innerHTML
- Another just the text content: textContent
- Several methods let you create new nodes, add nodes to a tree,and remove nodes from a tree:
  - create Element()
  - createTextNode()
  - appendChi l d () / removeChi l d ()
- properties and methods you can use to work with attributes:
  - className /id Lets you get or update the value of the cl ass and id attributes.
  - hasAttribute():checks if an attribute exists.
  - getAttribute():gets its value.
  - setAttri bute():updates the value.
  - removeAttribute():removes an attribute
- **DOM queries** : method that find ehe element in DOm tree
- DOM queries may return one element, or they may return a Nodelist,which is a collection of nodes.
- querySel ector( 1css selector '):This method returns only the first of the matching elements.
- METHODS THAT RETURN ONE OR MORE ELEMENTS (AS A NODELIST):
  - getElementsByClassName('class') :Selects one or more elements given the va lue of their cl ass attribute.
  - getEl ementsByTagName( ' tagName '):Selects all elements on the page with the specified tag name
  - querySelectorAll ('cssselector'):Uses CSS selector syntax to select one or more elements and returns all of those that match
- When a DOM method can return more than one element, it returns a Nodelist (even if it only finds one matching element).
- **live Nodelist** when your script updates the page, the Nodelist is updated at the same time.
- **static Nodelist** when your script updates the page, the NodeList is not updated to reflect the changes made by the script.
- There are two ways to select an element from a Nodelist: The item() method and array syntax. Both require the index number of the element you want
- When you have an element node, you can select another element in relation to it using these five properties. This is known as traversing the DOM:
  - parentNode This property finds the element node for the containing element in the HTML
  - previousSibling /nextSibling :These properties find the previous or next sibling of a node
  - firstChild/lastChild:These properties find the first or last child of the current element
- To work with the content of elements you can:
  - Navigate to the text nodes. This works best when the element contains only text, no other elements.
  - Work with the containing element. This allows you to access its text nodes and child elements. It works better when an element has text nodes
and child elements that are siblings.
- The textContent property allows you to collect or update just the text that is in the containing element
- Using the innerHTML property, you can access and amend the contents of an element,including any child elements
- DOM manipulation offers another technique to add new content to a page:
  - You start by creating a new element node using the createElement() method
  - createTextNode() creates a Now that you have your element new text node(GIVE IT CONTENT)
  - appendChild() ADD IT TO THE DOM
- DOM manipulation can be used to remove elements from the DOM tree.
  - STORE THE ELEMENT TO BE REMOVED IN A VARIABLE:
  - STORE THE PARENT OF THAT ELEMENT IN A VARIABLE:parentNode
  - REMOVE THE ELEMENT FROM ITS CONTAINING ELEMENT :The removeChild() method takes one parameter: the reference to the element that you no longer want
- you need to be aware of Cross-Site Scripting Attacks or XSS; otherwise,an attacker could gain access to your users' accounts.
- HOW XSS HAPPENS
  - XSS involves an attacker placing malicious code into a site. Websites often feature content created by many different people.
- **untrusted data** :Data you do not have complete control over

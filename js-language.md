JavaScript Language
===

###Lexical Structure

Character Set
JavaScript uses Unicode.
JavaScript is case-sensitive.

Comment
```javascript
//Single Line Comment
/* Multi-Line Comment */
```

###Literals

- **Number**
- **Integer**
- **Floating-point** -- [digits][.digits][ [E|e] [+|-] digits ]
- **String** -- Surrounded by double-quote or single-quote (For nesting)
- **Boolean** : true/false
- **Expressions**
- **Identifiers** and **Reserved Words** -- Begin with[ _|letter|$] (Numbers are not allowed as first character)


Novel Features
===

SIMD operations -- CPU SIMD API
WebGL
WebWorker -- multi-thread -- detail in my WebWorkers note


references

 - [JavaScript gains support for SIMD](http://www.2ality.com/2013/12/simd-js.html)
 - [Closing the Web Platform Gap with Native](http://cdn.oreillystatic.com/en/assets/1/event/106/Closing%20the%20Web%20Platform%20Gap%20with%20Native%20%20Presentation.pdf)
 - [Bringing SIMD to JavaScript](https://01.org/blogs/tlcounts/2014/bringing-simd-javascript)


Object Model
===

###Object Category

- Native Object: Objects defined by JavaScript
- Host Object: Objects defined by Browser
- User-defined Object


###Object Creation

Object Literals  
  -- [syntax] var object = { name: value, name: value };
  -- object.prototype === Object.prototype.

Keyword new (constructor)
  -- [syntax] var object = new Constructor(parameters);

Object.create()  
  -- [syntax] var object = Object.create(myPrototype);
  -- object.prototype === myPrototype.


###Constructor

[definition] Constructor is function designed to be used with the keyword [new] 

[link] object.prototype === Constructor.prototype.
[link] object.constructor === Constructor
[link] Constructor.constructor === Constructor === Constructor.prototype.constructor

actual process of [new Constructor(param)]
  -- this = Object.create(Constructor.prototype)
  -- constructor prcedure with [this] and [param]
  -- return this


###Prototype Inheritance

Prototype is a implicit link from an object to anther object
It is not copied into the new object, but linked to it.

recursive attribute lookup
  -- if attribute defined in the object, return it
  -- else, recursively look up the attribute in object's prototype 


###Object Attribute

Prototype
Object.getPrototypeOf(myObject);
Function object can use prototype keyword directly access the prototype.
Class Read-Only
Extensible
Specifies if a new property can be added to the object.
By default every object is extensible.
constructor

###Property Attribute

In ECMAScript 3 the property attributes are immutable, all writable enumerable and configurable.
Four property attributes of data property
value, writable, enumerable, configurable 
Four property attributes of accessor property
get, set, enumerable, configurable
Property attribute access methods
Object.getOwnPropertyDescriptor(myObject, ”property-name”); 
Return a object contains the four property attributes as its properties.
Object.defineProperty(myObject, “attribute-name”, attributeSet); 
Omitted attributes are default to be undefined and false.

###Property

Property Type
Data property
Accessor property
Accessor property defined by setter and getter methods (optional)
{set name(){function body}, get name(parameter){function body}}
Property Query
Object.property
Object[“property”]
Interpreter will search the property in the list of the object’s own properties, if not found, continue search in its prototype object, usually stops at Object.prototype.


Function
===

Functions are objects.

Invocation
  -- Function Invocation
  -- Method Invocation
  -- Constructor Invocation
  -- Indirect Invocation 

Invoke Context (“this” object)
  -- invoke context == method of an object
     [this] is the invoker object.
  -- invoke context == function
     strict mode: “this” is undefined
     non-strict mode: this is the global object. 

sometimes using Constructor is dangerous 
because if forgot [new], this will mean global object therefore may cause disaster

for function object, its prototype is a new object contains a property called constructor witch is a reference to the function object itself.

Regular Expression
===

####Create Regular Expression
```javascript
var pattern = /pattern/;
var pattern = new RegExp(“pattern”, ”flags”);
```

####Flags

 - g : preform a global matching (i.e. return all matches within the searched string)
 - i : preform case-insensitive matching
 - m : multiline mode

####Methods of String
```javascript
string.search();
// Return the index of the first match, return -1 if no match.
string.replace(/pattern/, string);
// Replace first/all matched pattern to the string. 
string.match();
// return the matched string, global search returns all matched string. Always return an array.
string.split();
// return an array of the split string separated by the pattern.
```
####Methods of RegExp Object
```javascript
pattern.exec()
pattern.test()
```
Javascript Execution Timeline
===

Javascript Type
  -- Synchronous (default) 
  -- Asynchronous <script async src=”url”></script>
     Run as soon as it is parsed. May execute out of order.
  -- Deferred <script defer src=”url”></script>
     Run after the document is fully loaded and ready to be manipulated.

###Client-Side JavaScript Timeline

Synchronous Script Execution Phase
  document.readyState = “loading”, readystatechange event
  Browser creates document object. 
  Begin paring the web page and adding nodes to the document.
  Begin synchronous script
  Begin asynchronous script
  Document completely parsed.
  document.readyState = “interactive”, readystatechange event
  Begin-and-Finish deferred script
  Browser fires a DOMContentLoaded event on Document object.

Asynchronous Event-Driven Script Execution Phase
  Complete loading additional non-textual content (include async script).
  document.readyState = “complete”, readystatechange event
  browser fires a load event on the Window object.
  Event handlers are invoked asynchronously in response to user events.


Client-Side Storage
===

Cookie
Write Cookie
Read Cookie


Windows Object
===

Timer



Events
===

Event Type
  -- Form Events
  -- Window Events
  -- Mouse Event
  -- Key Events


###Event Handler Register


element.onEvent = EventHandlerFunction;
     Use element property can register only one handler function to an event.

element.addEventListener(“event”,HandlerFunction,[true|false]);
     element.removeEventListener(“event”,HandlerFunction,[true|false]);
     Enable to register several handlers to one event. Invoke in the order of register.
     Repeat registering with same arguments is equivalent to doing nothing.

###Event Handler Invocation

Event Handler Argument
  -- Event handlers are invoked with an event object as their single argument.

Event Handler Context
  -- [this] variable in the event handler means the event target.

Event Handler Invoke Order
  -- First invoke handler registered by element property, then by the order of register.


###Event Propagation

First Phase: Event Capturing
  -- Inverse of event bubbling, invoked from window, document to target’s parent.
  -- Target’s event capturing handler is not invoked.
  -- Registered by element.addEventListener(“event”, HandlerFunction, true);

Second Phase: Target Event Handler Invocation

Third Phase: Event Bubbling
  -- Invoked from target’s handler to windows object along the DOM tree.
  -- Have several exceptions, some event do not bubble.





---
HTML XML DOM (!Todo)
===

Node
Document
HTML Document
XML Document
Character Data
Text Node
CDATA Section
Element
Attribute
Node is the superclass of the DOM system.
DOM Node Property
Traversal Property
parentNode, childNode
fitstChild, lastChild 
nextSibling, previousSibling
nodeName Read-Only
Element Node: tag name
Attribute Node: attribute name
Text Node: “#text” 
Document Node: “#document”
nodeType Read-Only
Element(1);Attribute(2);Text(3);CDATA(4);Comment(8);Document(9)
nodeValue
Element Node: undefined.
Text Node: text itself.
Attribute Node: attribute value.
DOM Node Query
DOM Node Query Methods Document Node Only
getElementById(“id”); 
getElementByName(“name”); 
querySelector(“CSS Selector”); & querySelectorAll(“CSS Selector”);
DOM Node Query Methods Document & Element
getElementsByTagName(“Tag Name”); 
getElementsByTagNameNS(“Namespace”);
getElementsByClassName(“CSS Class”);
DOM Node Content Modify
Modify By HTML (XML) Syntax (serialize-modify-parse)
innerHTML 
String content inside the invoker element’s tags.
outerHTML
String content of the invoker element include its tags.
insertAdjacentHTML
element.insertAdjacentHTML(“position”,HTMLSyntax);
position: [ beforebegin | afterbegin | beforeend | afterend ]
Modify By DOM
Create Node
document.createElement(“TagName”); 
document.createTextNode(“Text”);
node.cloneNode(true/false); false for shallow copy.
Insert Node
parentNode.insertBefore(node,anchor); 
Insert before the anchor node inside the parent node.
parentNode.appendChild(node); 
Insert inside the parent node as the last child.
Remove Node
node.parentNode.removeChild(node);
Replace Node
Node.parentNode.replaceChild(newNode,node);
DOM Element Attribute Access
Universal Approach
element.setAttribute(“AttributeName”,”value”);
element.getAttribute(“AttributeName”);
HTML DOM Attribute Access
HTML Standard Attributes element.attrName
Dataset Approach
element.setAttribute(“data-name”,”value”);
element.dataset.name
XML DOM Attribute Access
element.getAttributeNode(“name”); attrNode.nodeValue
Document Object
Create Document
Create HTML Document (with skeletal DOM tree)
document.implementation.createHTMLDocument(“head.title”);
Create XML Document
document.implementation.createDocument(“NameSpace”,”Root”,”Doctype”);
HTML Property
Some Special Element
document.body, document.head, document.title, document.doctype 
Frames
frameElement.contentWindow == frameWindowObject
frameWindowObjet.frameElement == frameElement

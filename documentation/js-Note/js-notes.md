
DOM manipulation is a key aspect of web development, allowing you to dynamically change the content, structure, and style of web pages. Here's an overview of the main topics related to DOM manipulation:
1. The Document Object Model (DOM)
The DOM is a programming interface for web documents. It represents the structure of a document as a tree of nodes, where each node is an object representing a part of the document (e.g., an element, attribute, or text).

<!DOCTYPE html>
<html>
<head>
<title>DOM Example</title>
</head>
<body>
<h1 id="header">Hello, World!</h1> 
<p class="paragraph">This is a paragraph.</p>
<p class="paragraph">This is another paragraph.</p>
<button id="myButton">Click me</button>
<script src="script.js"></script> 
</body>
</html>



2. Selecting Elements
JavaScript provides several methods to
select elements in the DOM.

- getElementByld
Selects an element by its ID.
let header =document.getElementById("header");
console.log(header); // <h1 id="header">Hello, World!</h1>

- getElementsByClassName
Selects elements by their class name. Returns an HTMLCollection.
let paragraphs = document.getElementsByClassName("paragraph");
console.log(paragraphs); //
HTMLCollection (2) [p.paragraph, p.paragraph]

- getElementsByTagName
Selects elements by their tag name. Returns an HTMLCollection.
let buttons =document.getElementsByTagName("button"); console.log(buttons); //HTMLCollection (1) [button#myButton]

- querySelector
Selects the first element that matches a CSS selector.
let firstParagraph =document.querySelector(". paragraph"); console.log(firstParagraph); // <p class="paragraph">This is a paragraph.</p>
  
- querySelectorAll
Selects all elements that match a CSS
selector. Returns a NodeList.
let allParagraphs =document.querySelectorAll(". paragraph"); console.log(allParagraphs); //NodeList (2) [p.paragraph, p.paragraph]



4. Modifying Elements
You can modify elements by changing their properties, attributes, and styles.
Changing Content
textContent: Sets or gets the text
content of an element.
header.textContent = "Hello, DOM!";

.innerHTML: Sets or gets the HTML
content of an element.
firstParagraph.innerHTML = "<strong>This is a strong paragraph.</strong>";

Changing Attributes
setAttribute: Sets the value of an attribute.
header.setAttribute("class", "header-class");



.getAttribute: Gets the value of an attribute.
let headerClass=header.getAttribute("class"); console.log(headerClass); // "header-class"
removeAttribute: Removes an attribute.
header.removeAttribute("class");

Changing Styles
You can change the inline style of an element using the style property.
header.style.color = "blue"; header.style. fontSize = "2em";


5. Event Handling
Event handling allows you to execute code in response to user actions such as clicks, key presses, or form submissions.
Adding Event Listeners
You can add event listeners using the addEventListener method.

let button =document.getElementById("myButton");
button.addEventListener("click",function() {
alert("Button was clicked!");
});

Event Objects
Event listeners receive an event object tha contains information about the event.
button.addEventListener("click",
function(event) {
console.log("Button clicked at
coordinates: " + event.clientX + || " + event.clientY);
});


Removing Event Listeners
You can remove event listeners using the removeEventListener method.
function handleClick() {
}

alert("Button was clicked!");
button.addEventListener("click",handleClick);
// Remove the event listener
button.removeEventListener("click",handleClick);



Practical Examples
Example 1: Changing Content on Button
Click
<!DOCTYPE html>
<html>
<head>
<title>DOM Manipulation</title>
</head>
<body>
<h1 id="header">Hello, World!</h1> <button id="myButton">Click me</
button>
<script>
let button =document.getElementById("myButton"); button.addEventListener("click",
function() {
let header =document.getElementById("header");
header.textContent = "You clicked the button!";
});
</script>
</body>
</html>



Example 2: Adding New Elements
<!DOCTYPE html>
<html>
<head>
<title>DOM Manipulation</title>
</head>
<body>
<ul id="list">
<li>Item 1</li>
<li>Item 2</li>
</ul>
<button id="addButton">Add Item</
button>
<script>
let addButton =document.getElementById("addButton"); addButton.addEventListener("click",
function() {
let list =document.getElementById("list");
let newItem =document.createElement("li");
newItem.textContent = "New Item"; list.appendChild(newItem);
});
</script>
</body>
</html>


Example 3: Removing Elements
<!DOCTYPE html>
<html>
<head>
<title>DOM Manipulation</title>
</head>
<body>
<ul id="list">
<li>Item 1</li>
<li>Item 2</li>
</ul>
<button id="removeButton">Remove Last Item</button>
<script>
let removeButton =document.getElementById("removeButton");
removeButton.addEventListener("click",function() {
let list =document.getElementById("list");
list.removeChild(list.lastElementChild);
});
</script>
</body>
</html>


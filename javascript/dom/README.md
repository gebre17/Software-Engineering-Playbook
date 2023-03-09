# Document Object Model (DOM) Manipulation

The Document Object Model (DOM) is the programming interface for web documents. It represents the page structure so that programs can alter the document structure, style, and content.

## Selecting Elements
*   `document.getElementById('id')`
*   `document.querySelector('.class')` (Selects the first matching element)
*   `document.querySelectorAll('div')` (Selects all matching elements as a NodeList)

## Creating & Modifying Elements
```javascript
// Create
const newDiv = document.createElement('div');

// Modify Content and Attributes
newDiv.textContent = "Hello, DOM!";
newDiv.setAttribute('id', 'new-element');
newDiv.classList.add('active');

// Append to DOM
document.body.appendChild(newDiv);
```

## Event Listeners
```javascript
const button = document.querySelector('button');

const handleClick = (event) => {
  console.log("Button clicked!", event.target);
};

button.addEventListener('click', handleClick);
// To clean up later:
// button.removeEventListener('click', handleClick);
```

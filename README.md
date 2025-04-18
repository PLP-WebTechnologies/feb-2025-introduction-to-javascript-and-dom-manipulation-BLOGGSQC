<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript and DOM Manipulation</title>
    <link rel="stylesheet" href="styles.css">
    <script src="script.js" defer></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .dynamic-style {
            color: blue;
            font-weight: bold;
        }
        .added-element {
            background: #f4f4f4;
            padding: 10px;
            margin: 5px 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>JavaScript DOM Manipulation Example</h1>
    </header>
    <main>
        <section>
            <p id="text">This is some text that will change.</p>
            <button id="changeTextBtn">Change Text</button>
            <button id="toggleStyleBtn">Toggle Style</button>
        </section>
        <section>
            <h2>Dynamic Element Manipulation</h2>
            <button id="addElementBtn">Add Element</button>
            <button id="removeElementBtn">Remove Element</button>
            <div id="elementContainer"></div>
        </section>
    </main>
    <footer>
        <p>&copy; 2025 Your Name. All Rights Reserved.</p>
    </footer>
</body>
</html>

script.js
// Change text content dynamically
document.getElementById('changeTextBtn').addEventListener('click', function() {
    document.getElementById('text').textContent = 'The text has been changed!';
});

// Modify CSS styles via JavaScript
document.getElementById('toggleStyleBtn').addEventListener('click', function() {
    const textElement = document.getElementById('text');
    textElement.classList.toggle('dynamic-style');
});

// Add or remove an element when a button is clicked
document.getElementById('addElementBtn').addEventListener('click', function() {
    const newElement = document.createElement('div');
    newElement.className = 'added-element';
    newElement.textContent = 'This is a dynamically added element.';
    document.getElementById('elementContainer').appendChild(newElement);
});

document.getElementById('removeElementBtn').addEventListener('click', function() {
    const container = document.getElementById('elementContainer');
    if (container.lastChild) {
        container.removeChild(container.lastChild);
    }
});


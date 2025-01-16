# Uncommon HTML Bug: Incorrect innerHTML Modification

This repository demonstrates a subtle bug that can occur in HTML when using JavaScript to manipulate the DOM.  The bug arises from attempting to modify the `innerHTML` of an element that does not exist. This will result in a silent failure; no error is thrown, and no change will be made to the page. This is easy to miss, leading to unexpected behavior.

The `bug.html` file showcases the problematic code. The `bugSolution.html` file provides a corrected version.

## Bug Description

The primary issue lies in the line:

```javascript
document.getElementById('myDiv2').innerHTML = "This text won't show.";
```

This code attempts to access and modify an element with the ID 'myDiv2'. However, no such element exists in the HTML structure.  Modern browsers handle this gracefully (no error) but it still produces unexpected results.

## Solution

The solution involves robust error handling or ensuring the element exists before attempting modification.
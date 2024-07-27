- DOM (Document Object Model) represents the entire <font color="#9bbb59">HTML document as a tree structure</font>. Each HTML element is a node in this tree. 
- It provides a programming interface that allows JavaScript to interact dynamically with the content, structure, and style of a website.
- Through the DOM, JavaScript can add, remove, and modify elements and attributes. Changes to the DOM automatically update the display on the web browser.

![[Pasted image 20240726012914.png]]

- **Window Object**: Window Object is object of the browser which is always at top of the hierarchy.  It is like an API that is used to set and access all the properties and methods of the browser. It is automatically created by the browser. e.g. <font color="#9bbb59">window.location.href</font>
	- **Document Object**: When an HTML document is loaded into a window, it becomes a document object. The ‘document’ object has various properties that refer to other objects which allow access to and modification of the content of the web page.
		 - **Form Object**: Represented by `<form>` tags, manages form data and controls.
		 - **Link Object**: Represented by `<link>` tags, used for linking external resources.
		 - **Anchor Object**: Represented by `<a>` tags, used for creating hyperlinks.
		 - **Form Control Elements**: Includes text fields, buttons, radio buttons, checkboxes within a form.

### DOM Methods

| Method                   | Description                                           |
| ------------------------ | ----------------------------------------------------- |
| write(“string”)          | Writes the given string on the document.              |
| getElementById()         | Returns the element having the given id value.        |
| getElementsByName()      | Returns all the elements having the given name value. |
| getElementsByTagName()   | Returns all the elements having the given tag name.   |
| getElementsByClassName() | Returns all the elements having the given class name. |


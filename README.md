# Build a Kanban Board with Javascript

## Status

**Published**

## Overview

This project is design to be completed on [Pluralsight](https://pluralsight.com). To find out more see here: [https://www.pluralsight.com/product/projects](https://www.pluralsight.com/product/projects).

## Installation

Run the following command from the root folder of the cloned project to install all dependencies.

`npm install`

## Verify Setup

In order to verify that everything is setup correctly, run the following command, which should show you the failing tests. This is good! We'll be fixing these tests once we jump into the build step.

`npm run test`

Every time you want to check your work locally you can type that command, and it will report the status of every task in that module.

As you move through the modules, you can run module-specific tests with the script `npm run test:module1`, replacing the number with one that corresponds with the module you are working in.

## Previewing Your Work

In order to see your changes in a browser, you can run `npm start` from the command line. This will open a browser and you should see your landing page.

## Steps 
### Step 1 - Create an Item
In this module we will add DOM event listeners to a Kanban Board. We will make it possible to add tasks, and drag and drop those tasks between columns.

To start, let's open the main file for the project, js/kanban.js.

Find the function called create_item(). In the body of this function, use the createElement() function to create a DOM element of type div. Save a reference to the element in a variable called item.

Hint: when working with DOM elements, you will need to reference document.

### Step 2 - Set Item Attributes
The item variable now stores a reference to a fully fledged DOM element. We can manipulate anything about this element. Below the existing code in the create_item() function, use the add method of the classList object to add the existing CSS class of item to the item element.

Next, give the item an id of item- plus the current value of order.

Finally, make the item draggable.

### Step 3 - dragstart Event Listener
Now that the item is draggable, add an event listener that listens for the dragstart event to item. When creating the event listener, pass an arrow function as the handler. The arrow function should accept a single parameter of event, and it should return a call to the setData() method. The setData() method is part of the DataTransfer object, which needs to be accessed through the event.

Use the setData() method to set 'text' to the id of the event.target element.

### Step 4 - dragend Event Listener
After the dragstart event listener, add an event listener that listens for the dragend event to item.

When creating the event listener, pass an arrow function as the handler. The arrow function should accept a single parameter of event, and it should return a call to the clearData() method. The clearData() method is part of the DataTransfer object, which needs to be accessed through the event.

### Step 5 - Create input Element
Below the drag event listeners, use the createElement() method to create a DOM element of type input. Save a reference to the element in a variable called input.

Append this new input element to the item element with the correct DOM method.

### Step 6 - Create a Save Button
Below the input element, use the createElement() method to create a DOM element of type button. Save a reference to the element in a variable called save_btn.

Change the innerHTML property of the save_btn element to Save.

### Step 7 - Save Button Event Listener
We can now add an event listener to save_btn. Below the existing code, register an event listener for save_btn that listens for a click event. Pass an arrow function as the handler. The arrow function does not need to accept any parameters.

### Step 8 - Validate Input - if conditional
In the body of the save_btn event handler, set the HTML of the error element to an empty string.

Next, create an if statement that tests whether the value of input is not equal to an empty string.

### Step 9 - if body
Add three lines in the body of the if statement. The first should add 1 to order and reassign the value back to order. The second should change the HTML of the item element to the value of the input. The third should toggle adding to false.

### Step 10 - else body
Still in the save_btn handler, add an else statement to the existing if statement. In the body of this else statement, set the HTML of the error element to the message string.

### Step 11 - Append the Save Button
Now that all parts of the save_btn are complete, append it to the item element. With this item is now complete as well, return it from the create_item() function.

### Step 12 - Drop Event - Handler
Below the create_item() function, find the forEach loop. In the body, add an event listener that listens for the drop event to element. When creating the event listener, pass an arrow function as the handler. The arrow function should accept a single parameter of event.

To begin the event handler, prevent the default action of event.

### Step 13 - Drag Event - Data Transfer
Still in the drop event handler, get the data in 'text' with the getData() method. The getData() method is part of the DataTransfer object, which needs to be accessed through the event. Store the returned value in a constant called id.

### Step 14 - Drag Event - Append Element
As the last line of the drop event handler, append the element that has an id of id to event.target. Hint: use the getElementById() method of document.

### Step 15 - Drag Event - Handler
Still in the forEach() loop function, add an event listener that listens for the dragover event to element. When creating the event listener, pass an arrow function as the handler. The arrow function should accept a single parameter of event and prevent the default action of event.

# Chapter 7 - FORMS

### ***Form Controls***

1) ***Adding Text***
    - Text input
    - Password input
    - text area
2) ***Making Choices***
    - Radio buttons
    - Checkboxes
    - Drop-down boxes
3) ***Submitting Forms***
    - Submit Buttons
    - image buttons
4) ***Uploading Files***
    - file upload

### ***How Forms Work***

1. User fills in a form and presses a button to submit the info to the server

2. The values of each form control are sent to the server

3. The information is processed or stored in a database

4. the server sends and new page back to the browser based on the info received

### ***Form Structure***

- always carry an action attribute
    - Its value is the URL that will receive the information in the form

- ### Method
    - **get**
        - the values from the form are added to the end of the URL specified in the action attribute
        - short forms
        - retrieving data from the web server
    - **post**
        - values are sent in HTTP headers
        - allows users to upload files
        - is very long
        - contains sensitive data
        - adds or deletes information to a database

- ### Name

- Each control requires a name attribute, the value identifies the form control and is sent along with the information they enter to the server.

### PASSWORD

- for full security communication between server and browser needs to be set up with ***Secure Sockets Layer SSL***

### TEXT AREA 

- A multi-line text input, requires an opening and closing tag.

### RADIO BUTTON // CHECKBOX

- Name should all be the same
- value should be unique for each input so the server knows which option the user has selected. 

### DROP DOWN LIST // MULTIPLE SELECT

- The **select attribute** is used to create the list containing the **option attribute**
    - The **size attribute** is used to indicate how many options should be displayed at a time
    - The **multiple attribute** is used if the user is able to select multiple options in the drop down list.

### FILE INPUT

- type= file creates a text input followed by a ***browser*** button, allowing users to upload files, the ***method attribute** must have a value of post.

### SUBMIT BUTTON

- The ***value attribute** controls the text that appears in the button
- ***Type='image'*** allows for an image to be used as a button
    - ***BUTTON ELEMENT*** allows for more customization
        - the ***hidden attribute** allows for allows devs to add values to forms that users can not see.

### LABEL

- Makes forms accessible to vision-impaired users.
- the value of the **for attribute** matches that of the id attribute on the form control it is labelling, can be used on any form control.
- when used with checkbox or radio, users can click on either the label or the form control.

### GROUPING

- **fieldset**
    - group related form controls together inside.
- **legend**
    - comes directly after the opening tag and contains the caption. 

### HTML5: FORM VALIDATION

- reduces the amount of work the server has to do
- enables users to see if there are problems with the form faster
    - ***required attribute** is used, does not need a value. 

### HTML5: DATE, EMAIL & URL input

- type attribute a value of **date**
- type attribute a value of **email**
- type attribute a value of **url**

### SEARCH INPUT

- type attribute a value of **search**
- **placeholder attribute** the value is the text shown in the box, disappears when user clicks.

## CHAPTER 14 LISTS TABLES AND FORMS

- This chapter goes over CSS best practices for styling lits tables and forms.
    - <https://formalize.me> is a good resource for downloading files to make you select boxes, radio buttons and checkboxes more consistent across all browsers

- adding padding to cells in tables improves readability
- if you have empty cells in your table you can use the **empty-cell** property to specify if the border should be shown, it takes three properties:
    - show
    - hide
    - inherit: if one table is nested in another, the nested table will obey the rules of th
    
- **border-spacing** property controls the distance between adjacent cells
    - ***collapse*** borders are collapsed into a single border
    - ***separate*** borders are detached, border-spacing and empty-cells will be obeyed

- stying text inputs
    - ***:focus*** pseudo class is used to change the background color od the text input when it is being used
    -***:hover*** pseudo class applies the same but when user hovers. 

- **Cursor styles** you should only used this to add help information, and not confuse the user.

### ***Web Developer Toolbar*** seems useful



# **CHAPTER 6** ***EVENTS***

## TERMINOLOGY 

- when an event has occurred it has **FIRED** or **RAISED**
- when a click even fires on an element it **TRIGGERS** and script

### How events trigger JS code

1. Using a DOM query, select the elements node(s) you want the script to respond to
2. **bind** the event to the DOM node, indicating which event on the selected node will trigger the response.
3. State the code(function) that you want to run when the event occurs.

### Three ways to bind an event to an element

1. **HTML EVENT HANDLER**
    - dont use
2. **DOM EVENT HANDLERS**
    - only able to attach a single function to any event.
3. **EVEN LISTENERS**
    - you are able to attach multiple functions to a single event.
        - less likely to be conflicts between scripts that run on the same page. 

the **addEventListener()** takes three parameters
1.  the event you want it to listen for
2. The code you want to run when the vent fires
    - parentheses are omitted
3. a boolean, idicating how to event should flow
    - false - bubbling
    - truse - capturing

### USING PARAMETERS WITH EVENT LISTENERS

- If you need to pass arguments to a function that is called by an event listener you wrap the function in an **anonymous function**.
    - the named function lives in the anonymous function
    - the anonymous function has parentheses- but it only runs when the event is triggered -- function()

### EVENT FLOW

- **EVENT BUBBLING**
    - the event starts at the ***most specific*** node and flows ***outwards*** to the **least** specific one. this is the **DEFAULT**
    - 'false'
- **EVENT CAPTURING**
    - the event starts at the ***least specific*** and flows ***inwards*** to the **most** specific one.
    - 'true'

### EVENT OBJECT

- Every time an event fires, the vent object contains data about the event, such as:
    - which element the vent happened on
    - which key was pressed- keypress event
- If you need toi pass arguments to a named function, the event object will first be passed to an anonymous wrapper function- happens automatically- then you must specify it as a parameter of the named function
- when the event object is passed into a function, it is often given a parameter name ***e***

### EVENT DELEGATION

- adding event listeners to each element can slow down performance (bad practice)
- events affect containing (ancestor) elements.
- **attach event listeners to containing elements**


## CHANGING DEFAULT BEHAVIOR

- **preventDefault()**
    - to prevent the default behavior of such elements
- **stopPropagation()**
    - possibly to stop events from bubbling to ancestors

***return false*** achieve both but since the blocks any further code within the function its often better to use *preventDefault()*

### USER INTERFACE EVENTS

- *event listener for UI events should be attached to the **browser window***
    - **load** - fires when the web page has finished loading- can also fire on nodes of other elements that load
    - **unload** - fires when a page is unloading( ususally when another one has been requested)
    - **error** fired when the browser encounters a JS error
    - **resize**
    - **scroll** - when users scrolls either on the page or in a specific element 

### FOCUS & BLUR EVENTS

- if you can interact with an element then it can gain and lose focus(blur)
- The CSS **:focus pseudo class** is best for changing the appearance of an element, unless you neesd to affect an element other than the pne that gained focus. 

**FOCUS** *(focusin)*: when an element gains focus the event fires
**BLUR** *(focusout)*: when abn element looses focus the even fires

### MOUSE EVENTS

- **click**
- **dblclick**
- **mousedown** - when the user presses down on any mouse button
- **mouseup** - when the user releases a mouse button
- **mouseover**
- **mouseout** - when the users cursor is over an element and then moves on to another, outside the current element
- **mousemove** 

when changing appearance the the CSS :hover pseudo class is preferred to mouseover and mouseout

*mousedown and mouseup are good for adding drag and drop functionality*

### WHERE EVENTS OCCUR

the event object can tell you where the cursor was positioned when an event was triggered

- **SCREEN** *(screenX & screenY)*- indicates the position of the cursor within the entire screen on your monitor
- **PAGE** *(pageX & pageY)*- indicates the position of the cursor within the entire page- top of page may be out pof viewport
- **CLIENT** *(clientX & clientY)&*- indicates the position of the cursor within browser viewport.

### KEYBOARD EVENTS

- **INPUT** - fires when the value or textarea element changes
- **KEYDOWN** - fires when the user presses ***any key***, if the user holds down the key the event continues to fire. *fires before a character shows on the screen.*
- **KEYPRESS** - fires when the user presses a key that would result in ***a character being shown***. *fires before a character shows on the screen*.
- **KEYUP** - fires when an user releases a key. *fire after the character would appear on the screen*

### FORM EVENTS

- **SUBMIT** - when the form is submitted the event fires on the node representing the form element. commonly used for validation
- **CHANGE** - fires when the status odf several form elements change. 
    - a slection is made from a dropdown
    - a radiobutton is selected
    - a checkbox is deselected 
**INPUT** 

**Mutation events are depreciated, instead uses** ***MUTATION OBSERVERS***
mutation observers are designed to wait until a script has finished its task before reacting then report changes as a batch, which is much faster and provides better performance than mutation events.

### HTML5 EVENTS

- **DOMContentLoaded** - fires when the DOM tree is formed, scripts start to run earlier than using load event. it can be attached to the window or document objects
- **hashchange** - fires when the URL hash changes. works on the window object, and after firingm the event object will have *oldURL* and *newURL* properties that hold the url before and after the hashchange
- **beforerunload** - fires on the window object before the page is unloaded- ex. it can be helpful to let a user know that changes on a form they completed have no been saved.


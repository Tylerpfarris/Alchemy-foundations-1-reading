# CHAPTER 15 LAYOUT

### BUILDING BLOCKS

block-level boxes start on a new line and act as the main building blocks of any layout
to separate boxes use:
-borders
-margins
-padding
-background-color

### CONTAINING ELEMENTS

a box may be nested inside several other block-level elements. *the containing element is always the direct parent of that element*

#### **CONTROLLING ELEMENT POSITION**

**NORMAL FLOW**

*position: static* 

- this is the default positioning

**RELATIVE POSITIONING**

*position: relative*

- this moves an element from the position it would be in normal flow. shifting it to the top, right, bottom, or left.
- does not affect the position of the surrounding elements.
- use the offset properties to indicate how far to move the element from where it would have been in normal flow.

**ABSOLUTE POSITIONING**

*position: absolute*

- box is taken out of normal flow and no longer affects the position of other elements on the page
- box offset properties specify where the element should appear in relation to its containing element.
- moves as the user scrolls up and down the page. 

**FIXED POSITIONING**

*position: fixed*

- positions the element in relation to the browser window. 
- box offset properties are used
- do not affect the position of surrounding elements
- does not move when user scrolls up and down the page

**OVERLAPPING ELEMENTS**

*z-index:*

- its value is a number, the higher the number the closer that element is to the front.

**FLOATING ELEMENTS**

*float:*

- takes an element out of normal flow and position it to the far left or right of the containing box.
- becomes a block-level element around which other content can flow.
- you should use the *width* property to indicate how wide the floated element should be.

*clear:*

- allows you to say that no element should touch the **left** or **right** hand sides of a box
- **both** neither left or right-hand sides will touch elements appearing in the same containing element.
- **none** elements can touch either side.

**parents of floated element SOLUTIONS**

- *overflow: auto*
- *width: 100%*


### FIXED WIDTH LAYOUT 

- do not change the size as the user increases or decreases the size of their browser window
- measurements tend to be PX

### LIQUID LAYOUT

- stretch and contract as the user increases or decreases the size of their browser window.
- tend to use percentages.

### LAYOUT GRIDS

*12 column grid creates 12 60px columns with margins set to 10px left and right.*

- 960 pixel grid is a good css framework to uses
- grid creates continuity between different pages
- helps users predict where to find information
- makes it easier to add new content
- helps collaboration

### MULTIPLE STYLE SHEETS

2 ways to import css style sheets

1. you can use the *@import*
    - `@import url("tables.css);`

2. you can link all the style sheets in ur HTML file.
    - `<link rel="stylesheet" type="text/css" href="css/site.css"`>


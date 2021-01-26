# READ 10

## DEBUGGING

### EXECUTION CONTEXTS

Javascript interpreter uses execution contexts. there is one global execution context, each function creates a new new execution context

every statement in a script lives in one one of three execution contests: **GLOBAL** **FUNCTION** **EVAL**

**HOISTING**

- prepare 
    - the new scope is created
    - variables functions and arguments are created

- execute
    - now it can assign values to variables
    -reference functions and run their code
    - execute statements

***LEXICAL SCOP*** - functions are linked to the object they were defined within.

ideally you create variables inside the functions that use them. 

### ERRORS

- The interpreter goes through the stack looking for error-handling code until it gets to the global context. if there is still no error handler, the script stops running and the error object is created.

### DEBUGGING WORKFLOW

- narrow down the area
    1. look at the error message
    2. check how far the script is running 
    3. use breakpoints.

**BREAKPOINTS** - pauses the execution of the script, then you can check the values stored in variables at that point in time.



### STACKING

javascript interpreter processes one lone of code at a time. 
when a statement needs data from another function it stacks or pile the new function on top of the current task

### CONSOLE.

- console.info - gen info
- console.warn - used for warnings
- console.error - hold errors
- console.group - group related message together
    - console.groupend
- console.table - outputs a table showing
    - objects 
    - arrays that contain other objects or arrays
- console.assert - test if a condition is met


...to be continued 
# JS BASIC EXECUTION

JS is a synchronoues single threaded languagge, it can only execute one command at a time


> The whole JS runs inside what is called the execution context
> Execution Context is divided into two parts 

## EXECUTION CONTEXT STRUCTURE:

### Memory (Variable Environemt)              ### Code (Thread of Execution)

    1.  all variables and functions          1.  Code is executed one line at a time
        stored as key value pairs               


# HOW JS CODE RUNS

> when a JS code is run a global execution context is created

``` javascript
var a = 2;
function functionName(){
    console.log('hello')
}
var print = functionName();
```

> Execution context is created in two phases 
    1. Memory creating phase: JS allocates memory to every function and variable 
        example: var a becomes, a: undefined, and any funcion func is saved as functionName: {   console.log('hello')} (i.e. the entire code of the function)

    2. Code execution phase:
        in line 22: in function execution phase the value 2 is assigned to n, i.e any value which is supposed to be assigned
        in line 26: a function is invoked, and when that happens a brand new execution context is created, and again the variables,parameters of function and functions which are local to the function are stored in the memory of the context(Variable env) and the code is stored in the code(thread of execution)

        return: this states that return the control of the program back to the execution context from which it was invoked, and the execution context of the function which has returned is deleted

        after all the code is finished the global execution context is also deleted.

        the execution context is destroyed and popped off the Call Stack if :
            0. encounters a return statement or
            1. encounters a closing paranthesis `}` of the function code block or
            2. In case of arrow functions without paranthesis, a semi-colon would do the job


# Call Stack
    > its a stack at the bottom of which is the global execution context, in other words whenever JS program starts to execute the global execution context is pushed into the stack.
    >whenever an execution context is created it is pushed into the stack whenever it is deleted it is popped from the stack
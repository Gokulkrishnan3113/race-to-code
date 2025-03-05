
![banner_thin](https://user-images.githubusercontent.com/6749212/168450952-8a884618-f075-45b7-ba17-762f3ebcab95.png)

Welcome to the rajini++ wiki! rajini++ (a.k.a rajiniPP, pronounced _rajini plus plus_) is a simple programming language created as a hobby project and dedicated to the one and only Superstar. The language has its syntax based on the iconic dialogues of Superstar Rajinikanth. This wiki acts as the official guide to the rajini++ programming language.

rajini++(a.k.a rajiniPP) is the programming language and `rajinipp` is the interpreter for the rajini++ programming language.

This project develops the `rajinipp` interpreter for the rajini++ language and is written written in python🐍. Simply put, the project parses the rajini++ code, converts it to its equivalent python code and executes it.


## Installation
- rajinipp requires **python >= 3.8**. Install python from [here](https://www.python.org/downloads/).
- Install the rajini++ interpreter using the following command:
  `pip install rajinipp`

- test installation: `rajinipp version`

## rajini++ program files
rajini++ programs are stored in files with the `.rpp` extension.

## Running rajini++ programs
the `rajinipp` package needs to be installed in order to run rajini++ programs.
- rajini++ programs can be run using the following commands:
    - `rajinipp run path/to/program.rpp` (or)
    - `python -m rajinipp run path/to/program.rpp`
where the program to run is stored in the `path/to/program.rpp` file.

## Using the rajinipp interpreter
Apart from being able to run rajini++ programs, `rajinipp` also has a tokenizer and an interactive shell(rajinipp>=0.2.0). 

The following are the features/commands supported by the rajinipp package:

### `run`
- The `run` command is used to run a rajini++ program.
  - Example: `rajinipp run path/to/program.rpp`

### `tokenize`
- The `tokenize` command tokenizes the input program and prints the tokens to the command line.
  - Example: `rajinipp tokenize path/to/program.rpp`

### `shell` (*unstable*)
- The `shell` command begins an interactive shell to try out rajini++ commands.
- **NOTE**: The shell uses a simplified parser and currently only supports a subset of the features of the full parser used to parse programs **[conditional statements and loops not supported]**.
- start the shell with the `rajinipp shell` command.
Example:
  
![rajinipp shell](https://user-images.githubusercontent.com/6749212/168477452-0b921cc1-f75e-47e7-ba93-349e13de693d.png)

## The rajini++ Language
The following are the main code constructs supported by rajini++:

### Main method
Every rajini++ program resides within the main method. The main method is of the form:
```
LAKSHMI START
[statements]
MAGIZHCHI
```

where,
- `LAKSHMI START`: denotes the start of the main method.
- `MAGIZHCHI`: denotes the end of the main method.

## Statements
- Every statement in the rajini++ language terminates with a semicolon(`;`).
    - Example: `DOT "Hello, world";` print `Hello, world` to the console.
- Every command supported by rajini++ is **capitalised**.

## Features
rajini++ currently supports the following features:

### Comments
- rajini++ supports single line comments.
- lines beginning with `!!` are treated as comments and are ignored by the interpreter.

Example:
```
LAKSHMI START
!! This is a comment and is ignored by the rajinipp interpreter.
DOT "Hello, world!";
MAGIZHCHI
```
will output `Hello, world!` to the console.
### Printing
The statement `DOT` can be used to print variables, strings, etc.

- The hello world program:
```
LAKSHMI START
DOT "Hello, world!";
MAGIZHCHI
```
will print `Hello, world!` to the console.

#### Printing expressions
- when printing an expression, rajini++ will automatically evaluate the expression before printing it.
- Example: `DOT 5*5;` will output `25.0` to the console.

#### Printing multiple expressions/variables
- rajini++ also supports printing multiple variables/epressions using the same `DOT` statement. This can be done by specifying the expressions/variables one after the other separated by a space.
- Example:

    `DOT "Hello, world! 5 + 5 =" 5+5;`
will output `Hello, world! 5 + 5=10.0` to the console.


### Variables
- rajini++ supports variables of type `boolean`,  `string` and `number`. 
- All variables in rajini++ are globally scoped!

- **NOTE**: Variable names can only contain small letters and underscores!
  
#### Declaring a variable
- whenever a variable is declared, its initial value must be set.
- Variables can be created using the following command:
  
   `AANDAVAN SOLLRAN <variable-name> ARUNACHALAM SEIYARAN <value>;`

#### Accessing variables
- Variavles can be accessed using their names.

#### Assigning values to existing variables
- new values can be assigned to existing variables using the following command:

    `<variable-name> BHAJJI SAAPDU <new-value>;`

**Example program**:
```
LAKSHMI START
!! declare a variable.
AANDAVAN SOLLRAN myvar ARUNACHALAM SEIYARAN 25;

!! access variable and print its value.
DOT "myvar = " myvar;

!! assign new value to variable.
myvar BHAJJI SAAPDU 100;
DOT "new myvar = " myvar;
MAGIZHCHI
```
will output the following:

```
myvar = 25.0
new myvar = 100.0
```

#### Boolean variables
- rajini++ supports boolean variables.
- The term `True` evaluates to true and the term `False` evaluates to false.
  
**Example**:
```
LAKSHMI START
!! declare a boolean variable with value True.
AANDAVAN SOLLRAN truevar ARUNACHALAM SEIYARAN True;

!! declare a boolean variable with value False.
AANDAVAN SOLLRAN falsevar ARUNACHALAM SEIYARAN False;

DOT "truevar = " truevar;
DOT "falsevar = " falsevar;

MAGIZHCHI
```
will output the following:
```
truevar = True
falsevar = False
```

#### String variables
- rajini++ supports string variables.
- anything enclosed within double quotes (`"`) is evaluated as a string.
- example: `"Hello String"` evaluates to a String.

#### Number variables
- rajini++ supports integer and decimal numbers, but all numbers are implicitly represented as `float32`.
- example: `420` and `4.20` evaluates to a number. 


### Arithmetic Operations
rajini++ supports all basic math ops: 
- Addition: `+`
- Subtraction: `-`
- Multiplication: `*`
- Divison: `/`
- Modulo: `%`

**Example** - math ops between two numbers and assigning it to a variable:

```
LAKSHMI START
!! addition operation
AANDAVAN SOLLRAN addvar ARUNACHALAM SEIYARAN 25 + 15;
!! subtraction operation
AANDAVAN SOLLRAN subvar ARUNACHALAM SEIYARAN 25 - 15;
!! multiplication operation
AANDAVAN SOLLRAN mulvar ARUNACHALAM SEIYARAN 5 * 5;
!! division operation
AANDAVAN SOLLRAN divvar ARUNACHALAM SEIYARAN 5 / 5;
!! modulo operation
AANDAVAN SOLLRAN modvar ARUNACHALAM SEIYARAN 51 / 5;
DOT "addvar = " addvar;
DOT "subvar = " subvar;
DOT "mulvar = " mulvar;
DOT "divvar = " divvar;
DOT "modvar = " modvar;
MAGIZHCHI
```
will output the following to the  console:
```
addvar = 40.0
subvar = 10.0
mulvar = 25.0
divvar = 1.0
modvar = 1.0
```

## Logical Operations
rajini++ rupports the following logical operations:
- Greater Than (GT): `>`
- Less Than (LT): `<`
- Greater Than Equal To (GTE): `>=`
- Lesser Than Equal To (LTE): `<=`
- Equal To (EQ): `==`
- Not Equal To (NEQ): `!=`

Example Program:

```
LAKSHMI START
!! Declare variables
AANDAVAN SOLLRAN x ARUNACHALAM SEIYARAN 5.5;
AANDAVAN SOLLRAN y ARUNACHALAM SEIYARAN 15;
AANDAVAN SOLLRAN a ARUNACHALAM SEIYARAN x;
AANDAVAN SOLLRAN b ARUNACHALAM SEIYARAN y;

!! print variables
DOT "x: " x "y: " y;
DOT "a: " a "b: " b;

!! Test Logical Operations
DOT "x > y: " x > y;
DOT "x >= y: " x >= y;
DOT "x < y: " x < y;
DOT "x <= y: " x <= y;
DOT "x == a: " x == a;
DOT "x != b: " x != b;
MAGIZHCHI
```
will result in the following output:
```
x:  5.5 y:  100.0
a:  5.5 b:  100.0
x > y:  False
x >= y:  False
x < y:  True
x <= y:  True
x == a:  True
x != b:  True
```

## Program Flow Control
rajini++ supports the following basic program flow control:
### If statements
if statements in rajini++ has the following syntax:

```
EN PEAR MANICKAM <condition> {
    <statements>
} KATHAM KATHAM;
```
- Nesting of if statements is also supported and has the following syntax:

```
EN PEAR MANICKAM <condition> {
    EN PEAR MANICKAM <condition> {
       .
       .
       .
    } KATHAM KATHAM;
} KATHAM KATHAM;
```

Example Program:
```
LAKSHMI START

!! Declare variable.
AANDAVAN SOLLRAN x ARUNACHALAM SEIYARAN 15;

!! if statement.
DOT "Example: If Statement";
EN PEAR MANICKAM x > 10{
    DOT "x (" x ") is larger than 10!"; 
} KATHAM KATHAM;

DOT "";

!! Nested if statement.
DOT "Example: Nested If Statement";
EN PEAR MANICKAM x > 14{
    DOT "Outer if statement"; 
    EN PEAR MANICKAM x == 15{
        DOT "Inner if statement."; 
        DOT "x (" x ") is equal to 15!"; 
    } KATHAM KATHAM;
} KATHAM KATHAM;

MAGIZHCHI
```

The above program has the following output:
```
Example: If Statement
x ( 15.0 ) is larger than 10!

Example: Nested If Statement
Outer if statement
Inner if statement.
x ( 15.0 ) is equal to 15!
```

### If-Else Statements
if-else statements  in rajini++ build on top of if statements and has the following syntax:

```
EN PEAR MANICKAM <condition> {
    <if statements>
} ENAKKU INNURU PEAR IRUKKU {
    <else statements>
} KATHAM KATHAM;
```

Example Program:
```
LAKSHMI START
!! Declare variable
AANDAVAN SOLLRAN x ARUNACHALAM SEIYARAN 5;

DOT "Example: If-Else Statement";

!! if statement.
EN PEAR MANICKAM x > 10{
    DOT "x (" x ") is larger than 10!";
} !! else statement.
ENAKKU INNURU PEAR IRUKKU{
    DOT "x (" x ") is less than 10!";
} KATHAM KATHAM;

MAGIZHCHI
```

will output the following to the console:

```
Example: If-Else Statement
x ( 5.0 ) is less than 10!
```

### For Loop
for loops in rajini++ has the following syntax:

```
NAA <start_number> THADAVA SONNA <end_number> THADAVA SONNA MADHRI{
    <statements>
}KATHAM KATHAM;
```
where the loop is executed from `start_number`(inclusive) to `end_number`(exclusive).

**NOTE**: For loops internally use the `range(start_number, end_number)` python function.

Example Program:

```
LAKSHMI START
!! for loop example
DOT "For Loop Example";
AANDAVAN SOLLRAN x ARUNACHALAM SEIYARAN 5;
DOT "Before loop: X =" x;
DOT "Running loop from 1...10";
NAA 1 THADAVA SONNA 10 THADAVA SONNA MADHRI{
    x BHAJJI SAAPDU x + 1;
}KATHAM KATHAM;
DOT "After loop: X =" x;
MAGIZHCHI
```

will output the following to the console: 

```
For Loop Example
Before loop: X = 5.0
Running loop from 1...10
After loop: X = 14.0
```

### While Loop
while loops in rajini++ has the following syntax:

```
BABA COUNTING STARTS <condition>{
    <statements>
}KATHAM KATHAM;
```

Example Program:

```
LAKSHMI START
DOT "While Loop Example";
AANDAVAN SOLLRAN ix ARUNACHALAM SEIYARAN 1;
BABA COUNTING STARTS ix<=5{
    DOT ix;
    ix BHAJJI SAAPDU ix + 1;
}KATHAM KATHAM;
MAGIZHCHI
```

will output the following to the console:

```
While Loop Example
1.0
2.0
3.0
4.0
5.0
```

### Break Statement
- rajini++ also supports the break statement to break out of loops.
- It is invoked with the following statement: `BLACK SHEEP;`.

Example Program:

```
LAKSHMI START
DOT "While Loop Example";
AANDAVAN SOLLRAN ix ARUNACHALAM SEIYARAN 1;
BABA COUNTING STARTS True{
    DOT ix;
    ix BHAJJI SAAPDU ix + 1;
    EN PEAR MANICKAM ix > 5{
        DOT "breaking out of loop...";
        BLACK SHEEP;
    }KATHAM KATHAM;
}KATHAM KATHAM;
MAGIZHCHI
```

will output the following:

```
While Loop Example
1.0
2.0
3.0
4.0
5.0
breaking out of loop...
```
#### How the Break statement works
- Internally, the break statement in rajini++ triggers a `rajinipp.exceptions.BreakException` exception to trigger breaking out of the loop.
- Internally, this exception is handled only by the loop statements and hence can be used only within loops(for/while).
- If used outside a loop, this exception is uncaught and exits the program.
  
### Functions
rajini++ supports functions (with no arguemnts) and is of the following syntax:

```
EN VAZHI THANI VAZHI <function-name>
    <statements>
MARAKKADHINGA
```

### Return Statement
Functions in rajini++ also support returning values. Return statements in rajini++ is of the following form:

`IDHU EPDI IRUKKU <return-val>`

#### How the Return statement works
- Internally, the break statement in rajini++ triggers a `rajinipp.exceptions.ReturnException` exception to trigger return statement in the function.
- Internally, this exception is handled only by the functions and hence can be used only within functions.
- If used outside a function, this exception is uncaught and exits the program.

Example Program:

<script src="https://gist.github.com/aadhithya/84db5b4dc83e96478316cf08b1bdd60c.js"></script>

will output the following:

```
Hi from main!
Hello from myfunc_one!
returning ix = 100.0 to main
Value returned from myfunc_one: 100.0`
```

### A Note on the variables in a function
- Since variables in rajini++ are globally scoped, variables declared inside functions are accessible outside the function as well.


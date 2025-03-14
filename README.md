# Lexer (Tokenizer) Project

This project is a simple lexer (tokenizer) example. The lexer reads a text file and breaks its content into tokens. These tokens can later be processed by a compiler or interpreter.

## Features

- **Supports Single-Line Comments:** Processes comments starting with `--`.
- **Supports Multi-Line Comments:** Processes comments enclosed in `/* ... */`.
- **Supports Numbers:** Handles integers (`123`) and real numbers (`45.67`).
- **Supports Strings:** Processes text enclosed in double quotes (`"Hello, World!"`).
- **Supports Keywords:** Recognizes keywords like `if`, `while`, `for`, and `print`.
- **Supports Operators:** Recognizes operators like `==`.

## How Does It Work?

The lexer reads the input file (`input.txt`) and breaks its content into tokens. Each token has a type (e.g., `IF`, `ID`, `NUM`) and a value (e.g., `if`, `x`, `123`). These tokens are then printed to the console.

## Installation

1. **Install JavaCC:**
   - Download and install JavaCC from its [official website](https://javacc.github.io/javacc/).
   - Alternatively, you can add JavaCC to your project using a build tool like Maven or Gradle.

2. **Build the Project:**
   - In the project directory, run the following command to generate the lexer using JavaCC:
     ```bash
     javacc SimpleParser.jj
     ```
   - Then, compile the Java code:
     ```bash
     javac *.java
     ```

3. **Run the Project:**
   - To run the lexer, use the following command:
     ```bash
     java SimpleParser
     ```

## Example Input File

Write the following content into the `input.txt` file:

```
if x 123 45.67 -- This is a comment
while y 987 3.14 -- Another comment
for i 0 10 -- Loop counter
print "Hello, World!" 42 7.89
x == a
/* This is a
   multi-line comment */
```

## Example Output

When you run the program, you should see the following output:

```
IF: if
ID: x
NUM: 123
REAL: 45.67
COMMENT: -- This is a comment
WHILE: while
ID: y
NUM: 987
REAL: 3.14
COMMENT: -- Another comment
FOR: for
ID: i
NUM: 0
NUM: 10
COMMENT: -- Loop counter
PRINT: print
STRING: "Hello, World!"
NUM: 42
REAL: 7.89
ID: x
EQUALS: ==
ID: a
MULTILINE_COMMENT: /* This is a
   multi-line comment */
```

## Token Types

| Token Type          | Description                                      | Example Value         |
|---------------------|--------------------------------------------------|-----------------------|
| `<IF>`              | `if` keyword                                     | `if`                  |
| `<WHILE>`           | `while` keyword                                  | `while`               |
| `<FOR>`             | `for` keyword                                    | `for`                 |
| `<PRINT>`           | `print` keyword                                  | `print`               |
| `<ID>`              | Identifier                                       | `x`, `y`, `i`         |
| `<NUM>`             | Integer                                          | `123`, `0`, `42`      |
| `<REAL>`            | Real number                                      | `45.67`, `3.14`       |
| `<COMMENT>`         | Single-line comment (starts with `--`)           | `-- This is a comment`|
| `<MULTILINE_COMMENT>`| Multi-line comment (enclosed in `/* ... */`)     | `/* This is a comment */` |
| `<STRING>`          | Text enclosed in double quotes                   | `"Hello, World!"`     |
| `<EQUALS>`          | `==` operator                                    | `==`                  |

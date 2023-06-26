# The Scelera Programming Language

Scelera is a general-purpose, high-level, compiled language.

### Hello World

To create a new project in Scelera, execute the following command:
```
$ scelera new hello-world
```

This command will generate a directory named `hello-world` which will contain all the project files.
```
hello-world
├── project.jsonc
└── src
    └── main.sclr
```

The **project.jsonc** file holds the project's configuration, including information such as the libraries required by the program.

The **src/main.sclr** file is the entry point of the code execution. It contains the following content:
```
import { println } from "sclr:io";

func void main() {
  println("hello, world");
}
```

This code outputs the line "hello, world" to the console. To run the code, navigate to your project directory and execute the following command:
```
$ scelera run
```

To obtain a binary file of the program that can run on the current system, use the following command:
```
$ scelera build
```
This command will generate a file with the same name as the project, in this case, a file named `hello-world`.

### Basic Syntax Example

Here's an example program in Scelera that calculates and prints the factorial of the number 5:
```
import { println } from "sclr:io";

func t_u32 factorial(t_u32 num) {
  if (num == 0) return 1;

  mut t_u32 fact = 1;
  for (t_u32 i = 1; i <= num; i++) {
    fact *= i;
  }
  return fact;
}

func void main() {
  t_u32 fact = factorial(5);
  println("${fact}");
}
```

### Code Comments

Code comments are useful for providing explanations and documentation within the code. In Scelera, single-line comments are created using `//`, and multi-line comments are enclosed within `/*` and `*/`. Here are some examples:
```
// Single-line comment

/* multi-line
comment */
```
Scelera allows multi-line comments to be nested inside other multi-line comments, as shown in this example:
```
/* a multi-line comment containing /* another multi-line comment */ */
```
This feature is beneficial when commenting out blocks of code that already contain multi-line comments.


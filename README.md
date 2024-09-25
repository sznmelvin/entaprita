# ENTAPRITA

This is just an interpreter in C. Going to make notes here, nothing special.

## What is an interpreter?

This is a program that is written in a high level language that executes code without converting to machine language.

## Steps in building an interpreter

### Lexing

Also known as scanning. A scanner takes in a string of characters and outputs a stream of tokens. Tokens are the building blocks of the language.

### Parsing

This is the process of developing larger parts from the smaller components. It takes a stream of tokens and forms ASTs.(Abstract Syntax Trees or parse trees) It reports syntax errors as well.

### Static Analysis

Binding is basically the language checking where each name is defined. Like the summation `a + b`.<br>
Scope is the region of the program where a name is defined. Like the variable `a` in the function `f` is only defined in the scope of `f` and not outside of it.<br>
Type checking is the process of the checking if the types of the name work together. If they don't, it throws a type error.<br>
Storing Analysis is basically how the language stores the code after understanding it. It can be stored in numerous ways like symbol table.<br>
Middle-End - There is more analysis here before finally generating the machine code in the backend.

### Optimization

Once we understand how a program works, we can switch it out with another program that has the same semantics but executes them more efficiently. This is the process of optimization. It can be done in numerous ways like loop unrolling, constant folding, dead code elimination, etc.<br>

### Runtime

If we compiled it to machine code, we simply tell theoperating system to load the executable and off it goes. If we compiled it to bytecode, we need to start up the VM and load the program into that.

## Reasons to Not Use Just-In-Time (JIT) Compilation:

- More Complex: JIT adds complexity to the language's implementation, which isn't always necessary.
- Extra Memory: JIT requires more memory to store compiled code, which might be an issue in resource-limited environments.
- Less Portable: JIT compiles machine code for specific platforms, making it harder to run the language everywhere.
- Security Risks: JIT can expose security vulnerabilities like code injection.
- Slower Start Times: JIT can slow down initial program execution because it compiles at runtime.

## Why Lisp Compilers Have Interpreters:

- Dynamic Code Execution: Lisp allows you to generate or modify code at runtime, and an interpreter can execute this code immediately.
- Easier Debugging: Interpreters are useful for testing and debugging code interactively without needing to recompile.
- Better Flexibility: Compiling to C helps with portability, but interpreters handle dynamic, on-the-fly code that compilation can't.
- This balance gives Lisp both speed and flexibility.

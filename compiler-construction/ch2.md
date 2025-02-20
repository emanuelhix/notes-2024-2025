# Chapter 2

Goal: `source program` → `[intermediate representations]` → `target program`.

## Example Program for Lvar

```py
x = 12 + 20
print(10 + x)
```

### Key Features Exhibited by This Sample Program  
- Assignment: `var = exp`  
- Binary operation: `12 + 20`  
- Nullary operation: `print(...)`  

#### Why Is `-` Considered a Unary Operator in Lvar?  

In Lvar, `-` is used exclusively for negation, meaning it has only one operand.  
Subtraction is handled as negation followed by addition in the AST.  
This is interesting because subtraction involves both a unary and a binary operation, whereas addition only requires a binary operation.  
This design choice likely simplifies compilation and may also allow for optimization.  

## Concise Definition of Lvar  

```
exp ::= int | input_int() | - exp | exp + exp | exp - exp | (exp)
stmt ::= print(exp) | exp

exp ::= var
stmt ::= var = exp
LVar ::= stmt*
```

### Remarks  

Lvar consists of a sequence of `stmt`s. Each `stmt` can be:  
- `stmt ::= print(exp) | exp | var = exp`  

## Extendible Interpreters  

### Questions  

- Do "real" interpreters use OOP?  

### Approach  

#### Open Recursion  

Open recursion allows a subclass method to override and be called instead of the parent class’s method, even when invoked from within the parent class.  

#### Env  

`Env` is a key-value store mapping variable names to their values.  
It enables variable reuse whenever a variable appears in an expression.  
If a variable lookup fails (e.g., due to an out-of-bounds error or accessing an uninitialized value), the interpreter halts execution.  

## Compilation to x86  

### Nano-Pass Approach  

Each pass over the AST should have a single, clear objective.  
This follows a principle similar to the Single Responsibility Principle, but applied to compilation passes.  

## Passes  

### Remove Complex Operands  

This pass ensures that every argument in Lvar consists of atomic expressions.  
To achieve this, complex operands are replaced with intermediate variables.  

By "atomic expressions," we mean representing `-5` as a single entity rather than as two separate components (`-` and `5`).  

Example transformation:  

```py
# Program A
x = -5 + 5
print(x + 10)
```

```py
# Program B
tmp_0 = -5
x = tmp_0 + 5
tmp_1 = x + 10
print(x + 10)
```

Here, `-5` is treated as an argument to `+`. Making it atomic simplifies later compilation steps.  

**Does this increase memory usage?**  
At a lower level, introducing more temporary variables could impact memory usage.  

### Monadic Normal Form  

A language is in **monadic normal form** when it distinguishes between pure expressions and those with side effects.  
With this transformation, Lvar now adheres to monadic normal form.  

### Select instructions

This pass translates x86mon, the language of the previous pass, to x86var.
x86var is a subest of x86 that still uses variables.
This pass mainly handles writing assembly for both assignment and the unary addition operation.

### Assign homes

This pass compiles x86var to  a subset of x86var, which no longer uses program name variables.
This is the result of placing all of the program variables in registers or on the stack.  
Notably, the stack is only used if we run out of registers. 

Program B:
```x86
movq $42, a  
movq a, b  
movq b, %rdi  
callq print_int  
```

Program B:
```x86
movq $42, -8(%rbp)  
movq -8(%rbp), -16(%rbp)  
movq -16(%rbp), %rdi  
callq print_int  
```

When program A is compiled to program B, we can see that the actual register locations are used instead of the variables. 

Are program A and program B both runnable? That is, suppose im writing source code for x86 directly- not writing python. Could i mix syntax from program B and syntax and program A? If i compile A to B, only the parts of A that are defined to be compiled for B will be compiled. 

<lua example>

### patch instructions

This pass will compile assign_homes into a subset of x86 that restricts two operands of an operation from being memory locations. Essentially, it handles edge cases of assign_homes.

Why is this problematic? Because we don't know if we're  retrieving the vlaue from the meomry location or sending the memory location itself?




### Solution

in order to fix this problem, the %rax register is used as an intermediary.

So, rather than movq <addr>, <addr2>, we'll do something like movq <addr>, %rax then movq %rax, <addr2>.


### Generate prelude and conclusion

This pass will generate the main function of the program with a prelude and conclusion wrapped around the rest of the program.
### Prelude

handles the "setup" of the stack frame, registers, and other resources.
the prelude does a few things:
1.saves the base pointer to the stack so that the program can return to it later
2. copies the stack pointer to the base pointer, which establishes a new stack frame
3. the stack pointer is adjusted to allocate space for new variables on the stack
4. registers that need to be preserved across function calls will be saved to the stack

### conclusion  
  
handles the cleanup of the stack frame, registers, and other resources.
during this process, a few things happen:  
1. the stack pointer is adjusted, which deallocate sspace that was used for local variables
2. the base pointer is restroed from the stack
3. the ret instruction is used to return control to the caller





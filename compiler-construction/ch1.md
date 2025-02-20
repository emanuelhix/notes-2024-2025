---

**Parker Hix**  

# Chapter 1  

```python
class Constant:
    def __init__(self, value):
        self.value = value

# Instance of the Constant class
eight = Constant(8)

class UnaryOp:
    def __init__(self, op, operand):
        self.op = op
        self.operand = operand

# Create an AST that negates a number
neg_eight = UnaryOp(USub(), eight)

# Caller AST
class Call:
    def __init__(self, func, args):
        self.func = func
        self.args = args

class Name:
    def __init__(self, id):
        self.id = id

# Create an AST node that calls input_int
read = Call(Name('input_int'), [])

# !! Continue later for binary add operations
```

## Partial Evaluator  

### Partial Evaluation  

The compiler starts by computing the pieces of the program that do not depend on any inputs.  

For example:  

```python
print(input_int() + -(2+3))  # Becomes print(input_int() + -5)
```  
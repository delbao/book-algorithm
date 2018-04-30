# How each method works?

### Temporary Variable: 
```
temp = a;
a = b;
b = temp;
```
### Arithmetic operation: 
```
a = a + b
b = a - b
a = a - b
```
### Bitwise XOR operation: 
```
a = a^b
b = a^b
a = a^b
```
# Pros and Cons of Each Method

### Time and Space Overhead

Temporary Variable requires extra memory for the temporary variable. Arithmetic operation incurs the overhead of ALU. Bit operation is the fastest of three. 

### Variable Types

Any kind of variables (even different types) can be swapped by Temporary Variable  whereas only numeric variables can use Arithmetic operation. A chance of overflow also exists. The XOR operation works only with the same data type (same length) and it fails with memory aliased values so extra memory address inequality check is needed.

### Other Concerns

Temporary Variable method is more readable. Most modern compilers can optimize it to be as fast and the same number of registers as the XOR swap. 

In modern CPU with instruction pipelines, the XOR technique is even slower because each operation depends on the previous results.

# Generalization

```
a = a # b
b = a @ b
a = a @ b
```
\# and @ are inverses of each other

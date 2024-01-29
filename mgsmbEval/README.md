# mgsmbCalc Eval Library

This is an library, which evaluates a mathematical term and returns the evaluated value.<br>
I chose to use my own [math library](../mgsmbMath), meaning the algorithms might not be very good until I improve them.<br>
#### Currently, mathematical functions are a bit broken. I am working on fixing that.<br>
<br>

## Using the library

##### This function inside the namespace `Eval` just takes one argument and returns the result as a non-rounded double.<br>
```c++
namespace Eval {
  double eval(const char* termCharPtr) { ... }
}
```
If you haven't already, include the `eval.h` file next to the other includes of your C++ program.<br>
When compiling, you also need to link the eval library to your program. <br>
If you want to compile it yourself, you have to link my math library to the eval library.<br>
<br>

### How to use mathematical functions
Type the function name next to a pair of parentheses.<br>
Type the function argument(s) inside of them. If the function requires multiple arguments, seperate them with a comma. 
As of now, these are the valid functions:
<table>
  <tr>
    <td><b>Function usage</b></td>
    <td><b>Description</b></td>
  </tr>
  <tr>
    <td>pow(a,n)</td>
    <td>a to the power of n</td>
  </tr>
  <tr>
    <td>exp(x) or e(x)</td>
    <td>The exponential function of x</td>
  </tr>
  <tr>
    <td>log(b,x)</td>
    <td>The logarithm base b of x</td>
  </tr>
  <tr>
    <td>ln(x)</td>
    <td>The natural logarithm of x</td>
  </tr>
  <tr>
    <td>sin(x)</td>
    <td>The sine function of x</td>
  </tr>
  <tr>
    <td>cos(x)</td>
    <td>The cosine of x</td>
  </tr>
  <tr>
    <td>tan(x)</td>
    <td>The tangent of x</td>
  </tr>
  <tr>
    <td>arcsin(x) or asin(x)</td>
    <td>The inverse sine of x</td>
  </tr>
  <tr>
    <td>arccos(x) or acos(x)</td>
    <td>The inverse cosine of x</td>
  </tr>
  <tr>
    <td>arctan(x) or atan(x)</td>
    <td>The inverse tangent of x</td>
  </tr>
</table>

<br>

#### Example program using eval
```c++
#include <iostream>
#include "../includes/eval.h"

main() {
  const char* exampleTerm = "2*log(10,2+sin(3))";
  double result = Eval::eval(exampleTerm);
  std::cout << exampleTerm << " = " << result << std::endl;
  return 0;
}
```
<br>
<br>

## Current issues
1. Broken mathematical functions
2. Data is being lost at double to string conversion
3. Bad math library
<br>

## To do list
1. Fix mathematical functions
2. Write own function for double to string conversion
4. Improve my math library
5. Improve code
6. Add constants (such as pi)
7. Make the library faster

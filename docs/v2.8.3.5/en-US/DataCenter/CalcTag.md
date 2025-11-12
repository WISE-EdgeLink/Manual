## Configure Calculation Tag　　

Calculation tag is a kind of special tags, the value of which indicates the calculation result of an formula. The parameter of this formula can be a tag or a constant. Also, the expression can utilize some common calculation methods, including arithmetic & logic operation and trigonometric function, etc..

Calculation tag can perform some relatively complex operations, such as converting the acquired sensor value to the real physical quantity (liquid level, wind speed, etc.), so as to make the computation less intensive for the upper computer as well as the device more intelligent.

Each calculation tag corresponds to one expression which may support at most 8 tags as its input variables. For users' convenience, 8 tags are represented by A, B, C, D, E, F, G and H (case insensitive) in the expression.

### Add Calculation Tag

Please follow the procedures to add a calculation tag:

1. Double-click on "Calculation Tag" in the left tree menu.

2. Click "Add" button to add a new calculation tag.

3. Fill in the basic information. "Periods (s)" specifies how often the tags are calculated, and its unit is second.

4. Enter an expression. Uses can select default function or operator from the pull-down lists or type them manually. The example figure shows the calculation expression of "Lighting Failure", the expression logic of which is that the lighting is failed when the value of any tag in four switches is 0.

5. Double-click the variable box to add a tag.

6. Click "OK" button to save the changes.

![](CalcTag_1.png)

### Expression Check

On the right of "Expression" box there is a calculator button![](CalcTag_3.png). Click it to open "Calc Expression" window shown as below. This interface is roughly the same as "Advanced" setting interface in the above, but with a "=" button and a box displaying the operation result. Besides, the variable boxes here require users to input the variable values rather than tag names.

![](CalcTag_2.png)

To verify the expression is correct or not, users can click this button![](CalcTag_4.png)to get the result, then review it to see its correctness. After the expression has been verified, click "OK" button to update the value; if users do not want to update it, click "Cancel" button.　

### Function and Operator Description

Through the drop-down boxes, users can set the functions and operators calculation tag supports, which is divided into five categories: "Mathematical", "Functions", "Trigonometry", "Assignment" and "Boolean logic". Moreover, "Constant" box is also provided, allowing users to select from three constants: pi (the ratio of the circumference to the diameter of a circle), epsilon (the smallest positive double value that is greater than zero) and inf (infinity).

As shown in the figure below, the functions or operators listed in the box can be classified into three types: 1. With no brackets, this indicates binary operations (labeled with 1); 2. With brackets but no comma, this means this function only has one parameter (labeled with 2); 3. With brackets and comma, this means the function supports more than one parameter (labeled with 3).

![](CalcTag_5.png)

All functions and operators are described as follows:

(0) Arithmetic & Assignment Operators

| OPERATOR | DEFINITION                                              |
| ------ | --------------------------------------------- |
|  +       | Addition between x and y.  (eg: x + y)                  |
|  -       | Subtraction between x and y.  (eg: x - y)               |
|  *       | Multiplication between x and y.  (eg: x * y)            |
|  /       | Division between x and y.  (eg: x / y)                  |
|  %       | Modulus of x with respect to y.  (eg: x % y)            |
|  ^       | x to the power of y.  (eg: x ^ y)                       |
|  :=      | Assign the value of x to y. Where y is either a variable<br> or vector type.  (eg: y := x)|
|  +=      | Increment x by the value of the expression on the right<br> hand side. Where x is either a variable or vector type.<br>(eg: x += abs(y - z))                                   |
|  -=      | Decrement x by the value of the expression on the right<br> hand side. Where x is either a variable or vector type.<br> (eg: x[i] -= abs(y + z))                                |
|  *=      | Assign the multiplication of x by the value of the<br> expression on the righthand side to x. Where x is either<br> a variable or vector type.<br> (eg: x *= abs(y / z))                                   |
|  /=      | Assign the division of x by the value of the expression<br> on the right-hand side to x. Where x is either a<br> variable or vector type.  (eg: x[i + j] /= abs(y * z))  |
|  %=      | Assign x modulo the value of the expression on the right<br> hand side to x. Where x is either a variable or vector<br> type.  (eg: x[2] %= y ^ 2)                              |


(1) Equalities & Inequalities

| OPERATOR | DEFINITION                                              |
| ------ | --------------------------------------------- |
| == or =  | True only if x is strictly equal to y. (eg: x == y)     |
| <> or != | True only if x does not equal y. (eg: x <> y or x != y) |
|  <       | True only if x is less than y. (eg: x < y)              |
|  <=      | True only if x is less than or equal to y. (eg: x <= y) |
|  >       | True only if x is greater than y. (eg: x > y)           |
|  >=      | True only if x greater than or equal to y. (eg: x >= y) |


(2) Boolean Operations

| OPERATOR | DEFINITION                                              |
| ------ | --------------------------------------------- |
| true     | True state or any value other than zero (typically 1).  |
| false    | False state, value of exactly zero.                     |
| and      | Logical AND, True only if x and y are both true.<br> (eg: x and y)                                           |
| mand     | Multi-input logical AND, True only if all inputs are<br> true. Left to right short-circuiting of expressions.<br> (eg: mand(x > y, z < w, u or v, w and x))               |
| mor      | Multi-input logical OR, True if at least one of the<br>| inputs are true. Left to right short-circuiting of<br> expressions.  (eg: mor(x > y, z < w, u or v, w and x))  |
| nand     | Logical NAND, True only if either x or y is false.<br> (eg: x nand y)                                          |
| nor      | Logical NOR, True only if the result of x or y is false<br> (eg: x nor y)                                           |
| not      | Logical NOT, Negate the logical sense of the input.<br> (eg: not(x and y) == x nand y)                          |
| or       | Logical OR, True if either x or y is true. (eg: x or y) |
| xor      | Logical XOR, True only if the logical states of x and y<br> differ.  (eg: x xor y)                                  |
| xnor     | Logical XNOR, True iff the biconditional of x and y is<br> satisfied.  (eg: x xnor y)                              |
| &        | Similar to AND but with left to right expression short<br> circuiting optimisation.  (eg: (x & y) == (y and x))    |
| |        | Similar to OR but with left to right expression short<br> circuiting optimisation.  (eg: (x | y) == (y or x))     |


(3) General Purpose Functions

| FUNCTION | DEFINITION                                              |
| ------ | --------------------------------------------- |
| abs      | Absolute value of x.  (eg: abs(x))                      |
| avg      | Average of all the inputs.<br> (eg: avg(x,y,z,w,u,v) == (x + y + z + w + u + v) / 6)   |
| ceil     | Smallest integer that is greater than or equal to x.    |
| clamp    | Clamp x in range between r0 and r1, where r0 < r1.<br> (eg: clamp(r0,x,r1))                                    |
| equal    | Equality test between x and y using normalised epsilon  |
| erf      | Error function of x.  (eg: erf(x))                      |
| erfc     | Complimentary error function of x.  (eg: erfc(x))       |
| exp      | e to the power of x.  (eg: exp(x))                      |
| expm1    | e to the power of x minus 1, where x is very small.<br> (eg: expm1(x))                                          |
| floor    | Largest integer that is less than or equal to x.<br> (eg: floor(x))                                          |
| frac     | Fractional portion of x.  (eg: frac(x))                 |
| hypot    | Hypotenuse of x and y (eg: hypot(x,y) = sqrt(x*x + y*y))|
| iclamp   | Inverse-clamp x outside of the range r0 and r1. Where<br> r0 < r1. If x is within the range it will snap to the<br> closest bound. (eg: iclamp(r0,x,r1)                     |
| inrange  | In-range returns 'true' when x is within the range r0<br> and r1. Where r0 < r1.  (eg: inrange(r0,x,r1)           |
| log      | Natural logarithm of x.  (eg: log(x))                   |
| log10    | Base 10 logarithm of x.  (eg: log10(x))                 |
| log1p    | Natural logarithm of 1 + x, where x is very small.<br> (eg: log1p(x))                                          |
| log2     | Base 2 logarithm of x.  (eg: log2(x))                   |
| logn     | Base N logarithm of x. where n is a positive integer.<br> (eg: logn(x,8))                                         |
| max      | Largest value of all the inputs. (eg: max(x,y,z,w,u,v)) |
| min      | Smallest value of all the inputs. (eg: min(x,y,z,w,u))  |
| mul      | Product of all the inputs.<br> (eg: mul(x,y,z,w,u,v,t) == (x * y * z * w * u * v * t)) |
| ncdf     | Normal cumulative distribution function.  (eg: ncdf(x)) |
| nequal   | Not-equal test between x and y using normalised epsilon |
| pow      | x to the power of y.  (eg: pow(x,y) == x ^ y)           |
| root     | Nth-Root of x. where n is a positive integer.<br> (eg: root(x,3) == x^(1/3))                              |
| round    | Round x to the nearest integer.  (eg: round(x))         |
| roundn   | Round x to n decimal places  (eg: roundn(x,3))<br> where n > 0 and is an integer.<br> (eg: roundn(1.2345678,4) == 1.2346)                     |
| sgn      | Sign of x, -1 where x < 0, +1 where x > 0, else zero.<br> (eg: sgn(x))                                            |
| sqrt     | Square root of x, where x >= 0.  (eg: sqrt(x))          |
| sum      | Sum of all the inputs.<br> (eg: sum(x,y,z,w,u,v,t) == (x + y + z + w + u + v + t)) |
| swap     | Swap the values of the variables x and y and return the |
| <=>      | current value of y.  (eg: swap(x,y) or x <=> y)         |
| trunc    | Integer portion of x.  (eg: trunc(x))                   |


(4) Trigonometry Functions

| FUNCTION | DEFINITION                                              |
| ------ | --------------------------------------------- |
| acos     | Arc cosine of x expressed in radians. Interval [-1,+1]<br> (eg: acos(x))                                           |
| acosh    | Inverse hyperbolic cosine of x expressed in radians.<br> (eg: acosh(x))                                          |
| asin     | Arc sine of x expressed in radians. Interval [-1,+1]<br> (eg: asin(x))                                           |
| asinh    | Inverse hyperbolic sine of x expressed in radians.<br> (eg: asinh(x))                                          |
| atan     | Arc tangent of x expressed in radians. Interval [-1,+1]<br> (eg: atan(x))                                           |
| atan2    | Arc tangent of (x / y) expressed in radians. [-pi,+pi]<br> eg: atan2(x,y)                                          |
| atanh    | Inverse hyperbolic tangent of x expressed in radians.<br> (eg: atanh(x))                                          |
| cos      | Cosine of x.  (eg: cos(x))                              |
| cosh     | Hyperbolic cosine of x.  (eg: cosh(x))                  |
| cot      | Cotangent of x.  (eg: cot(x))                           |
| csc      | Cosecant of x.  (eg: csc(x))                            |
| sec      | Secant of x.  (eg: sec(x))                              |
| sin      | Sine of x.  (eg: sin(x))                                |
| sinc     | Sine cardinal of x.  (eg: sinc(x))                      |
| sinh     | Hyperbolic sine of x.  (eg: sinh(x))                    |
| tan      | Tangent of x.  (eg: tan(x))                             |
| tanh     | Hyperbolic tangent of x.  (eg: tanh(x))                 |
| deg2rad  | Convert x from degrees to radians.  (eg: deg2rad(x))    |
| deg2grad | Convert x from degrees to gradians.  (eg: deg2grad(x))  |
| rad2deg  | Convert x from radians to degrees.  (eg: rad2deg(x))    |
| grad2deg | Convert x from gradians to degrees.  (eg: grad2deg(x))  |


(5) String Processing

| FUNCTION | DEFINITION                                              |
| ------ | --------------------------------------------- |
|  = , ==  | All common equality/inequality operators are applicable |
|  !=, <>  | to strings and are applied in a case sensitive manner.  |
|  <=, >=  | In the following example x, y and z are of type string. |
|  < , >   | (eg: not((x <= 'AbC') and ('1x2y3z' <> y)) or (z == x)  |
| in       | True only if x is a substring of y.<br> (eg: x in y or 'abc' in 'abcdefgh')                     |
| like     | True only if the string x matches the pattern y.<br> Available wildcard characters are '*' and '?' denoting<br> zero or more and zero or one matches respectively.<br> (eg: x like y or 'abcdefgh' like 'a?d*h')               |
| ilike    | True only if the string x matches the pattern y in a<br> case insensitive manner. Available wildcard characters<br> are '*' and '?' denoting zero or more and zero or one<br> matches respectively.<br> (eg: x ilike y or 'a1B2c3D4e5F6g7H' ilike 'a?d*h')      |
| [r0:r1]  | The closed interval [r0,r1] of the specified string.<br> eg: Given a string x with a value of 'abcdefgh' then:<br> 1. x[1:4] == 'bcde'<br> 2. x[ :5] == x[:10 / 2] == 'abcdef'<br> 3. x[2 + 1: ] == x[3:] =='defgh'<br> 4. x[ : ] == x[:] == 'abcdefgh'<br> 5. x[4/2:3+2] == x[2:5] == 'cdef'<br><br> Note: Both r0 and r1 are assumed to be integers, where<br> r0 <= r1. They may also be the result of an expression,<br> in the event they have fractional components truncation<br> will be performed. (eg: 1.67 --> 1)                     |
|  :=      | Assign the value of x to y. Where y is a mutable string<br> or string range and x is either a string or a string<br> range. eg:<br> 1. y := x<br> 2. y := 'abc'<br> 3. y := x[:i + j]<br> 4. y := '0123456789'[2:7]<br> 5. y := '0123456789'[2i + 1:7]<br> 6. y := (x := '0123456789'[2:7])<br> 7. y[i:j] := x<br> 8. y[i:j] := (x + 'abcdefg'[8 / 4:5])[m:n]<br><br> Note: For options 7 and 8 the shorter of the two ranges<br> will denote the number characters that are to be copied.|
|  +       | Concatenation of x and y. Where x and y are strings or<br> string ranges. eg<br> 1. x + y<br> 2. x + 'abc'<br> 3. x + y[:i + j]<br> 4. x[i:j] + y[2:3] + '0123456789'[2:7]<br> 5. 'abc' + x + y<br> 6. 'abc' + '1234567'<br> 7. (x + 'a1B2c3D4' + y)[i:2j]                           |
|  +=      | Append to x the value of y. Where x is a mutable string<br> and y is either a string or a string range. eg:<br> 1. x += y<br> 2. x += 'abc'<br> 3. x += y[:i + j] + 'abc'<br> 4. x += '0123456789'[2:7]                               |
| <=>      | Swap the values of x and y. Where x and y are mutable<br> strings.  (eg: x <=> y)                                 |
| []       | The string size operator returns the size of the string<br> being actioned.<br> eg:<br> 1. 'abc'[] == 3<br> 2. var max_str_length := max(s0[],s1[],s2[],s3[])<br> 3. ('abc' + 'xyz')[] == 6<br> 4. (('abc' + 'xyz')[1:4])[] == 4                        |


(6) Control Structures

|STRUCTURE | DEFINITION                                              |
| ------ | --------------------------------------------- |
| if       | If x is true then return y else return z.<br> eg:<br> 1. if (x, y, z)<br> 2. if ((x + 1) > 2y, z + 1, w / v)<br> 3. if (x > y) z;<br> 4. if (x <= 2*y) { z + w };                             |
| if-else  | The if-else/else-if statement. Subject to the condition<br> branch the statement will return either the value of the<br> consequent or the alternative branch.<br> eg:<br> 1. if (x > y) z; else w;<br> 2. if (x > y) z; else if (w != u) v;<br> 3. if (x < y) { z; w + 1; } else u;<br> 4. if ((x != y) and (z > w))<br> &nbsp;&nbsp;&nbsp;{<br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;y := sin(x) / u;<br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;z := w + 1;<br> &nbsp;&nbsp;&nbsp;}<br> &nbsp;&nbsp;&nbsp;else if (x > (z + 1))<br> &nbsp;&nbsp;&nbsp;{<br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;w := abs (x - y) + z;<br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;u := (x + 1) > 2y ? 2u : 3u;<br> &nbsp;&nbsp;&nbsp;}                                                    |
| switch   | The first true case condition that is encountered will<br> determine the result of the switch. If none of the case<br> conditions hold true, the default action is assumed as<br> the final return value. This is sometimes also known as<br> a multi-way branch mechanism.<br> eg:<br> switch<br> {<br> &nbsp;&nbsp;case x > (y + z) : 2 * x / abs(y - z);<br> &nbsp;&nbsp;case x < 3       : sin(x + y);<br> &nbsp;&nbsp;default          : 1 + x;<br> }                                                       |
| while    | The structure will repeatedly evaluate the internal<br> statement(s) 'while' the condition is true. The final<br> statement in the final iteration will be used as the<br> return value of the loop.<br> eg:<br> while ((x -= 1) > 0)<br> {<br> &nbsp;&nbsp;y := x + z;<br> &nbsp;&nbsp;w := u + y;<br> }                                                       |
| repeat/  | The structure will repeatedly evaluate the internal     |
| until    | statement(s) 'until' the condition is true. The final<br> statement in the final iteration will be used as the<br> return value of the loop.<br> eg:<br> repeat<br> &nbsp;&nbsp;y := x + z;<br> &nbsp;&nbsp;w := u + y;<br> until ((x += 1) > 100)                                  |
| for      | The structure will repeatedly evaluate the internal<br> statement(s) while the condition is true. On each loop<br> iteration, an 'incrementing' expression is evaluated.<br> The conditional is mandatory whereas the initialiser<br> and incrementing expressions are optional.<br> eg:<br> for (var x := 0; (x < n) and (x != y); x += 1)<br> {<br> &nbsp;&nbsp;y := y + x / 2 - z;<br> &nbsp;&nbsp;w := u + y;<br> }                                                       |
| break    | Break terminates the execution of the nearest enclosed  |
| break[]  | loop, allowing for the execution to continue on external<br> to the loop. The default break statement will set the<br> return value of the loop to NaN, where as the return<br> based form will set the value to that of the break<br> expression.<br> eg:<br> while ((i += 1) < 10)<br> {<br> &nbsp;&nbsp;if (i < 5)<br> &nbsp;&nbsp;&nbsp;&nbsp;j -= i + 2;<br> &nbsp;&nbsp;else if (i % 2 == 0)<br> &nbsp;&nbsp;&nbsp;&nbsp;break;<br> &nbsp;&nbsp;else<br> &nbsp;&nbsp;&nbsp;&nbsp;break[2i + 3];<br> }                                                       |
| continue | Continue results in the remaining portion of the nearest<br> enclosing loop body to be skipped.<br> eg:<br> for (var i := 0; i < 10; i += 1)<br> {<br> &nbsp;&nbsp;if (i < 5)<br> &nbsp;&nbsp;&nbsp;&nbsp;continue;<br> &nbsp;&nbsp;j -= i + 2;<br> }                                                       |
| return   | Return immediately from within the current expression.<br> With the option of passing back a variable number of<br> values (scalar, vector or string). eg:<br> 1. return [1];<br> 2. return [x, 'abx'];<br> 3. return [x, x + y,'abx'];<br> 4. return [];<br> 5. if (x < y)<br> &nbsp;&nbsp;&nbsp;&nbsp;return [x, x - y, 'result-set1', 123.456];<br> &nbsp;&nbsp;&nbsp;else<br> &nbsp;&nbsp;&nbsp;&nbsp;return [y, x + y, 'result-set2'];                   |
| ?:       | Ternary conditional statement, similar to that of the<br> above denoted if-statement.<br> eg:<br> 1. x ? y : z<br> 2. x + 1 > 2y ? z + 1 : (w / v)<br> 3. min(x,y) > z ? (x < y + 1) ? x : y : (w * v)         |
| ~        | Evaluate each sub-expression, then return as the result<br> the value of the last sub-expression. This is sometimes<br> known as multiple sequence point evaluation.<br> eg:<br> ~(i := x + 1, j := y / z, k := sin(w/u)) == (sin(w/u)))<br> ~{i := x + 1; j := y / z; k := sin(w/u)} == (sin(w/u))) |
| [*]      | Evaluate any consequent for which its case statement is<br> true. The return value will be either zero or the result<br> of the last consequent to have been evaluated.<br> eg:<br> [*]<br> {<br> &nbsp;&nbsp;case (x + 1) > (y - 2)    : x := z / 2 + sin(y / pi);<br> &nbsp;&nbsp;case (x + 2) < abs(y + 3) : w / 4 + min(5y,9);<br> &nbsp;&nbsp;case (x + 3) == (y * 4)   : y := abs(z / 6) + 7y;<br> }                                                       |
| []       | The vector size operator returns the size of the vector<br> being actioned.<br> eg:<br> 1. v[]<br> 2. max_size := max(v0[],v1[],v2[],v3[])                 |

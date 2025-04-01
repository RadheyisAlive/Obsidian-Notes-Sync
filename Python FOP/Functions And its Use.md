- **.isdigit()**  
    function returns a Boolean value TRUE if all the values in the input  
    string are digits; else it returns FALSE. The Python isdigit() string  
    method is used **to check if all the characters in the string are digit values or not**.
- The type() function is mostly used for debugging purposes. Two different types of arguments can be passed to type() function, single and three arguments. If a single argument type(obj) is passed, it returns the type of the given object. If three argument types (object, bases, dict) are passed, it returns a new type object. it can be used as str(type()) to see what is the data tyoe

Python type() function Syn...

x = 10  
print(type(x)  

- Definition and Usage. The str() function **converts the specified value into a string**

We Can use the str(type()) Function to Print the data type of the data entered In the Brackets

- eg if Rad.isdigit():
- SO if you put String and multiply it with some kind of number then It prints the number for that much times eg……

print(”Radhey “ *10)

then it will print Radhey for 10 times as a out put !!

  

We can also add strings like

dog= Sting + Add+is possible

![[Screenshot_(16).png]]

![[Screenshot_(17).png]]

  

![[Python FOP/assets/Functions And its Use/Screenshot_(19).png]]

![[Python FOP/assets/Functions And its Use/Screenshot_(22).png]]

- The input function In Python, we **request user input**  
    using the input() function. This set of code is requesting for user  
    input, and will store it in the message variable. Note: Inputs are  
    automatically saved as strings. Therefore, always convert to integers  
    before doing any math operators like addition / subtraction.  
    

## Python divides the operators in the following groups:

- Arithmetic operators
- Assignment operators
- Comparison operators
- Logical operators
- Identity operators
- Membership operators
- Bitwise operators

---

## Python Arithmetic Operators

Arithmetic operators are used with numeric values to perform common mathematical operations:

|   |   |   |
|---|---|---|
|Operator|Name|Example|
|+|Addition|x + y|

|   |   |   |
|---|---|---|
|-|Subtraction|x - y|
|*|Multiplication|x * y|
|/|Division|x / y|
|%|Modulus|x % y|
|**|Exponentiation|x ** y|
|//|Floor division|x // y|

---

## Python Assignment Operators

Assignment operators are used to assign values to variables:

|   |   |   |
|---|---|---|
|Operator|Example|Same As|
|=|x = 5|x = 5|

|   |   |   |
|---|---|---|
|+=|x += 3|x = x + 3|
|-=|x -= 3|x = x - 3|
|*=|x *= 3|x = x * 3|
|/=|x /= 3|x = x / 3|
|%=|x %= 3|x = x % 3|
|//=|x //= 3|x = x // 3|
|**=|x **= 3|x = x ** 3|
|&=|x &= 3|x = x & 3|
|\|=|x \|= 3|x = x \| 3|
|^=|x ^= 3|x = x ^ 3|
|>>=|x >>= 3|x = x >> 3|
|<<=|x <<= 3|x = x << 3|

---

---

## Python Comparison Operators

![[main-qimg-b1853522cca2c3a17994bc4bc75677c4-pjlq.jpeg]]

Comparison operators are used to compare two values:

|   |   |   |
|---|---|---|
|Operator|Name|Example|
|==|Equal|x == y|

|   |   |   |
|---|---|---|
|!=|Not equal|x != y|
|>|Greater than|x > y|
|<|Less than|x < y|
|>=|Greater than or equal to|x >= y|
|<=|Less than or equal to|x <= y|

---

## Python Logical Operators

Logical operators are used to combine conditional statements:

|   |   |   |
|---|---|---|
|Operator|Description|Example|
|and|Returns True if both statements are true|x < 5 and  x < 10|

|   |   |   |
|---|---|---|
|or|Returns True if one of the statements is true|x < 5 or x < 4|
|not|Reverse the result, returns False if the result is true|not(x < 5 and x < 10)|

---

## Python Identity Operators

Identity operators are used to compare the objects, not if they are  
equal, but if they are actually the same object, with the same memory  
location:  

|   |   |   |
|---|---|---|
|Operator|Description|Example|
|is|Returns True if both variables are the same object|x is y|

|   |   |   |
|---|---|---|
|is not|Returns True if both variables are not the same object|x is not y|

---

## Python Membership Operators

Membership operators are used to test if a sequence is presented in an object:

|   |   |   |
|---|---|---|
|Operator|Description|Example|
|in|Returns True if a sequence with the specified value is present in the object|x in y|

|   |   |   |
|---|---|---|
|not in|Returns True if a sequence with the specified value is not present in the  <br>object|x not in y|

---

## Python Bitwise Operators

Bitwise operators are used to compare (binary) numbers:

|   |   |   |   |
|---|---|---|---|
|Operator|Name|Description|Example|
|&|AND|Sets each bit to 1 if both bits are 1|x & y|

|   |   |   |   |
|---|---|---|---|
|\||OR|Sets each bit to 1 if one of two bits is 1|x \| y|
|^|XOR|Sets each bit to 1 if only one of two bits is 1|x ^ y|
|~|NOT|Inverts all the bits|~x|
|<<|Zero fill left shift|Shift left by pushing zeros in from the right and let the leftmost bits fall  <br>off|x << 2|
|>>|Signed right shift|Shift right by pushing copies of the leftmost bit in from the left, and let  <br>the rightmost bits fall off|x >> 2|

|   |   |
|---|---|
|Operator|Description|
|`()`|Parentheses|

|   |   |
|---|---|
|`**`|Exponentiation|
|`+x`   <br>  <br>`-x`   <br>  <br>`~x`|Unary plus, unary minus, and bitwise NOT|
|`*`   <br>  <br>`/`   <br>  <br>`//`   <br>  <br>`%`|Multiplication, division, floor division, and modulus|
|`+`   <br>  <br>`-`|Addition and subtraction|
|`<<`   <br>  <br>`>>`|Bitwise left and right shifts|
|`&`|Bitwise AND|
|`^`|Bitwise XOR|
|`\|`|Bitwise OR|
|`==`   <br>  <br>`!=`   <br>  <br>`>`   <br>  <br>`>=`   <br>  <br>`<`   <br>  <br>`<=`   <br>  <br>`is`   <br>  <br>`is not`   <br>  <br>`in`   <br>  <br>`not in`|Comparisons, identity, and membership operators|
|`not`|Logical NOT|
|`and`|AND|
|`or`|OR|
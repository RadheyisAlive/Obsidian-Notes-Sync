![[image 17.png]]

Dynamic means **the memory is allocated during runtime (execution of the program) from the heap segment**. Initializationmalloc() allocates a memory block of given size (in bytes) and returns a pointer to the beginning of the block. malloc() doesn't initialize t.11 Oct 2024  
  

**Automatic allocation refers to the allocation of memory during the execution of a program in a stack, whereas dynamic allocation is the allocation of memory during runtime from the heap**

  

  

what is the use of strcpy is that it just copies the string nothing else dude !!

`int` `main()`

`{`

`char` `str1[] = "Hello World!";`

`char` `str2[] = "GfG";`

`char` `str3[40];`

`char` `str4[40];`

`char` `str5[] = "GeeksForGeeks";`

`strcpy(str2, str1);`

`strcpy(str3, "Copy successful");`

`strcpy(str4, str5);`

`printf("str1: %s\nstr2: %s\nstr3: %s\nstr4:%s\n", str1,`

`str2, str3, str4);`

`return` `0;`

`}`

---

**Output**  
  
  
`str1: Hello World! str2: Hello World! str3: Copy successful str4:GeeksForGeeks`

  

  

  

this is for the bash scripts for example this one  
  

```JavaScript
#!/bin/bash
if [ "$#" -ne 2 ]; then
# condition not satisfied, skip to end of script
else
file1="$1"
file2="$2"
if [ -e "$file1" ] && [ -e "$file2" ]; then
if [ "$file1" -nt "$file2" ]; then
# Scenario 1 happens
elif [ "$file2" -nt "$file1" ]; then
# Scenario 2 happens
else
# Scenario 3 happens
fi
else
# cannot do any scenario
fi
fi
```

## **1. Comparison Operators (for Numbers)**

Used within `**[ ]**` **or [[ ]]** to compare numeric values.

|   |   |   |
|---|---|---|
|**Operator**|**Description**|**Example**|
|`-eq`|Equal|`[ "$x" -eq "$y" ]`|
|`-ne`|Not equal|`[ "$x" -ne "$y" ]`|
|`-gt`|Greater than|`[ "$x" -gt "$y" ]`|
|`-lt`|Less than|`[ "$x" -lt "$y" ]`|
|`-ge`|Greater than or equal to|`[ "$x" -ge "$y" ]`|
|`-le`|Less than or equal to|`[ "$x" -le "$y" ]`|

---

## **2. String Comparison Operators**

Used to compare strings in `**[ ]**` **or [[ ]]** blocks.

|   |   |   |
|---|---|---|
|**Operator**|**Description**|**Example**|
|`=`|Strings are equal|`[ "$str1" = "$str2" ]`|
|`!=`|Strings are not equal|`[ "$str1" != "$str2" ]`|
|`<`|String 1 is less than String 2 (lexicographically)|`[[ "$str1" < "$str2" ]]`|
|`>`|String 1 is greater than String 2|`[[ "$str1" > "$str2" ]]`|
|`-z`|String is empty|`[ -z "$str" ]`|
|`-n`|String is not empty|`[ -n "$str" ]`|

---

## **3. Logical Operators**

Used to **combine conditions**.

|   |   |   |
|---|---|---|
|**Operator**|**Description**|**Example**|
|`&&`|Logical AND|`[ "$x" -gt 0 ] && [ "$y" -gt 0 ]`|
|`||`|
|`!`|Logical NOT|`[ ! -e "$file" ]`|

---

## **4. File Test Operators**

Used to **check file properties**.

|   |   |   |
|---|---|---|
|**Operator**|**Description**|**Example**|
|`-e`|File exists|`[ -e "$file" ]`|
|`-f`|File exists and is a regular file|`[ -f "$file" ]`|
|`-d`|File is a directory|`[ -d "$dir" ]`|
|`-s`|File is not empty|`[ -s "$file" ]`|
|`-r`|File is readable|`[ -r "$file" ]`|
|`-w`|File is writable|`[ -w "$file" ]`|
|`-x`|File is executable|`[ -x "$file" ]`|
|`-nt`|File1 is newer than File2|`[ "$file1" -nt "$file2" ]`|
|`-ot`|File1 is older than File2|`[ "$file1" -ot "$file2" ]`|

---

## **5. Arithmetic Operators (Using** `**(( ))**`**)**

Used to perform **arithmetic operations** in Bash.

|   |   |   |
|---|---|---|
|**Operator**|**Description**|**Example**|
|`+`|Addition|`(( sum = x + y ))`|
|`-`|Subtraction|`(( diff = x - y ))`|
|`*`|Multiplication|`(( prod = x * y ))`|
|`/`|Division|`(( quot = x / y ))`|
|`%`|Modulus (remainder)|`(( mod = x % y ))`|
|`++`|Increment|`(( x++ ))`|
|`--`|Decrement|`(( y-- ))`|

---

## **6. Special Variable Operators**

These operators help in **variable substitution and checking**.

|   |   |   |
|---|---|---|
|**Operator**|**Description**|**Example**|
|`${var:-default}`|Use default value if `var` is unset or empty|`echo ${name:-"Guest"}`|
|`${var:=default}`|Set default value to `var` if it is unset or empty|`echo ${name:="Guest"}`|
|`${var:+alt}`|Use alternate value if `var` is set|`echo ${name:+Hello}`|
|`${var:?error}`|Print error if `var` is unset|`echo ${name:?"Name required"}`|
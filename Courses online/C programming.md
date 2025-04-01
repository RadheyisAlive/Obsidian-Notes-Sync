I am learning it from w3 schools it clears the concepts!!

[https://www.w3schools.com/c/index.php](https://www.w3schools.com/c/index.php)

# C Install IDE

An IDE (Integrated Development Environment) is used to edit AND compile the code.

Popular IDE's include Code::Blocks, Eclipse, and Visual Studio. These are all free, and they can be used to both edit and debug C code.

**Note:** Web-based IDE's can work as well, but functionality is limited.

We will use **Code::Blocks** in our tutorial, which we believe is a good place to start.

  

  

|   |   |
|---|---|
|Escape Sequence|Description|
|\t|Creates a horizontal tab|
|\\|Inserts a backslash character (\)|
|\"|Inserts a double quote character|

  

printf("Hello World!"); // This is a comment

  

|   |   |   |   |
|---|---|---|---|
|Data Type|Size|Description|Example|
|`int`|2 or 4 bytes|Stores whole numbers, without decimals|`1`|
|`float`|4 bytes|Stores fractional numbers, containing one or more decimals. Sufficient for storing 6-7 decimal digits|`1.99`|
|`double`|8 bytes|Stores fractional numbers, containing one or more decimals. Sufficient for storing 15 decimal digits|`1.99`|
|`char`|1 byte|Stores a single character/letter/number, or ASCII values|`'A'`|

  

|   |   |   |
|---|---|---|
|Format Specifier|Data Type|Try it|
|`%d` or `%i`|`int`|[Try it »](https://www.w3schools.com/c/tryc.php?filename=demo_format_spec_di)|
|`%f` or `%F`|`float`|[Try it »](https://www.w3schools.com/c/tryc.php?filename=demo_format_spec_f)|
|`%lf`|`double`|[Try it »](https://www.w3schools.com/c/tryc.php?filename=demo_format_spec_lf)|
|`%c`|`char`|[Try it »](https://www.w3schools.com/c/tryc.php?filename=demo_format_spec_c)|
|`%s`|Used for **[strings](https://www.w3schools.com/c/c_strings.php) (text)**, which you will learn more about in a later chapter||

  

- This is the code for printing till one point digits this is the way to do that

```Plain
float myScore = 9.5;
printf("%.f", myScore);
```

  

  

- mUse **type conversion** to make sure that the **result** of the following example is `1.5`, and not just `1`.

```Plain
float sum = (float)3 / 2;
printf("%.1f", sum);
```

- Make sure that the value of the following variable is not possible to change:

```Plain
 const int hoursPerDay = 24;
```
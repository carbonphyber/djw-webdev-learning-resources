PHP
===

About
-----

PHP is a scripting language originally designed to make creating dynamic web pages incredibly simple.

Hello World
-----------

First make sure your PHP interpreter is installed:

Execute ```php --version``` from the command line (CLI).

If you get a shell error, PHP is not installed in your environment and you need to get assistance to install PHP (that was beyond the scope of this document).

We will now assume you have PHP installed in your environment.

Copy-paste this content to a file `helloworld.php`:

```php
<?php
echo "Hello World\n";
//?>
```

Now execute this file using PHP: ```php helloworld.php```.  You should see the output ```Hello World.```

Language Basics
---------------

PHP is a procedural language with Object-Oriented features.  The PHP library has a fantastic number of global functions and constants (which is generally considered bad programming).

PHP is a loosely typed language with no need for variable instantiation.  Uninstantiated variables are assumed to be of type `null`.

PHP code is interpreted and compiled (in one step), on every script execution. There exist opcache libraries such as EA and APC.

Data Types
----------

 * `null` - the absense of a value
 * `bool` - a boolean
 * `integer` - a "whole" number.  On 64-bit architectures, numbers between 2^63 + 1 and 2^64 - 1 can not be represented by the integer data type because there is no "unsigned" type in PHP.
 * `float` - floating point number
 * `string` - a byte array.  Note: PHP arrays use C-strings internally so the null-byte (`\0`) will terminate a PHP string
 * `array` - a key-value store.  All arrays are inherently associative.  Note: Be careful about using keys that are integers / strings that coerce into integers.
 * `resource` - a type that is reserved for dealing with resources.  These typically are built into the language.
 * `object` - a class instance
 * `function` - new to PHP 5.3, functions are "first-class".
 * `callable` - a way to reference a function.

Loose Types
-----------

PHP is a loosely-typed language. This means that using the double-equals operator to test equality will test only the value and not the type.  If the operands are two different data types, one or both will be coerced.

There are many values that are considered "falsy".  For example:

 * `null`
 * `false` - boolean
 * `0` - integer
 * `0.00` - float
 * `''` - empty string
 * `'0'` - the string that contains the character 0 / zero
 * `array()` - the empty array



... to be continued...


Dynamic Linking
---------------

PHP allows you to separate your code into multiple files.  The following functions allow you to execute other PHP scripts:

 * `include` - execute another PHP script (the script can be executed multiple times if it is called multiple times)
 * `include_once` - execute another PHP script (the script won't be executed multiple times)
 * `require` - execute another PHP script but throw a fatal error if the script is not found (the script can be executed multiple times if it is called multiple times)
 * `require_once` - execute another PHP script but throw a fatal error if the script is not found (the script won't be executed multiple times)

Comments
--------

PHP is a mishmash of many different languages. As such, there are at least three accepted commenting styles:

 * `// this is a single-line comment` - single-line comments
 * `# this is a single-line comment` - shell-style comments
 * `/* this is a multi-line comment */` - C-style multi-line comments

Validation Operators and Functions
----------------------------------

Some suggested helper operators and functions for validation

 * `==` and `===` - "Equality" operator and "Identical" operator. @see [PHP Comparison Operators at PHP.net](http://us3.php.net/manual/en/language.operators.comparison.php)
 * `empty` - Function detects if a variable has a falsy value. Note: you _must_ pass a variable (with a variable identifier) to this function... you can't use the return value of a function or a null/boolean/integer/string/array literal.
 * `isset` - Function to detect if a value is "not NULL".  Warning - this function's return value has changed a few times in recent versions.
 * `ctype_alnum` - Does the input consist entirely of alphanumeric characters? Note: requires a string as input -- make sure to cast input into a string.
 * `ctype_digit` - Does the input consist entirely of decimal (0-9) characters? Note: requires a string as input -- make sure to cast input into a string.
 * `strcmp` - String comparison function (implemented like the C-ancestor).  Returns 0 iff the two parameters are string-identical.
 * `strpos` - Substring position detection.  "What position inside the first parameter+string is the second parameter+string?" (implemented like the C-ancestor... except for the return value).  Returns FALSE if not found; Returns 0 iff the second parameter begins at the first character inside of the first parameter. Use `===` to compare the result of this function!!!
 * `in_array` - Does the first parameter exist as an element in the second parameter?
 * `preg_match` - A regular-expression test function. @see [PCRE patterns at PHP.net](http://us3.php.net/manual/en/pcre.pattern.php)



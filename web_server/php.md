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

 * `// this is a comment` - single-line comments
 * `/* this is a comment */` - C-style multi-line comments
 * `# this is a comment` - shell-style comments

String Validation
-----------------

Some suggested helper functions for validation

 * `ctype_alnum` - 
 * `ctype_digit` - 

... to be continued...


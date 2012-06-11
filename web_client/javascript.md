JavaScript
==========
Not to be confused with Java.  These two languages share next to nothing.

JavaScript is a language that's found in all major modern web browsers as a way to add behavior to web pages. It is also recently used for some server-side programming.

Hello World
-------------

```javascript
    /**
     * Define a function "foo"
     */
    var foo = function () {
        alert("Hello world."); // the "alert" function is defined in all browsers
    };
    /**
     * Execute the function
     */
    foo();
```

Brief History
-------------

JavaScript was originally invented and implemented for the Netscape browser in 1994.  It adds behavior to web pages (assuming the browser supported it).  It has grown quickly more complex and is currently one of the most-used programming languages in the world.

The ECMA organization adopted the core of JavaScript circa 1996.  ECMAScript is the ECMA organization's specification of their language while JavaScript and Adobe's ActionScript are near-cousins of the ECMAScript spec.

Quick Start
-----------
JavaScript is quick and easy to set up in a web browser.

1. Create a new text file with name `helloworld.html`.
2. Open the file in an editor and add the following code to the file:

    ```html
    <html>
    <body>
        <script type="text/javascript">
            alert("hello world");
        </script>
    </body>
    </html>
    ```
    Note that this is less than ideal HTML code.  Read up on `DOCTYPE`s to learn more.  I recommend you use the DOCTYPE for either `XHTML 1.0 STRICT` or `HTML 5` to learn web programming.

3. Save the file.
4. Open the file in your browser.
5. You should see an empty web page (no title or body content) with an `alert` message with the string `"hello world"`.
6. You can now modify the JavaScript code inside of the `<script>` tags.

Language Overview
-----------------
* Turing-complete
* function-based scoping with closures
* "protoype"-based language (not class-based object-oriented)
* single-threaded.  you can defer code, but only one thread ever runs so deferred code waits until all currently-running scripts finish.
* event-based with callbacks (lamdbas)


Environment
-----------
1. browser or server (node.js)
2. interpreter (SpiderMonkey, V8, etc.)
3. console

Data Types
----------
1. `undefined` -- the lack of an assignment leaves a variable `undefined`
2. `numeric` -- integers, floats, longs, doubles, etc. are all of type `numeric`
3. `string`
4. `array` -- an array type with only integer (numeric) keys
5. `function` -- variable values can be functions!  The term for this is `first class functions`
6. `object` -- an extensible object and a dictionary in one!  Can be treated like an associative array.
7. `RegExp` (Regular Expression) -- 
* note there is no `null` datatype; developers sometimes mistakenly use it interchangably with `undefined`
All data types can be modified via the `prototype` property -- but there is a tradeoff to this!

Operators
---------
Many standard operators of common languages:

* `+` addition (or string concatenation... depending on context/operand data types)
* `-` subtraction
* `*` multiplication
* `/` division
* `.` Key accessor within object (for a key known in the code)

```javascript
    var object = new Object();
    object.myNewKey = 2;
    alert(object.myNewKey);
```
Scoping
-----------------
* All scoping is function-based.
* All variables are global unless defined to be local using the `var` keyword.
* When JavaScript runs in a browser, the `window` object is the global scope.
* Variables are automatically `closure`d into all functions defined in the scope where the variable was defined.

Features to Avoid
-----------------
* `eval` -- extremely insecure
* `call`-- alters the scope of the function when it runs
* `apply`-- alters the scope of the function when it runs

Syntax
------------------
Control structures

if / else if / else

```javascript
    if () {
        // 
    } else if () {
        // 
    } else {
        // 
    }
```

switch

```javascript
    switch (/* test possible values against this expression */) {
        case "one":
            // do stuff
            break;
        case 1:
            // do stuff
            break;
        case undefined:
            // do stuff
            break;
        default:
            // do stuff
            break;
    }
```

for

```javascript
    var arrayValues = ["a", "b", "c"],
        arrayLength,
        i;
    for (i = 0, arrayLength = arrayValues.length; i < arrayLength; i++) {
        // 
    }
```

for-in

```javascript
    var arrayAssociative = {"a": "alpha", "b": "beta", "c": "gamma"},
        thisKey;
    for (thisKey in arrayAssociative) {
        thisKey; // "a", "b", "c", etc
        arrayAssociative[thisKey]; // "alpha", "beta", "gamma", etc
    }
```

Object creation

```javascript
    var myFirstObject = new Object();
    var mySecondObject = new Object; // 
    var myThirdObject = {}; // this is an object-literal (JSON)
    var myFourthObject = {
        "someKey": "someValue"
    }; // this is an object-literal (JSON)
```



Language Reference
------------------
* [JavaScript RegExp Object on Regular-Expressions.info](http://www.regular-expressions.info/javascript.html "JavaScript RegExp Object")

Reference Books
---------------
* [JavaScript the Good Parts](http://www.amazon.com/JavaScript-Good-Parts-Douglas-Crockford/dp/0596517742) Douglas Crockford

Respected JavaScript Developers
-------------------------------
* [Douglas Crockford](http://crockford.com/)
* [John Resig](http://ejohn.org/)
* [Paul Irish](http://paulirish.com/)
* [Jeff Atwood](http://www.codinghorror.com/blog)
* [Thomas Fuchs](http://mir.aculo.us/)
* [Jonathan Snook](http://snook.ca/)
* Brendan Eich -- Inventor of JavaScript

Environment Reference
---------------------
* content type

    * `text/javascript`
    * `application/javascript`
    * `text/ecmascript`
    * `application/ecmascript`

    see [JavaScript MIME Type on Anne van Kesteren's Blog](http://annevankesteren.nl/2006/05/javascript-mime-type "The JavaScript MIME Type explained")

* charset

    I personally recommend UTF-8 or all coding and content purposes where available.

    [Accent Folding For Auto Complete @ A List Apart](http://www.alistapart.com/articles/accent-folding-for-auto-complete/ "Accent Folding For Auto Complete @ A List Apart")

Tool Reference
--------------
* [JSLint](http://www.jslint.com/) A static-analysis tool to help you code your JavaScript to a particular convention and avoid unintended consequences
* [JSHint](http://www.jshint.com/) A variant of JSLint designed to warn you of possible mistakes but less convention-oriented.
* [JSBeautifier](http://jsbeautifier.org/) A tool designed to format JavaScript code or JSON data to your desired specifications (or to make viewing data tolerable)

Language Reference
------------------
* [JavaScript Language Reference at Mozilla Developer Network](https://developer.mozilla.org/en/JavaScript)
* [JavaScript Language Reference at Microsoft Developer Network](http://msdn.microsoft.com/en-us/library/yek4tbz0%28v=VS.94%29.aspx)
* [JSON.org](http://json.org/ "JavaScript object notation reference")

DOM API Reference
-----------------
* [JavaScript DOM Reference at Mozilla Developer Network](https://developer.mozilla.org/en/DOM)
* [JavaScript DOM Reference at Microsoft Developer Network](http://msdn.microsoft.com/en-us/library/hh772384%28v=vs.85%29.aspx)
* [JavaScript DOM Reference for WebKit at Apple](https://developer.apple.com/library/mac/#documentation/AppleApplications/Conceptual/SafariJSProgTopics/WebKitJavaScript.html "JavaScript DOM Reference for WebKit at Apple")

Tutorials
---------

* [Modern Debugging Tips and Tricks @ A List Apart](http://www.alistapart.com/articles/modern-debugging-tips-and-tricks/ "Modern Debugging Tips and Tricks")

Library Reference
-----------------
* DOM abstraction libraries
  1. [JQuery](http://jquery.org/ "JQuery JavaScript Library") Widely popular framework based around a very simple core usage principle
  2. [YUI3](https://developers.yahoo.com/yui/3/ "YAHOO!'s open-sourced framweork (version 3.x)")
  3. [YUI2](https://developers.yahoo.com/yui/2/ "YAHOO!'s open-sourced framweork (version 2.x)") (older version that is not compatible with YUI3)
  4. [Dojo]
  5. [Javelin] Facebook's internal (now open-sourced)
  6. [PrototypeJS](http://prototypejs.org/)

* specialized libraries


Language Quirks
---------------
* [Automatic Semicolon Insertion (ASI)](http://mislav.uniqpath.com/2010/05/semicolons/)
* ```typeof null; // "object"```
* ```typeof undefined; // "undefined"```
* ```parseInt("010"); // returns 8``` ```parseInt``` will assume all inputs that begin with "0" are octal strings. Instead use ```parseInt("010", 10); // returns 10```
* "Dangling Comma" at the end of an array or an object creates a parse-error in Internet Explorer. Examples:
    * `["a", 2,]` is better written as `["a", 2]`
    * `{"a": "alpha", "b": "beta",}` is better written as `{"a": "alpha", "b": "beta"}`

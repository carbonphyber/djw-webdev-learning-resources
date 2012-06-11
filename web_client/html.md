HTML
==========
HTML is a markup language used to describe multimedia documents.  Web browsers and other applications interpret these HTML documents and present the viewer with an interactive experience.

The web is composed of trillions of HTML documents, each with a unique URL. Hyperlinks link content in one document to anther relevant document.  Forms also provide content linking and content creation.

Hello World
-------------
This is the minimal code required to create an HTML5 web page:

```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Hello World.</title>
        </head>
        <body>
            <h1>Hello World.</h1>
        </body>
    </html>
```

Brief History
-------------

HTML is a text-based markup; it is not Turing complete language.  HTML provides data and some semantics, Cascading StyleSheets (CSS) is used to add styling, and JavaScript (or ECMAScript) provides behavior to a document.

More history

* [A Brief History of Markup @ A List Apart](http://www.alistapart.com/articles/a-brief-history-of-markup/ "A Brief History of Markup @ A List Apart")

Quick Start
-----------
Basic HTML is quick and easy to set up in a web browser.

1. Create a new text file with name `helloworld.html`.
2. Open the file in an editor and add the following code to the file:

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <!-- this line is an XML comment -->
            <meta http-equiv="content-type" content="text/html; charset=utf-8" /> <!-- This line defines the content-type and charset the browser/agent should use to interpret this document -->
            <title>Hello World.</title> <!-- This line puts text at the top of the browser window/tab -->
        </head>
        <body>
            <h1>Hello World.</h1> <!-- This is Heading1 text: the largest text on the page that should describe the contents of this document -->
        </body>
    </html>
    ```
    Note that this code uses the HTML5 doctype: ```<!DOCTYPE html>``` (which I recommend).  Read up on `DOCTYPE`s to learn more.

3. Save the file.
4. Open the file in your browser.
5. You should see the text: `"hello world"` in large lettering.
6. You can now modify the markup. Save, refresh in your browser.

HTML Overview
-----------------
* Text-based documents
* Can be shared across many platforms and Operating Systems via `HTTP` / `HTTPS` or local file systems.
* `XML`-like syntax
* Markup adds semantics and multimedia to web documents
* `HTML` is based off of `SGML` -- a markup language used by the publishing industry before browsers were available
* Browsers are free to interpret `HTML` as they wish (or as the user configures the browser).

Environment
-----------
1. browser or agent (an application not directly controlled by a user)
2. Loaded via `HTTP`, `HTTPS`, (or other similar network protocols), or local file system

DOCTYPE
-------
A `DOCTYPE` is a declaration from the developer to a browser/agent that the browser render the document according to a specific ruleset.

`HTML5` is the newest supported DOCTYPE. Other doctypes include: `XHTML 1.0 STRICT`, `XHTML 1.0 TRANSITIONAL`, `XHTML 1.0 LOOSE`, `XHTML 1.0 QUIRKSMODE` (which is less of a standard and more of the lack of a standard), `HTML 4.0 STRICT`, `HTML 4.0 LOOSE`, `HTML 4.0 QUIRKSMODE`, `HTML 3.2`, etc. `XHTML`-based doctypes are fully-XML-compatible versions (they must be well-formed XML), whereas HTML documents are allowed to be sloppy -- the browser will fix issues and present the user with something usable.  Due to the unpredictability of browser handling of bad code (and possible malicious uses), it is strongly reccomended that you learn by using a strict doctype and validating your HTML markup as you learn.

QuirksMode is a well-understood "Doctype" (actually the lack of a correctly-defined DOCTYPE).

Markup
------
HTML is made up of the following components:

* Tags and Elements -- an element is a composite entity which can container either (1) one self-closing tag or (2) one open tag, optional nested content, and one close tag.
* (XML) comments
* PCData
* Whitespace

Whitespace in HTML is complicated. Whitespace between tags is mostly squashed (with the exception of tags like `pre` which retain the exact whitespace characteristics in the markup).

Lifecycle
---------
HTML exists in a saved document/file.  Once that file is opened by a browser/agent, the HTML is parsed and disregarded.  The Document-Object Model (DOM) is the in-memory model, which can generally be thought to be stored as a tree of DOM Nodes (such al HTML Elements, comments, whitespace, etc).  If the DOM is modified after the initial page load, the underlying HTML _is_ _not_ updated with these changes.

Tags
----
Tags are used to create HTML Elements.

* This is an open-script tag: `<script>`
* This is a close-script tag: `</script>`
* This is a self-closing tag: `<hr />`.  There is no such thing as a close-HR (`</hr>`) so this element must be self-closed (as required in XHTML and optional in HTML) or unclosed (as is available in HTML).
* This is a tag: `<span>`
* This is an element composed of two tags: `<span></span>`
* This tag has an attribute `key` and an attribute-value of `value`: `<link key="value" />`

Tag names are case-insensitive.  `<script>` is interpreted the same as `<ScRipT>`.  As a convention, all of my HTML tag names and attribute names are lower-case, with the exception of the `<!DOCTYPE html>` tag name.  This makes it easier to `grep` for tags through an entire codebase.

HTML provides a short list of attributes that are available in any open/self-closing tag on the document, a longer list of attributes that are available to specific tags, and HTML5 allows for arbitrary attributes using the `data-` prefix.

No HTML element may have the same attribute defined twice in the same tag -- this behavior is undefined.  For example:

```html
    <body class="myfirstbody" class="mysecondbody">...</body>
```
The `body` element in the DOM could have the value of either `myfirstbody` or `mysecondbody` -- this behavior is undefined and therefore advisable to avoid.

Tag List
-----------------
The specific tags that are available are dependent on which `DOCTYPE` the document is defined to use.

`HTML5` tags:

* required attributes: `html` 1, `head` 1, `body` 1, `title` 1 (requires exactly one of each)
* special web elements: `a` *, `form` *, `meta` +, `link` *, `script` *, `iframe` *
* heading elements: `h1` 1, `h2` *, `h3` *, `h4` *, `h5` *, `h6` *
* generic elements: `div` *, `p` *, `span` *
* table elements: `table` *, `thead` *, `tfoot` *, `tbody` *, `tr` *, `th` *, `td` *
* form elements: `fieldset` *, `legend` *, `label` *, `input` *, `button` *, `textarea` *, `select` *
* media elements: `img` *, `audio` *, `video` *, `canvas` *, `object` *, `embed` *
* text enhacements: `blockquote` *, `pre` *, `code` *, `del` *, `tt` *, `kbd` *, `strike` *, `em` *, `strong` *, `sub` *, `sup` *, (deprecated: `i` *, `b` *, `u` *)
* and many more.

    see []()

HTML Reference
------------------
* [Safari HTML Reference at Apple](https://developer.apple.com/library/safari/#documentation/AppleApplications/Reference/SafariHTMLRef/Introduction.html "Safari HTML Reference at Apple")

Environment Reference
---------------------
* content type

    * `text/html` -- HTML, XHTML, default for all `*.html` and `*.php` files in PHP
    * `text/xml` - for XHTML strict-XML parsing; required for RSS / Atom feeds; required for XML+XSLT)
    * `application/xhtml+xml` -- 

    * [Content-Typeing XHTML by GreyTower](http://www.greytower.net/archive/articles/xhtmlcontent.html "Content-Typeing XHTML by GreyTower")
    * [Content-Negotiation Techniques to serve XHTML at W3.org](http://www.w3.org/2003/01/xhtml-mimetype/content-negotiation "Content-Negotiation Techniques to serve XHTML at W3.org")

* charset

    * I personally recommend UTF-8 or all coding and content purposes where available.
    * [The UTF-8-Everywhere Manifesto](http://www.utf8everywhere.org/ "UTF8 Everywhere - Text made easy once again")

HTML Security
-------------

* [Postcards from the Post-XSS world](http://lcamtuf.coredump.cx/postxss/ "XSS and other HTML exfiltration security risks")
* [OWASP XSS Prevention CheatSheet](https://www.owasp.org/index.php/XSS_%28Cross_Site_Scripting%29_Prevention_Cheat_Sheet "OWASP XSS Prevention CheatSheet")
* [http://ha.ckers.org/xss.html]("XSS (Cross-Site Scripting) Cheat Sheet")

Glossary
--------

* Charset: "Character Set" -- the encoding used to map binary streams to characters.  Examples: fixed-length characters: {`ASCII`, `ISO-8859-1`}, variable-length characters: {`UTF-8`, `UTF-16`}
* Content-Type: the "type" of document.  Windows uses the "file extension" (the few characters after the last dot/period of the filename) to determine a content-type; The "Content-Type" HTTP header and `<meta ... />` tag is a similar way to describe the same information
* HTML: Hyper Text Markup Language
* W3C:  World Wide Web Consortium

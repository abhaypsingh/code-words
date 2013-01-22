Code Words
==========

Get a handle on unfamiliar code by extracting and visualising the natural language programmers used when writing it.

![Board Game Example](https://raw.github.com/npryce/code-words/master/examples/multiplayer-board-game.png)

An example generated from a multiplayer boardgame written in Java.

Usage
-----

    <language>-code <source-file-or-directory>* | code-to-words -k <stop-keyword-file> ... -s <stop-word-file> ... | wordcloud -o <output-file>.png

E.g.

    java-code project/src/ | code-to-words -k java-stop-words -s cargo-cult-java-stop-words | wordcloud -o project.png


The stop-keyword files and stop-word files must have a single word per
line.

The words in stop-keyword-files are filtered out after identifiers
have been extracted from the language but before any further processing.

The words in stop-word-files are filtered out after the identifiers
have been split into separate words at underscores or camel-case
boundaries and normalised to lowercase.


Languages supported
-------------------

 * C: `c-code`
     * `c-stop-words`: most C keywords
     * `c-primitive-type-stop-words`: ignores basic C types (int, char, etc.)
 * C++: `c++-code`
     * `c++-stop-words`: most C++ keywords
     * `c-primitive-type-stop-words`: ignores basic C types (int, char, etc.)
 * Haskell: `haskell-code`
     * `haskell-stop-words`
 * HTML: `html-text`
     * no stop words file provided. Stop words files for various natural languages can be found on the web.
 * Java: `java-code`.
     * `java-stop-words`: most keywords
     * `java-primitive-type-stop-words`: ignores primitive types
     * `cargo-cult-java-stop-words`: ignores get, set, bean etc.
 * JavaScript: `javascript-code`.
     * `javascript-stop-words`: ignores keywords and reserved words (from ECMA-262 Edition 3)
     * `java-primitive-type-stop-words`: ignores primitive types
     * `nodejs-globals-stop-words`: ignores node.js globals
 * Python: `python-code`
     * `python-stop-words`: most keywords
 * Ruby: `ruby-code`
     * `ruby-stop-words`
 * Scala: `scala-code`
     * `scala-stop-words`
 * PHP: `php-code`
     * `php-stop-words`
     * `php-strict-stop-words`

Examples
--------

Example visualisations of various applications are in the examples/ directory.


Dependencies
------------

To extract text from source code:

 * Bash
 * Gnu Sed
 * Grep
 * Awk

To extract text from HTML:

 * w3m

To visualise the results
 
 * Java 1.6

It should work on any desktop Linux. It does not yet work on MacOS unless you install the Gnu command-line tools.

To compile the Java wordcloud generator:

 * JDK 1.6
 * Gnu Make


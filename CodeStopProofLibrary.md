# Coding Avenue PHP Proof Library

A PHP Proof Library parses, analyzes, and evaluates a PHP file. It aims to help course authors of CodeStop validate the answers of learners. This library is ideally used inside your PHPUnit tests.

## PHP Proof Library has 3 main components

 - **Parse** - Parses the php file and traverse through it to be able to understand fully what is on the code.
 - **Analyze** - Analyze the php file if it follows the PSR2 Coding Standard and Mess Detection.
 - **Evaluate** - Evaluates the php file and gives back the output, returned value or error.

## Terms and Meaning

Before we dig deeper into this library, let's try to identify some terms and their meanings, as used in this wiki.

 - **Code file** - This is the file where this library will look as the code input. Meaning the php file that will be parsed, analyze and evaluated.
 - **Proof file** - A proof file is a PHPUnit test that uses this library.
 - **Test answer** - A Test answer is a php file that would be use as an answer to your course question. This term is primarily use for local testing and setting up the environment.

## File structure requirement

This library requires a certain file structure for it to work properly.

 - All proof files must be placed inside a parent directory and that directory is on the root of your project.
 - All test answers must be placed inside a parent directory and that directory is also on the root of your project.
 - A test answer must have the same file name as the proof file. It should also have the same path part after its parent directory. What this means is that if you have a proof file at `proofs/chapter1/question3.php`, then your test answer for this proof file should be at `testAnswers/chapter1/question3.php`. This example assumes that `proofs` and `testAnswers` are the parent directory of your proof file and test answers. 

# Installation

To install via Composer add the following code to your `composer.json` file:

```
{
     "repositories": [
          {
              "type": "git",
              "url": "https://github.com/CodingAvenue/ca-school-php-proof"
          }
     ],
     "require": {
          "codingavenue/php-proof": "0.0.7"
     }
}
```
Then do `composer update`. Once the composer is installed and upated, you are ready to use this awesome library!

# Configuration for local testing

Coding Avenue Proof Library was created with a mindset that it should work on any environment and not just on the CodeStop Sandbox. This allows authors to test their proof files locally.

In order for this library to work on your environment, create a `proof.json` configuration file on the root directory of your course. `proof.json` only needs 3 settings:

 - **codeFilePath** - This is the path to the file where the php file to be use by this library is located.
 - **answerDir** - This is the base directory for all test answers files.
 - **proofDir** - This is the base directory for all proof files.

Check [File Structure Requirements](https://github.com/CodingAvenue/ca-school-proof-library/wiki#file-structure-requirement) for details.

Once you save your settings, this library should be ready to work on your environment.

# Basic Usage

The PHP Proof Library only requires you to import the Code class `CodingAvenue\Proof\Code` and create an instance of the `Code` class.

```php
use CodingAvenue\Proof\Code;

$code = new Code();
```

With this code, you have the full arsenal of the library on your PHPUnit test. The `Code` class looks at the PHP File that you [configure](https://github.com/CodingAvenue/ca-school-proof-library/wiki/Configuration-for-local-testing) on your `proof.json` file. 

The constructor will throw an error if it does not find the file. So make sure you setup your settings properly.

## Methods

### Main methods

 - **[analyzer](https://github.com/CodingAvenue/ca-school-proof-library/wiki/Analyzer)** - Returns an instance of the `CodingAvenue\Proof\Analyzer` class.
 - **[evaluator](https://github.com/CodingAvenue/ca-school-proof-library/wiki/Evaluator)** - Returns an instance of the `CodingAvenue\Proof\Evaluator` class.
 - **[getNodes](https://github.com/CodingAvenue/ca-school-proof-library/wiki/Nodes)** - Returns an instance of the `CodingAvenue\Proof\Code\Nodes` class.
 - **[find](https://github.com/CodingAvenue/ca-school-proof-library/wiki/Traversing)** - Returns a filtered instance of the `CodingAvenue\Proof\Code\Nodes` class from the selector.

### Other methods

 - **[parse](https://github.com/CodingAvenue/ca-school-proof-library/wiki/Parser)** - Returns the parsed php code by [PHP Parser](https://github.com/nikic/PHP-Parser)
 - **[getConfig](https://github.com/nikic/Config)** - Returns the instance of the Config class that this `Code` instance uses.

# Analyzer

The Analyzer class checks the PHP file for any violation of **PSR2 Coding Standard** and **Mess Detection**.

## Methods

### codingStandard

```php
use CodingAvenue\Proof\Code;

$code = new Code();
$analyzer = $code->analyzer();

$result = $analyzer->codingStandard();
```

`$result` will be an array of violations of the **PSR2 Coding Standard**. Each element of the array is an array with the following keys:

 - **message** - The actual violation message.
 - **line** - The line number from the code where the violation is found.
 - **column** - The column number from the code where the violation is found.

The `codingStandard()` method accepts an optional parameter, `$option`, which is an array. The current supported option is `skipEndTagMessage`, which ignores the violation of a code that has no php end tag `?>` in the PHP file.

### messDetection

```php
use CodingAvenue\Proof\Code;

$code = new Code();
$analyzer = $code->analyzer();

$result = $analyzer->messDetection();
```

`$result` will be an array of violations for possible potential problems on the code. Each element of the array is an array with the following keys:

 - **message** - The actual violation message.
 - **beginLine** - The line where the violation started.
 - **endLine** - The line where the violation ends.

`messDetection()` accepts an optional parameter `$rules`, which is an array of rules to be used for detecting possible problems on the code. The following are the supported rules:

 - `cleancode`
 - `codesize`
 - `controversial`
 - `design`
 - `naming`
 - `unusedcode`

By default, all rules apply to the PHP file.

# Evaluator

The Evaluator class evaluates the PHP file.

```php
use CodingAvenue\Proof\Code;

$code = new Code();
$evaluator = $code->evaluator();

$result = $evaluator->evaluate();
```

`$result` will be an array with the following keys:

 - **result** - the result of the evaluated code. This is the returned value of the code before it exits.
 - **output** - the output of the evaluated code. This is anything that displays on your screen if you run the PHP file  yourself.
 - **error** - If the evaluated code result to any error, the error can be accessed through this.

`evaluate()` accepts the optional parameter `$code`, which is an additional string of code that will be appended to the actual code. `evaluate()` is used to check if a given function gives you the desired result.

Let's look into this code:

```php
function add($firstNumber, $secondNumber)
{
  return $firstNumber + $secondNumber;
}
```

Evaluating the code as it is won't give us a result that we could use. The best way to evaluate it is to call the `add()` function. This is where the optional line of code can come in handy.

```php
use CodingAvenue\Proof\Code;

$code = new Code();
$evaluator = $code->evaluator();

$result = $evaluator->evaluate('add(1,1)');
```

The result will then be:
```php
array(
 [result] => 2,
 [output] => ''
)
```
This is more useful to us since now we can validate that the `add()` function is working correctly.

# Nodes

A `Nodes` class represent the parsed php code and allows us to traverse through the node tree to find specific nodes. It is designed to traverse the node tree in a more expressive way. This class uses results from [PHP Parser](https://github.com/nikic/PHP-Parser). But its objective is to simplify how to traverse the node tree without any knowledge of what PHP Parser is.

## Traversing

The main method for traversing the `Nodes` class is the `find()` method. It accepts a `selector` string, much like a `css selector`. Here's a glimpse of how the `Nodes` class can be used:

```php
use CodingAvenue\Proof\Code;
$code = new Code();
$nodes = $code->getNodes();
```

To find all echo nodes:
```php
$echoNodes = $nodes->find('construct[name="echo"]');
```

To find all assignment nodes:
```php
$assignmentNodes = $nodes->find('operator[name="assignment"]');
```

To know how many times an `echo` statement was used:
```php
$echoNodes->count();
```

To know the string literals from the `echo` nodes:
```php
$echoNodes->text();
```

To use the find() method to return a new instance of the Nodes class so you can cascade the calls:
```php
$assignmentNodes = $nodes->find('function[name="add"]')->find('operator[name="assignment"]');
```
The code above will return all assignment operator statement inside the function add().

PHP has a lot of built-in functions, language constructs, and operators. Each of those will be discussed on its own page so it will be easier to look at them in the future. Check the sublist on the right to know more about how you can find them in the `Nodes` class.

## `Code` class `find` method

The `Code` class also has a find method, which is just a shortcut of calling `getNodes()` and the `find()` method of the `Nodes` class.

```php
$code = new Code();

$nodes = $code->find('construct[name="echo"]');
```

`$nodes` will then be a `Nodes` class with the echo nodes in it.

# Variables

## Finding Variables

```php
$name = "Jerome";

```

To find the variable node in the code above:

```php
// Assuming that $nodes is an instance of the `Nodes` class

$variable = $nodes->find('variable[name="name"]');
```

`$variable` would then be a `Nodes` class of variable `name`.

Variables can appear on almost every part of the code. A variable can used in an assignment operation or an expression. Finding variable might then give you more result than you normally expected. It would be better to first find the expression/construct/operators where you expect the variable will be used. Then, traverse the result further to find the variable node.

Function and method parameter variables are not included in the results. This is primarily because functions and methods parameters are represented as a `Param` instance of the PHP Parser and not as a `Variable`. As such, they won't be seen when we traverse for variables.

```php
function joinMe($string1, $string2)
{
   return $string1 . $string2;
}
```

In the code above, finding for variable `$string1` will only give you the variable node inside the function body. The parameters on the function won't be included on the result.

## Variable Interpolation

```php
$name = "Foo";

$greet = "Hi $name!";
```

To get the variable interpolation node in the code above:

```php
$interpolateNodes = $nodes->find('interpolation');
```

`$interpolateNodes` will be an instance of the `Nodes` class. To get the string part of the interpolation, just do `$interpolateNodes->text()`

# Data Types

## String

Using the `text()` method of the `Nodes` class is not always useful to your use case. This is because the `text()` method will join all string literals in the nodes, including string literals that are on a variable interpolation.

Suppose you are looking for the string literal `Hi There` in this php code:

```php
$name = "Foo";
$hi = "Hi There";
$greet "$hi $name";
```

Using `text()` in there will give you `FooHi There` which isn't what you are looking for. So to find the `Hi There` string literal node, do this:
```php
$stringNodes = $node->find('datatype[name="string", value="Hi There"]');
```
Note, the `value` attribute is optional.

Calling `text()` on the `$stringNodes` will give you the `Hi There` text.

In the future, we will support `regexp` on the `value` attribute to make searching more flexible.

There are four ways to specify strings in PHP: `single quoted`, `double quoted`, `heredoc syntax`, and `nowdoc syntax`. If you want to specifically find a string literal that is `single quoted`, simply add a `type="single"` attribute.

```php
$stringNodes = $node->find('datatype[name="string", value="Hi There", type="single"]');
```

`$stringNodes` will be an empty node since all of the strings are `double quoted`. To get the `double quoted` strings,pass `double` to the type attribute. `heredoc` and `nowdoc` will also be the value of the type attribute if you wish to find a string constructed using the `heredoc syntax` or `nowdoc syntax`.

## Arrays

```php
$nameArray = array('foo', 'bar', 'baz');
echo $nameArray[2]; // Display 'baz'
```
To find the array construction node in the code above:

```php
$arrayNodes = $nodes->find('datatype[name="array"]');
```
`$arrayNodes` will be a `Nodes` class instance of the `array('foo', 'bar', 'baz')` node.

To get array key/index fetching, as if in an `echo` statement:

```php
$arrayFetchNodes = $nodes->find('datatype[name="arrayfetch"]');
```

`$arrayFetchNodes` will be a `Nodes` class instance of the array fetch. You can add the attribute `variable` to `arrayfetch` to return only array fetch nodes of a particular variable. For example:
`$nodes->find('datatype[name="arrayfetch", variable="nameArray"]')`

# Operators

Check the [PHP Manual](http://php.net/manual/en/language.operators.php) page for the list of operators.

An operator search requires a `name` attribute, which is the name of the operator you are trying to find. Additional attribute may be included in some operators to refine the search.

## Assignment Operator

To find the assignment operator node:

```php
// Given the following php code

$first = "First Name";
$last = "Last Name";

// $node is an instance of the Node class
$assignment = $node->find('operator[name="assignment"]');
```

`$assignment` will be a `Nodes` instance with two nodes in it, since the assignment operator was used twice. To find an assignment operator `=` that is assigned to a particular variable name, do this:

```php
$assignment = $node->find('operator[name="assignment", variable="last"]');
```

`$assignment` will now be a `Nodes` instance with only one node. That node is `variable="last"` since it assigns an assignment operator `=` to the variable `$last`.

Since `$assignment` is also an instance of the `Nodes` class, you can call the `text()` method to get the literal string of the assignment. In this case the returned value is the string `Last Name`.

## Increment Operators

```php
$var = 1;
$var++;
++$var;
```

To find an increment operator node in the code above:
```php
$increment = $node->find('operator[name="increment"]');
```
`$increment` will be a `Nodes` instance with two nodes in it, since the increment operator was used twice. To find a `post` or `pre` increment operator, pass a `type` attribute in the selector.

```php
$node->find('operator[name="increment", type="post"]');
```

The code above will return the `post` increment node. Pass `pre` on the `type` value to get the `pre` increment node.

You can filter the result further by specifying the variable name that was used in the operator, as shown here: `$node->find('operator[name="increment", variable="var"]')`. This will return only increment operator used in the variable `var`.

## Decrement Operators

Finding the `decrement` operator is the same with the `increment` operator. Simply change the operator name from `increment` to `decrement`. 

## String Operators

### Concatenation operator

```php
$name = "Foo " . "Bar";
```
To find string concatenation nodes in the code above, do:

```php
$concatNode = $nodes->find('operator[name="concat"]');
```
`$nodes` is an instance of the `Nodes` class. `$concatNode` will be a `Nodes` instance of the concatenation of the strings `Foo ` and `Bar`. Calling the `text()` method on the `$concatNode` will result to the string `Foo Bar`.

### Assignment Concatenation operator

```php
$name = "Foo ";
$name .= "bar";
```
To find assignment concatenation operator in the code above, do:
```php
$assignConcat = $nodes->find('operator[name="assign-concat"]');
```
`$nodes` is an instance of the `Nodes` class.`$assignConcat` will be a `Nodes` instance of the assignment concatenation operator. You can also find an assignment concatenation operator that is assigned to a particular variable. You only need to add an additional attribute on the operator selector.

```php
$foo = "foo";
$bar = "bar";
$foo .= " baz";
$bar .= " baz";
```

In the code above, you can find an assignment concatenation operator assigned to a particular variable by doing this:

```php
$assignConcat = $nodes->find('operator[name="assign-concat", variable="bar"]');
```

`$assignConcat` will then be a `Nodes` instance of the assignment concatenation operator that uses the variable `$bar`.

## Arithmetic Operators

To find an arithmetic operator nodes just add the operator name ti the `name` attribute.

```php
$add = 1 + 1;
$sub = 2 - 1;
$mul = 1 * 3;
$div = 2 / 2;
$mod = 4 % 2;
$pow = 4 ** 2;
```

To find the addition operator `+` in the code above, do:
```php
$nodes->find('operator[name="addition"]');
```
You can do the same for other operators.

To find the subtraction operator `-`:
```php
$nodes->find('operator[name="subtraction"]');
```
To find the multiplication operator `*`:
```php
$nodes->find('operator[name="multiplication"]');
```
To find the division operator `/`:
```php
$nodes->find('operator[name="division"]');
```
To find the modulo operator `%`:
```php
$nodes->find('operator[name="modulo"]');
```
To find the exponential operator `**`:
```php
$nodes->find('operator[name="pow"]');
```

## Comparison Operators

Like searching for arithmetic operators, to find a comparison operator node, just add the operator name to the `name` attribute.

```php
$less = $a < $b;
$greater = $a > $b;
$lessEqual = $a <= $b;
$greaterEqual = $a >= $b;
$equal = $a == $b;
$identical = $a === $b;
$notEqual = $ != $b;
$notEqual = $a <> $b;
$notIdentical = $a !== $b;
$spaceship = $a <=> $b;
```

To find the less than comparison operator `<`:
```php
$nodes->find('operator[name="less"]');
```

To find the greater than comparison operator `>`:
```php
$nodes->find('operator[name="greater"]');
```

To find the less than or equal comparison operator `<=`:
```php
$nodes->find('operator[name="less-equal"]');
```

To find the greater than or equal comparison operator `>=`:
```php
$nodes->find('operator[name="greater-equal"]');
```

To find the equal comparison operator `==`:
```php
$nodes->find('operator[name="equal"]');
```

To find the identical comparison operator `===`:
```php
$nodes->find('operator[name="identical"]');
```

To find the not equal comparison operator `<>`:
```php
$nodes->find('operator[name="not-equal"]');
```

To find the not identical comparison operator `!==`:
```php
$nodes->find('operator[name="not-identical"]');
```

To find the spaceship comparison operator `<=>`:
```php
$nodes->find('operator[name="spaceship"]');
```
# Nodes

A `Nodes` class represent the parsed php code and allows us to traverse through the node tree to find specific nodes. It is designed to traverse the node tree in a more expressive way. This class uses results from [PHP Parser](https://github.com/nikic/PHP-Parser). But its objective is to simplify how to traverse the node tree without any knowledge of what PHP Parser is.

## Traversing

The main method for traversing the `Nodes` class is the `find()` method. It accepts a `selector` string, much like a `css selector`. Here's a glimpse of how the `Nodes` class can be used:

```php
use CodingAvenue\Proof\Code;

$code = new Code();
$nodes = $code->getNodes();

// Finding all echo nodes.
$echoNodes = $nodes->find('construct[name="echo"]');

// Finding all assignment nodes;
$assignmentNodes = $nodes->find('operator[name="assignment"]');

// Want to know how many times the echo statement was used?
$echoNodes->count();

// Want to know the string literals from the echo nodes?
$echoNodes->text();

// The find() method returns a new instance of the Nodes class so you can cascade the calls
$assignmentNodes = $nodes->find('function[name="add"]')->find('operator[name="assignment"]');
// Will return all assignment operator statement inside the function add().
```

PHP has a lot of built-in functions, language constructs, and operators. Each of those will be discussed on its own page so it will be easier to look at them in the future. Check the sublist on the right to know more about how you can find them in the `Nodes` class.

## `Code` class `find` method

The `Code` class also has a find method, which is just a shortcut of calling `getNodes()` and the `find()` method of the `Nodes` class.

```php
$code = new Code();

$nodes = $code->find('construct[name="echo"]');
```

`$nodes` will then be a `Nodes` class with the echo nodes in it.
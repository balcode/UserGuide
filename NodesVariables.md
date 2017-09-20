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
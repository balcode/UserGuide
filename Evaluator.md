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
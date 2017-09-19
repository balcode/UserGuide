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

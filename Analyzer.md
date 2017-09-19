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
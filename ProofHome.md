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

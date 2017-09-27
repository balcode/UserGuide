## Introduction

This style guide is called **Writer's Block**. The objectives of **Writer's Block** are:
- to make content as consistent as possible
- to make writing questions and answers efficient
- to save time and energy deciding what words to use

## Question construction

### Question form

Whenever possible, write questions instead of incomplete statements.

*What does the `echo` function do on line 3?*
</br>instead of</br>
*On line 3, the `echo` function:*

### Organizing a question

If a learner needs to locate a specific line of code, indicate its location first so that they can see it in the code evaluator.  

*On line 12, add an equal sign `=` after the greater than `>` in the conditional expression. What is the value assigned to `$salary`?*
</br>instead of</br>
*Add an equal sign `=` after the greater than `>` in the conditional expression on line 12. What is the value assigned to `$salary`?*

### Statement form
When it is unavoidable to write in statement form, end the statement with a colon `:` to suggest that the choices are a continuation to the incomplete statement. 

### Problem construction

There are many ways to write a problem. CodeStop recommends to do the following:

- The first sentence describes what the code should do.
</br>
*Write a program that interpolates multiple variables in a string.*

- Describe how the program should be written, starting from the first line of code.

- The last line indicates what the learner should see if they write the code correctly.

Problem:

<code>
Write a program that interpolates multiple variables in a string. Create the variables `$name` and `$address`, and assign the strings `Davidson` and `San Francisco` respectively. Use `echo` to display the string `$name is working in $address.`, wherein the variables are replaced with their corresponding values.
</code>

Code:

    $name = "Davidson";
    $address = "San Francisco";
    echo "$name is working in $address.";


### Common constructions for single choice questions

*Which statement [condition]?*

*Which statement best describes the error on line 3?*

*Which statement correctly describes the error on line 3?*

### Multiple selections

These are the common constructions for questions that require multiple selections

*Which statements [condition]?*
*Which statements correctly describe the error on line 3?*

### Verbs

This is a good cheat sheet if you are lazy or aiming at consistency. These are suggestions and not rules. Tweaking, variations, and some creativity are welcomed. But your compliance is encouraged.

**Variables**

Write *replace its value* to mean that a variable is interpolated with its value. 

**Strings** 

Write *display* to mean that a variable is interpolated in a string. For example: *The the string should display its value*.

**Error message** 

Write *produces an error* to mean that a code generates an error message.

**Program**

Write *execute* to mean that you intend a user to run a program.

For example: *Execute the program. What is its output?***

Write ***run*** in problem statements.


### Capitalization

#### PHP
Write in all caps when referring to the name of the programming language
Write in small caps when referring to code blocks of PHP

#### Boolean

Lower case for data type
Capitalized for classes

#### Choices 

The first word of each choice is capitalized. This also appies to single-word choices.

### Punctuation

#### Backticks and periods 
Put a period after a complete sentence that is enclosed in backticks. 
The program displays `Hello, World.`.

#### Oxford comma

For example: ***Today, you’ll learn about variables, interpolation, and strings.***
			 ***You can study PHP, Java, Python, or Ruby.***
Introductory phrases
	Set off introductory words and phrases with a comma
	Next, create a variable named $studentGrade.
#### If vs. When


Verbs/Nouns + Prepositions
Enclosed = in
	The string is not enclosed in quotation marks. 
Lines = on
	On which line does the error occur?
Based = on
	Based on the statement...
Difference = between
	Calculate the difference between the integers 45 and 15. 
Interpolate = in
	Write a program that interpolates the variable in a string.
Separated = with 
 	Separate with a space


Line spaces
From one number to another = 2 lines
From problem statement to code block = 1 line ```php
<?php
From end of code block to annotation of question type = no space



Word order for:
compound nouns
terms with multiple words
subtraction operator `-`
subtraction `-` and addition `+`
terms that contain a symbol
open curly brace `{`
Multiplication operator  `*`
the `define()` function




Things to look out for when editing:

Structure
Spelling
Grammar 
Punctuation
Tenses
Vocabulary
Clarity
Readability
Characterization
Descriptions
Tone
Contradictions
Inconsistencies
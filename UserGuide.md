 ## Introduction

The goal of this guide is to make the content of question documents consistent. The content of CodeStop is created for individuals 12 years and older, with no background in programming. 

### The Four Phases of Creating a Lesson
The steps in creating a lesson: 
1. Write objectives for the lesson.
2. Gather facts about the lesson. 
3. Create content and questions. 
4. Create answers and tests files for type CR questions.

## Writing Objectives

Begin by writing objectives in order to limit the scope of the lesson and identify the skills that you want to learners to acquire. The objectives document will not be accessed by learners. It is a reference for you, the course creator, and the reviewers.

To write objectives, follow these steps:

1. Annotate the title of the lesson that you are writing objectives for with three number signs `###`. In the markdown format, three number signs `###` will render at text in heading three format. Enclose the name of the lesson in backticks <code>`</code>.

![Writing an objective's title](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/title-lesson-objectives.png)
**Figure 1.** Use the heading 3 annotation for the title of the objective document. Enclose the name of the lesson in backticks <code>`</code>.

2. Enumerate the skills that a learner must acquire by the end of the lesson.
3. Use the <code>verb</code> **+** <code>knowledge / topic</code> format:
        </br>
        <code>1. Perform variable interpolation.</code> 
        </br>
        <code>2. Identify the output of an echo statement.</code>
        </br>
4. Adhere to the S-M-A-R-T guideline of writing objectives: specific, measurable, attainable, and time-bounded.
5. Avoid non-specific words such as <code>learn</code>, <code>know</code>, or <code>understand</code>.
6. Save the objective document in the following format:
        </br>
        a. name of the lesson, with every word capitalized
        </br>
        b. the word <code>objective</code>
        </br>
        c. the markdown <code>.md</code> file extension

![Writing an objective](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/objectives.png)
**Figure 2.** When saving an objective document, capitalize every word including conjunctions. Do not capitalize the words <code>objectives</code> and <code>md</code>.

## Gathering Facts

The facts document serve as your reference when writing questions. The facts document will not be accessed by learners. It is a reference for you, the course creator, and the reviewers. 

To write a facts document, follow these steps:

1. Annotate the title of the lesson with three number signs `###`. In the markdown format, three number signs `###` will render at text in heading three format. Enclose the name of the lesson in backticks <code>`</code>. 
2. Summarize the relevant facts that you will be included in the lesson.
3. Save the facts document in the following format:
        </br>
        a. name of the lesson, with every word capitalized
        </br>
        b. the word <code>facts</code>
        </br>
        c. the markdown <code>.md</code> file extension 
![Writing the facts document](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/facts-lesson-list.png)
**Figure 3.** Write the facts that will be included in the lesson.


## The Question Document

### Naming convention for a question document

When saving a question document file, capitalize every word of the filename including conjunctions. The filename is composed of the following:

1.	the name of the lesson
2.	the suffix ".q"
3.	the file extension ".md"

![How to name a question document](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/guide-sc-naming-conventions.png)
**Figure 4.** When naming a question document, capitalize every word including conjunctions.

### Annotations

Annotations denote how a group of text will be rendered by the reader. The annotation for headers are as follows:
#### One number sign #

Use one number sign # to denote the title of the lesson.

#### Three number signs ###

Use three number signs ### to denote a specific part of a lesson.

#### Three slash signs /// 	

Use three slash signs /// to denote the type of a question or render a code editor. 

![Three slash signs](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/guide-slash-types.png)

**Figure 5.** In the first instance, the slashes indicate that what follows is a read-only **REPL**. 
              In the second instance, the slashes denote the type of question.

To know more about the different types of question, read **Types of Questions** below.

#### Three colons :::

Three colons `:::` indicate the scope of a set of code and questions.

Use three colons to indicate that:

- what follows is a code block
- all the codes and questions within the two sets of three colons `:::` go together

![First set of three colons](https://raw.githubusercontent.com/balcode/UserGuide/user-guide-review/user-guide-screens/three-colons-1.png)
![Second set of three colons](https://raw.githubusercontent.com/balcode/UserGuide/user-guide-review/user-guide-screens/three-colons-2.png)
**Figure n.** The two sets of three colons `:::` indicate that the code and set of questions that start on `line 8` and end on `line 125` go together.

#### Three plus signs

Each question document has four parts:

1. Sample Code Analysis
2. Knowledge Assessment
3. Finding and Fixing Errors
4. Practice

Use two sets of three plus signs `+++` to indicate that the text they enclose are a specific part of the lesson.

![First three plus signs](https://raw.githubusercontent.com/balcode/UserGuide/user-guide-review/user-guide-screens/three-plus-signs.PNG)

**Figure n.** The three plus signs `+++` indicate that the text enclosed within are specific part of a lesson. The three plus signs `+++` indicate the beginning of `Part 1 Sample Code Analysis`. 

![Second three plus signs](https://raw.githubusercontent.com/balcode/UserGuide/user-guide-review/user-guide-screens/three-plus-signs-2.png)
**Figure n.** The first set of three plus signs `+++` indicate the end of `Part 1 Sample Code Analysis.` The second set of three plus signs `+++` indicate the beginning of `Part 2 Knowledge Assessment`. 

### How to Annotate an Answer Key

Before each question, create a two-part annotation that indicates:
* the type of question; and
* the correct answer. 

This is called the answer key. The answer key allows the reader to locate the correct answer. 

To annotate an answer, follow these steps:
1.	Use three slash signs `///` to denote that the text that follows indicates the type of question and the answer key.
2.	Write **type=**`type of question`, followed by a comma `,`. 
    </br>*See **Types of Questions** below to know how to annotate for different types of questions.*
3.	Then, write **answer=**[`answerwithinthebrackets`].
4.	Within the square brackets, indicate the correct answer. For single selection and multiple selection, the correct answer is indicated by a number: **1** being the first answer in the selection, **2** being the second, and so forth.

For code response answers, indicate the path of the file that contains the correct answer.

![Include the path for code response](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/guide-sc-CR-type.PNG) 
**Figure 6.** For **Code Response** questions, indicate the path of the file that contains the correct answer.

### Types of Questions

There are five annotations that indicate the type of question. 

**MS**. **MS** stands for multiple selection. This type of question requires two or more selections. Use this annotation for a multiple selection question: **/// type=MS**.

**SS**. **SS** stands for single selection. This type of question requires one selection. Use this annotation for a single selection question: **/// type=SS**. 	

**TI**. **TI** stands for text input. This type of question requires a learner to enter text for the answer. Use this annotation for a question that requires text input: **/// type=TI**.

**CR**. **CR** stands for code response. This type of question requires a learner to enter a line or block of code to answer a question. Use this annotation for a question that requires code response: **/// type=CR**.

A learner should run a CR to see its result.

**REPL**. **REPL** stands for read-eval-print loop. This annotation indicates that what follows the annotation is a block of code. The code block can be read-only or editable. Use this annotation for a read-only REPL: **/// type=REPL, readonly=true**. For an editable REPL, use this annotation: **/// type=REPL**. 
//This requires writers to prepare answers and tests files for proofs.
    

A learner should run an REPL to see its result.

![Indicate the question type and correct answer](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/guide-sc-question-annotation.png) 

**Figure 7.** This question annotation indicates that question 1 requires a single answer and the correct answer is the first option.

### How to annotate a question 

All question documents are formatted using a markup language called **Markdown**. Follow these conventions when annotating the question documents: 

1. Put a hyphen **-** before each choice. The CodeStop reader interprets a hyphen **-** as a radio button for questions that require a single selection; and as a checkbox for questions that require multiple selection.

![Put a hyphen before each selection](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/guide-sc-question-hyphen.png)

![Hyphens as radio buttons](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/guide-sc-radio-button.png)

**Figure 8.** A hyphen **-** is rendered as a radio button. 

2.	Enclose all of the following in backticks <code>`</code> whenever they are contained in a question or answer:

*	Names of variables
*	Values of variables
*	Blocks of code
*	Code tags
*	Operators
*	Names of functions
*	Keywords

![Enclose certain words in backticks](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/guide-sc-variable-ticks.png) 

**Figure 9.** The values of variables, names of variables, and code tags are enclosed in backticks <code>`</code> when part of a question or an answer.


### How to annotate a code block

Annotate blocks of code so that they are contained in the code evaluator.

To annotate a code block, follow these steps:
1. Write three backticks followed by the name of the programming language. For example: **```php**.
2. Enter the code block.
3. Write three backticks **```** to close the code block.

![Code blocks are enclosed in backticks](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/guide-sc-code-annotation.png)

**Figure 10.** Enclose code blocks in three backticks.  

![How code blocks are rendered](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/guide-sc-code-rendered.png)

**Figure 11.** Annotated code blocks are contained in the code evaluator.  	

### Title of the lesson

Write the title on the first line of the question document. To annotate the title, follow these steps:
1.	Put a number sign **#** to denote that what follows is the title of the lesson. 
2.	Write the title of the lesson using headline capitalization. 
3.	Leave the next line blank.

![](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/first-line-title.png) 

**Figure 12.** On the first line of the document, write the title of the lesson using headline style capitalization.

### Sample Code Analysis

The first among four types of questions is called **Sample Code Analysis**. The goal is to make a learner try a code and infer its function. Below are the basic guidelines for Sample Code Analysis:
1.	Write the heading in this format: **### Part 1. Sample Code Analysis**. 
2.	Write the instruction. For example: <code>Refer to the code below to answer questions 1 to 8</code>. 
3.	Present a working code that is relevant to the lesson.
4.	Write the questions that pertain to the code.

In **Sample Code Analysis**, you may use more than one code block.

### Knowledge Assessment

The second part of a question document is called **Knowledge Assessment**. In this section, learners answer questions to test what they have learned from **Sample Code Analysis**. Below are the basic guidelines for **Knowledge Assessment**:
1.	Write the heading in this format: **### Part 2. Knowledge Assessment**.
2.	Write the questions.

### Finding and Fixing Errors

In **Finding and Fixing Errors**, learners test their ability to identify the cause of an error and fix it. Below are the basic guidelines for **Finding and Fixing Errors**: 
1.	Write the heading in this format: **### Part 3. Finding and Fixing Errors**. 
2.	Present a code that has one or more errors.
3.	Write questions that relate to why a code is not working or what they can do to correct an erroneous code.

### Practice

In **Practice**, learners test what they have learned in the past three sections by writing a code in response to a problem. To write a practice question, follow these steps:

1.	Write the heading in this format: **### Part 4. Practice**. 
2.	Before the problem statement, create an annotation for the type of question and path of the answer.
3.	In the first sentence, state the goal of the problem. 
4.	Write a detailed explanation of the problem that needs to be solved. 
5.	In the last sentence, state what should happen if the program is written correctly.
6.	Create the annotation for the code evaluator.

![](https://raw.githubusercontent.com/balcode/UserGuide/22e7d3c59f38ad41e00aa60f653fc52d67768a91/user-guide-screens/guide-sc-practice.png) 

**Figure 13.** Create an annotation for the question type and answer. Write the problem statement. Lastly, create an annotation for the code evaluator.

## Creating Answers and Test Files

A code, proof, and test files are necessary to verify the answers of code response questions.

### How to Write Test Files

For now, the guidelines on how to write those files are ideally used for PHP tests. For detailed instructions, view the [Proof Library](https://github.com/CodingAvenue/ca-school-proof-library/wiki "Open proof library on GitHub") on Github.

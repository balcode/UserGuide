 ## Introduction

The goal of this guide is to make the content of question documents consistent. The content of CodeStop is created for individuals 12 years and older, with no background in programming. 

### The Four Phases of Creating a Lesson
The steps in creating a lesson: 
1. Write goals/objectives for the lesson.
2. Gather facts about the lesson. 
3. Create content/questions based on facts. 
4. Create answers and tests files for type CR questions.

## Writing Objective

Begin by writing objectives in order to limit the scope of the lesson and identify the skills that you want to learners to acquire. 

To write objectives, follow these steps:

1. Enumerate the skills that a learner must acquire by the end of the lesson.
2. Use the <code>verb</code> **+** <code>knowledge / topic</code> format:
        </br>
        <code>1. Perform variable interpolation.</code> 
        </br>
        <code>2. Identify the output of an echo statement.</code>
3. Adhere to the S-M-A-R-T guideline of writing objectives: specific, measurable, attainable, and time-bounded.
4. Avoid non-specific words such as <code>learn</code>, <code>know</code>, or <code>understand</code>.
5. Save the objective document in the following format:
        </br>
        a. name of the lesson, with every word capitalized
        </br>
        b. the word <code>objective</code>
        </br>
        c. the markdown <code>.md</code> file extension

![Writing an objective](https://lh5.googleusercontent.com/OKl_5vJvUNpci8AI2YJ38RvcPBpZKtdnKNxKusfseX-oHhc8KcHPcPL4NZVR7UddwMrGMi8jJ_4vHxQ=w1919-h950-rw)
**Figure .** When saving an objective document, capitalize every word including conjunctions. Do not capitalize <code>objectives</code> and <code>md</code>.

## Gathering Facts

The facts document serve as your reference when writing questions.

n. Save the facts document in the following format:
        </br>
        a. name of the lesson, with every word capitalized
        </br>
        b. the word <code>facts</code>
        </br>
        c. the markdown <code>.md</code> file extension 


## 3. The Question Document

### Naming convention for a question document

When saving a question document file, capitalize every word of the filename including conjunctions. The filename is composed of the following:

1.	the name of the lesson
2.	the suffix ".q"
3.	the file extension ".md"

![How to name a question document](https://lh4.googleusercontent.com/XmuBgnM4mhPd7zYlS0Dx_O9wTX0bkCBfk2n7jURwKOMn9HIXSfN_zsqXNY0cqzQ6UDAJWSPXyJwv1pE=w1920-h950-rw)

&nbsp;&nbsp;&nbsp;**Figure 1.** When naming a question document, capitalize every word including conjunctions.

### Annotations

Annotations denote how a group of text will be rendered by the reader. The annotation for headers are as follows:
#### One number sign #

Use one number sign # to denote the title of the lesson.

#### Three number signs ###

Use three number signs ### to denote a specific part of a lesson.

#### Three slash signs /// 	

Use three slash signs /// to denote the type of a question or render a code editor. 

![Three slash signs](https://lh6.googleusercontent.com/4E0N5-oE5VB3xFmbi3yjKyEvTiMmYWtt2PE75ainRKRsledtUuS1cXBDntVRWyrCpgyqK8myOk49On0=w1920-h950)

**Figure 2.** In the first instance, the slashes render a code editor. 
              In the second instance, the slashes denote the type of question.

### How to Annotate an Answer Key

Before each question, create a two-part annotation that indicates:
* the type of question; and
* the correct answer. 

This is called the answer key. The answer key allows the reader to locate the correct answer. 

To annotate an answer, follow these steps:
1.	Use three slash signs **///** to denote that the text that follows indicates the type of question and the answer key.
2.	Write **type=**`type of question`, followed by a comma **,**. 
    </br>*See **Types of Questions** below to know how to annotate for different types of questions.*
3.	Then, write **answer=**[`answerwithinthebrackets`].
4.	Within the square brackets, indicate the correct answer. For single selection and multiple selection, the correct answer is indicated by a number: **1** being the first answer in the selection, **2** being the second, and so forth.

For code response answers, indicate the path of the file that contains the correct answer.

![Include the path for coder response](https://lh4.googleusercontent.com/tEOJrxGXeXL_-IjQvorqpWW2PsxispGYln3UFVOYpm7wIMbXnibXZekbaaAWQ3cGL_ng25uNJTTJQrI=w1920-h950-rw) 
**Figure 3.** For Code Response questions, indicate the path of the file that contains the correct answer.

### Types of Questions

There are five annotations that indicate the type of question. 

**MS**. **MS** stands for multiple selection. This type of question requires two or more selections. Use this annotation for a multiple selection question: **///type=MS**.

**SS**. **SS** stands for single selection. This type of question requires one selection. Use this annotation for a single selection question: **///type=SS**. 	

**TI**. **TI** stands for text input. This type of question requires a learner to enter text for the answer. Use this annotation for a question that requires text input: **///type=TI**.

**CR**. **CR** stands for code response. This type of question requires a learner to enter a line or block of code to answer a question. Use this annotation for a question that requires code response: **///type=CR**.

A learner should run a CR to see its result.

**REPL**. **REPL** stands for read-eval-print loop. This annotation indicates that what follows the annotation is a block of code. The code block can be read-only or editable. Use this annotation for a read-only REPL: **///type=REPL, readonly=true**. For an editable REPL, use this annotation: **///type=REPL**. 
//This requires writers to prepare answers and tests files for proofs.
    

A learner should run an REPL to see its result.

![](https://lh5.googleusercontent.com/uKAr0PbAUCaeq_bGU2ueSz0D6-r41XYcwbIdngE21XRJZFnejMZgbxi0q506pkTPwQAwlED6ai-a3iU=w1920-h950) 
**Figure 4**. This question annotation indicates that question 1 requires a single answer and the correct answer is the first option.

### How to annotate a question 

All question documents are formatted using a markup language called **Markdown**. Follow these conventions when annotating the question documents: 

1.	Put a hyphen **-** before each choice. The CodeStop reader interprets a hyphen **-** as a radio button for questions that require a single selection; and as a checkbox for questions that require multiple selection.

![](https://lh6.googleusercontent.com/lrPyy9KIqlZT7BdFWDySkp8iStKQ1aHhEnwK8cPyTo_TzxMJN8FLFqq8Ghy_Kry8AoxOXsJ2w06Gvv4=w1920-h950)

![](https://lh6.googleusercontent.com/YnYeAc0cQik9sZey2WS71E9LN_V3cmUfYcRYyfAJZg8X-Iowi-invbL9SGf4LKQ1gvOfJ7Bat9e_Yio=w1920-h950)

**Figure 5**. A hyphen **-** is rendered as a radio button. 

2.	Enclose all of the following in backticks **`** whenever they are contained in a question or answer:

*	Names of variables
*	Values of variables
*	Blocks of code
*	Code tags
*	Operators
*	Names of functions
*	Keywords

![](https://lh5.googleusercontent.com/_VNe9sFqAOFfbZUd7greLEVnfdQxp8wsndC-2KuJhh3xwRPscoldAgB_aztZq3FCxVqs5WIsx4rNHAI=w1920-h950) 

**Figure 6**. The values of variables, names of variables, and code tags are enclosed in backticks **`** when part of a question or an answer.


### How to annotate a code block

Annotate blocks of code so that they are contained in the code evaluator.

To annotate a code block, follow these steps:
1. Write three back ticks followed by the name of the programming language. For example: **```php**.
2. Enter the code block.
3. Write three back ticks **```** to close the code block.

![](https://lh4.googleusercontent.com/pR0d89FJylVqe0LOkgjhjKHPdWHfWl1bRM3i-vp29Hb74X64XZKvvik9HR_umNN0v1-dZ2TPSPwD2zo=w1920-h950)

**Figure 7**. Enclose code blocks in three backticks.  

![](https://lh3.googleusercontent.com/SRNv_009GVvobc18B21ubWxSKXpSWgGoaq6yWNXy5n_1I1-H6T-MGTVoVGRqQ57Js8CAT1-Qa9pTtUc=w1920-h950)

**Figure 8**. Annotated code blocks are contained in the code evaluator.  	

### Title of the lesson

Write the title on the first line of the question document. To annotate the tile, follow these steps:
1.	Put a number sign **#** to denote that what follows is the title of the lesson. 
2.	Write the title of the lesson using headline capitalization. 
3.	Leave the next line blank.

![](https://lh3.googleusercontent.com/qB8efw9XLNNesC-dnseuuInaSHfh0eyZKDMae4xtVJZnROA4I2NxkucMQ9tsmNAoKNxyrfDGcRaQEng=w1920-h950) 

**Figure 9**. On the first line of the document, write the title of the lesson using headline style capitalization.

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

![](https://lh4.googleusercontent.com/5n59TM2Sj4RUJ95YVr9foCABN6lXDZRfdws46pUupCVemXDaDfPFXEM1aTTRWTe6ee3qMYEDNH-OzRI=w1919-h950-rw) 

**Figure 10.** Create an annotation for the question type and answer. Write the problem statement. Lastly, create an annotation for the code evaluator.

 

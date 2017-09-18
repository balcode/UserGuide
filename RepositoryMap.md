# Repositories on Github

This section of `Content Creation Guide` explains how to organize directories, subdirectories, and files. For specific information on how to write each file, refer to `UserGuide`.

On Github, the PHP course has three repositories:
    - ca-school-php-introduction-course
    - ca-school-php-intermediate-level-course

# Outline of Repositories and Directories

This is the outline of directories and subdirectories for each repository. 

```bash
├── Repository
└── answers directory
    ├── subdirectories for each lesson
    │   ├── Test files
    ├── Strings.md
└── content directory
    ├── Subdirectories for each lesson
    │   ├── facts.md
        ├── objectives.md
        ├── q.md
└── tests directory
    ├── Subdirectories for each lesson
    │   ├── test files 
└── vendor directory
```

# Directories

Just like most Github repositories, each repository of CodeStop PHP courses have directories and subdirectories.

We'll use the repository `ca-school-php-introduction-course` as the example to illustrate the outline above. The repository contains the following directories:

- answers
- content
- tests
- vendor

## Answers

The directory `answers` contains subdirectories. There is a subdirectory for each lesson. In this example, we'll use two subdirectories to illustrate the outline above. The two subdirectories are `AssigningAndDisplayingVariables` and `BooleanTypeWithConditional`.

Each subdirectory contains answer files. Answer files validate whether the proofs are correct. These files are organized as follows:

```bash
├── ca-school-php-introduction-course
└── answers 
    ├── AssigningAndDisplayingVariables
        ├── AssignAmericanToCitizenshipTest.php
        ├── AssignWisconsinToAddressTest.php
        ├── CorrectCodeCurieTest.php
    ├── BooleanTypeWithConditional
        ├── AssignTestResultRemarkTest.php
        ├── AssignTrueToVariablePassedQuizTest.php
        ├── MissingAssignmentOperatorTest.php
```

## Content

In the directory `content`, there is one subdirectory for each lesson. Each subdirectory contains three files:

- `facts.md`
- `objectives.md`
- `.q.md`

`facts.md` contains information on what the lesson is about. 

`objectives.md` contains information on what learners should be able to learn by the end of the course. Both `facts.md` and `objectives.md` are not accessible by learners. They serve as the guide of course creators for writing lessons.

`q.md` contains questions, selections, and various annotations. The content of `q.md` is what learners see when they take lessons.

```bash
├── ca-school-php-introduction-course
└── content 
    ├── AssigningAndDisplayingVariables
        ├── AssigningAndDisplayingVariables.facts.md
        ├── AssigningAndDisplayingVariables.objectives.md
        ├── AssigningAndDisplayingVariables.q.md
    ├── BooleanTypeWithConditional
        ├── BooleanTypeWithConditional.facts.md
        ├── BooleanTypeWithConditional.objectives.md
        ├── BooleanTypeWithConditional.q.md
```

## Tests

In the directory `tests`, there is one subdirectory for each lesson. Inside each subdirectory are test files, which verify whether the answer of the learners are correct. Test files are necessary for questions that require a code response.

```bash
├── ca-school-php-introduction-course
└── tests 
    ├── AssigningAndDisplayingVariables
        ├── AssignAmericanToCitizenshipTest.php
        ├── AssignWisconsinToAddressTest.php
        ├── CorrectCodeCurieTest.php
     ├── BooleanTypeWithConditional
        ├── AssignTestResultRemarkTest.php
        ├── AssignTrueToVariablePassedQuizTest.php
        ├── MissingAssignmentOperatorTest.php
```

## Vendor

Inside the `vendor` directory are classes used by the proof class. Course creators do not need to create this directory or the files it contains. 

The `vendor` directory and its files are automatically created when you create a new course repository. To know how to create a new repo, see `How to create a new course repository`.



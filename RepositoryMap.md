# Repositories on Github

On Github, the PHP course has three repositories:
    - ca-school-php-introduction-course
    - ca-school-php-intermediate-level-course

# Outline of Repositories and Directories

This is the outline of directories and subdirectories for each repository. 

```bash
├── Repository
└── `answers` directory
    ├── subdirectories for each lesson
    │   ├── Test files
    ├── Strings.md
└── `content` directory
    ├── Subdirectories for each lesson
    │   ├── `facts`.md
        ├── `objectives`.md
        ├── `q`.md
└── `tests` directory
    ├── Subdirectories for each lesson
    │   ├── test files 
└── `vendor` directory
```

# Directories

Just like most Github repositories, each repository of CodeStop PHP courses have directories and subdirectories.

We'll use the repository `ca-school-php-introduction-course` as the example to illustrate the outline above. The repository contains the following directories:

- answers
- content
- tests
- vendor

## Answers

The directory `answers` contains subdirectories. Each subdirectory is named after a lesson. In this example, we'll use two subdirectories to illustrate the outline above. The two subdirectories are `AssigningAndDisplayingVariables` and `BooleanTypeWithConditional`.

Each subdirectory contains test files. Test files validate the answer of the learners. They are organized as follows:

```bash
├── ca-school-php-introduction-course
└── `answers` 
    ├── `AssigningAndDisplayingVariables`
        ├── `AssignAmericanToCitizenshipTest.php`
        ├── `AssignWisconsinToAddressTest.php`
        ├── `CorrectCodeCurieTest.php`
    ├── `BooleanTypeWithConditional`
        ├── `AssignTestResultRemarkTest.php`
        ├── `AssignTrueToVariablePassedQuizTest.php`
        ├── `MissingAssignmentOperatorTest.php`
```

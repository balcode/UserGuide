In this document:
- Outline of Repositories and Directories
- Directories
- Answers
- Content
- Tests
- Vendor
- How to Create A Repository
- How to Clone a Repository
- Repositories on Github
- How to Zip a Course
- Linux
- Windows
- Mac OS
- The Open Source Contributor Mindset

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
## Directories

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

The `vendor` directory and its files are automatically generated when you create a new course repository. To know how to create a new repo, see `How to create a new course repository`.

## How to Create A Repository 

Create a new repository on Github whenever you create a new course. 

Below are the steps to create a new course repository on GitHub.

 1. On the upper-right corner of GitHub, click the `plus sign` **`+`** to create a new course repository. 

![Click the add button.](https://raw.githubusercontent.com/balcode/UserGuide/user-guide-review/user-guide-screens/create-new-repo.png)In the upper-right corner, click the plus sign to to create a new repository. 
 
 2. On the `Create a new repository` page, enter the name of your new repository. All names course repositories must be in lowercase with each word separated by a dash. For example, `ca-school-javascript-introduction`.

## How to Clone a Repository

After creating a repository on Github, you will need to create a local directory. Your local directory is where you will put all the files you need in the process of creating a course. To clone a Github repository, do this:

1. Copy the SSH link to the repository page that you want to clone.
![Copy the SSH link](https://raw.githubusercontent.com/balcode/UserGuide/user-guide-review/user-guide-screens/create-new-repo-ssh.png)
2. On your local computer, open Git Bash and type `cd "Local directory"` to switch to the directory where you want to store your files.
3. Type `git clone` `"SSH link to repository"`

![Run this command to clone](https://raw.githubusercontent.com/balcode/UserGuide/user-guide-review/user-guide-screens/create-new-repo-git-dir.png)
4. Run the following commands: 
 ```php
  git pull
  git checkout -b "name-of-lesson-branch"
 ```
`git pull` integrates a remote repository to your current branch.
`git checkout -b name-of-lesson-branch` creates a new branch. Note that the name of the branch only contains lower case letter, with each word separated by a hyphen `-`.
5. From an existing Code Stop repository, copy the following folders/files to the cloned repository:
  ```php
    SUMMARY.md
    content
    tests
    answers
    course.json
    run.sh
    proof.json
    code
    phpunit.xml
    composer.json
 ```
 6. Run `composer install`.
 7. Copy the lesson content you created to the respective folders in the cloned repository.
 8. Run:
 ```php
    git add .
    git commit -m "Your commit message here"
    git push origin name-of-lesson-branch
 ```
 To view more commands, open the [Github cheatsheet](https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf). 
 
# Repositories on Github

This section of `Content Creation Guide` explains how to organize directories, subdirectories, and files. For specific information on how to write each file, refer to `UserGuide`.

On Github, the PHP course has three repositories:
    - ca-school-php-introduction-course
    - ca-school-php-intermediate-level-course

# How to Zip a Course

## Linux

Before upload a course to a platform, the course files must be zipped. To zip course files in a Linux environment, follow these steps:

1. Open a terminal in the directory where the course files are located.
2. Run this command: `zip -r "the name of your new zip file"`

## Windows

## Mac OS

# The Open Source Contributor Mindset

The idea of assigning each of us our own repo to contribute to is to avoid the one-man-mind decision. But still it doesn't mean it should look like its a wild-west where each has its own rules. We are still working on the common goal and to achieve that common goal is to be transparent with what we are working on, have documentation for each services you own, work on the right stuff, so that by the end of the day our services/repos will still talk to each other without much fuss configuring them to... talk to each other, no redundancies in logics between repos - think as if it is still a one repo.

Current repos and their owners:

 - reader @sandae
 - renderer @jerome
 - dashboard @mark @arnold
 - sandbox @sandae
 - proof-library @jerome
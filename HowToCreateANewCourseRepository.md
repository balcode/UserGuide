## Create A Repository 

Create a new repository on Github whenever you create a new course. 

The following are the steps to create a new course repository on GitHub.

 1. On the upper-right corner of GitHub, click the `new symbol` **`+`** to create a new course repository. 
 
 2. On the `Create a new repository` page, enter the name of your new repository. All names course repositories must be in lowercase with each word separated by a dash. For example, `ca-school-php-introduction-course`.

 3. On your local computer, create a clone of your repository by opening your command line and typing this command: `git clone git@github.com:CodingAvenue/ca-school-php-introduction-course.git your-local-repository-name`

 4. In the cloned repository, run the following commands: 

 ```php
  git pull
  git checkout -b name-of-lesson-branch
 ```
`git pull` integrates a remote repository to your current branch.
`git checkout -b name-of-lesson-branch` creates a new branch. Note that the name of the branch only contains lower case letter, with each word separated by a hyphen `-`.

 5. From the existing repositories, copy the following folders/files to the cloned repository:
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

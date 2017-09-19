## Create A Repository 

The following are the steps to create a new course repository on GitHub.

 - On GitHub, create a new course repository. For example, "ca-school-php-introduction-course".

 Note: All names of course repositories must be in lowercase with each word separated by a dash.

 - On your local computer, create a clone of your repository by typing this command on your command line: `git clone git@github.com:CodingAvenue/ca-school-php-introduction-course.git your-local-repository-name`

 - On the cloned repository, run the following commands: 
 ```php
  git pull
  git checkout -b name-of-lesson-branch //to create a new branch.
 ```
  -  From the existing repositories, copy the following folders/files to the cloned repository:
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
 - Run `composer install`.

 - Copy the lesson content you created to the respective folders in the cloned repository.

 - Then run:
 ```php
    git add . -A
    git commit -m "Your commit message here"
    git push origin name-of-lesson-branch
 ```

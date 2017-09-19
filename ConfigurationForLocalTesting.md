# Configuration for local testing

Coding Avenue Proof Library was created with a mindset that it should work on any environment and not just on the CodeStop Sandbox. This allows authors to test their proof files locally.

In order for this library to work on your environment, create a `proof.json` configuration file on the root directory of your course. `proof.json` only needs 3 settings:

 - **codeFilePath** - This is the path to the file where the php file to be use by this library is located.
 - **answerDir** - This is the base directory for all test answers files.
 - **proofDir** - This is the base directory for all proof files.

Check [File Structure Requirements](https://github.com/CodingAvenue/ca-school-proof-library/wiki#file-structure-requirement) for details.

Once you save your settings, this library should be ready to work on your environment.

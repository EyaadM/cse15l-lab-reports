# Week 5 Lab Report

In the last lab report I covered a task that required me to clone a repository, use junit tests on a file in the repository, fix the error that the junit tests failed on, retest the file to show it works properly, and then update the github repository with the correct file. In lab, we competed with one another to complete this task as quickly as possible. In the time we were using to prepare, we realized that we could complete the entire task in around 10-15 seconds (depending on how long it takes to login and clone and push the github repo) using a script.

## The Script

```bash
git clone git@github.com:kevin-dough/lab7.git

javac -cp .:lab7/lib/hamcrest-core-1.3.jar:lab7/lib/junit-4.13.2.jar lab7/*.java

cd lab7

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples

sed -i '43s/index1/index2/g' ListExamples.java

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples

git add ListExamples.java
git commit -m "Updated"
git push
```
The script mostly just runs the exact same commands that you would manually:
- The first line clones the repository
- The second line compiles the java files with junit
- The third line enters the repository directory
- The fourth line runs the TestListExamples file
- The sixth line recompiles the java files with junit
- The seventh lines reruns the TestListExamples file
- The eigth, ninth, and tenth lines commit and push the repository

However, the fifth line uses a different command, sed. This command allows you to replace lines in files without even opening them, as long as you add the -i keyword (i stands for "in-place"). The 43 stands for the line number that is being edited, the s stands for substitute, while the g stands for global. Basically, the space next to s will be replaced by the space to the left of g for all lines unless the line is specified (like we do!). This allowed us to modify the error in the code without replacing index1 with index2 everywhere in the file, which would only have made the problem worse. Obviously, this script could not have been made without knowing what the error was in the first place, so replacing the sed line with nanoing the file instead would be useful if you didn't already know what the error was, as you would be able to find and fix the error with the script doing the rest of the work (like retesting the file and pushing and committing to github).

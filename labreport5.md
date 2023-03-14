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


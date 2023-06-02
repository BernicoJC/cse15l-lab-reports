# Lab Report 5 - Putting it All Together

In this lab report, I will show a debugging scenario and describe how I'd answer a hypothetical debugging problem not unlike how it happens on edStem. Furthermore, I will also write my end-of-the-quarter reflection here.

## Debugging Scenario
### The Original Student's Question
**Title:** Unable to start the autograder script on ieng6 server

**What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?**
MSI Windows Laptop, Windows 10, Chrome, bash terminal / Visual Studio Code

**Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.**
Hi, I'm trying to finish off my autograder script and it seemed to be working as intended when I tried to run it on my local terminal, same with local server. This is my intended output.
```
$ bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected
Cloning into 'student-submission'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
Finished cloning
student-submission/ListExamples.java
File found
Files compiled succesfully
Failures found
Out of 4 tests, you failed 3 :
1) testAlwaysFail(TestListExamples)
2) testAlwaysFail1(TestListExamples)
3) testAlwaysFail2(TestListExamples)
Your score is 25 out of 100
```
Meanwhile, when I tried to run it on the ieng6 server, this output shows up, which shows an error saying the files aren't compiling. This means that I can't even run the java file for starting the server.
```
Cloning into 'student-submission'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
Finished cloning
student-submission/ListExamples.java
File found
grading-area/TestListExamples.java:1: error: package org.junit does not exist
import static org.junit.Assert.*;
                       ^
grading-area/TestListExamples.java:2: error: package org.junit does not exist
import org.junit.*;
^
grading-area/TestListExamples.java:13: error: cannot find symbol
  @Test(timeout = 500)
   ^
  symbol:   class Test
  location: class TestListExamples
grading-area/TestListExamples.java:22: error: cannot find symbol
  @Test
   ^
  symbol:   class Test
  location: class TestListExamples
grading-area/TestListExamples.java:26: error: cannot find symbol
  @Test
   ^
  symbol:   class Test
  location: class TestListExamples
grading-area/TestListExamples.java:30: error: cannot find symbol
  @Test
   ^
  symbol:   class Test
  location: class TestListExamples
grading-area/TestListExamples.java:19: error: cannot find symbol
    assertEquals(expected, merged);
    ^
  symbol:   method assertEquals(List<String>,List<String>)
  location: class TestListExamples
grading-area/TestListExamples.java:24: error: cannot find symbol
    assertFalse(true);
    ^
  symbol:   method assertFalse(boolean)
  location: class TestListExamples
grading-area/TestListExamples.java:28: error: cannot find symbol
    assertFalse(true);
    ^
  symbol:   method assertFalse(boolean)
  location: class TestListExamples
grading-area/TestListExamples.java:32: error: cannot find symbol
    assertFalse(true);
    ^
  symbol:   method assertFalse(boolean)
  location: class TestListExamples
10 errors
Your files failed to compile
```
Here is a screenshot of the bit that's probably triggering the bug, since it is where `"Your files failed to compile"` should be printed from.
![Image](Images/0.png)

**Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.**
The command that I did, as shown above, is `bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected`. However, I'm pretty sure that it isn't the command-line argument that's causing this as it is the correct version with all of the infrastructures like the `ListExamples.java` file intact. My working directory for the ieng6 run was `[cs15lsp23lr@ieng6-203]:list-examples-grader:510`. I didn't run anything before the run on the ieng6 server, other than the usual `cd` and `ls` commands, along with `git clone ` method to clone the same repository I'm using on local.

### Leading question / command suggestion
Hi Bernico, looking over your error message, this seems to be an error with your script trying to run the tester file. Here are a few things that you should check out.
1. Since you're starting it fresh from the github, maybe your local directory has something set up that isn't yet established in the github repository. Try to check the directory you're running the commands in. In particular, try to make sure that the tester's library folder is in there. You can do this by doing `ls [folder name]` in said directory.
2. If it still fails, then try to look over your bash script and see if there are any

### The student's followup and the bug itself

### The final TA's answer and information

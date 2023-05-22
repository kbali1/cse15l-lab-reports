#### Kirsten Bali

# Lab Report 4

### 1. Log into ieng6
![Image](Capture.PNG)

First I set my default terminal to git bash and typed in the terminal line `ssh cs15lsp23aa@ieng6.ucsd.edu` <enter>. Then I typed in my password and pressed enter to login. After I logged in, the image above shows what was displayed on my screen in the terminal.

  
### 2. Clone the Repository from Github 
![Image](Lab7GitClone.PNG)

To clone this repsoitory, I first typed `ls` to see which which directory I was in and typed `cd <filename>`, so I can clone the repository in the directory I want to. After that I typed `git clone https://github.com/ucsd-cse15l-s23/lab7` and pressed enter to clone the repository. The image above shows that the repository was successfully cloned.

  
### 3. Run the Tests
![Image](Lab7MyFail.png)

To compile the code in the lab7 file, I ran the command line `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` <enter> and ran the tests by using the command line `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` <enter> in the terminal. After the code compiles and runs, it should show on the screen that the tests fail as shown in the image above.


### 4. Fix the Failing Tests
![Image](Lab7FixedBugs.png)
  
To fix the failing tests, I have to edit the file `ListExamples.java`. I edited this file by using vim and opened it up by running the command lim `vim ListExamples` and pushed enter. The terminal opened it up on vim. The screen that should appear in the terminal is shown in the image above. To edit the code on vim, press these keys: <esc>, <j> 42 times, <i>, <l> 12 times, <2>, <backspace>, <esc> and <:wq>. 
Pressing the "esc" button to make sure you are in normal mode. The "j" moves the cursor down to the line where it shows `index1 += 1` in the last while loop. The "i" changes vim to insert mode so I can press "l" 12 times to move the cursor to the right 12 times. Pushing the number 2 on the keyborad and the backspace button allows `index1` to be changed to `index2`. Pressing the "esc" button puts vim back into normal mode. I can now save changes and exit vim by typing ":wq".


### 5. Run the Tests Again
![Image](Lab7Mysuccess.PNG)

Like in step 3, to compile the code run the command line in the terminal, type `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and push enter. Run the code by typing `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` and pressing enter. The screen should show that the tests passed after it ran.

  
### 6. Commit and Push Changes
![Image](gitcommitlab7.png)
![Image](gitpushlab7.png)

Though I was unable to complete the last step due to an error in generating an ssh key for github, to commit and push the changes to my GitHub account, I would type the command `git commit -m "edit lab7"` and `git push origin main`. The message does not have to be "edit lab7." It can be anything as long as it is in quotes in the commit command line. The branch does not have to be main in the push command line. It just has to be a brach name.

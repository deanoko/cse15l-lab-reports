# Lab-Report4 - vim

`part1: Write a webserver called StringServer`

1. Log into ieng6

- `ssh cs15lfa23m@ieng6.ucsd.edu <enter>`

![Image](ienglogined.png)

2. Clone your fork of the repository from your Github account (using the SSH URL).

-  `git clone <Ctrl> <V> <enter>`

-  Ctrl+V is git@github.com:deanoko/lab7.git

![Image](gitclone2.png)

3. Run the tests, demonstrating that they fail.

- `cd lab7 <enter> bash test.sh <enter>`
  
- cd lab7 means changing directory to lab7
  
- test.sh means running the program
  
- Failed message
  
![Image](failedmessage.png)


4. Edit the code file ListExamples.java to fix the failing test (as a reminder, the error in the code is just that index1 is used instead of index2 in the final loop in merge).

- `vim ListExamples.java <Enter>`
  
![Image](logintovim2.png)

- 'Fix Problem1'
  
![Image](problem1.png)

`<down><down><down><down><down><down><down><down><down><down><down><down><down><down><right><right><right><right><right><right><right><right><right><right><right><right><right><right><right><right><right><right><right><right><right><right> <i> <backspace><backspace><backspace> <esc>`

- The line that have error is located in 15 rows, which made me press down 14 times.

- Press the <i> to revise the code and press the <backspace> 3 times to delete the wrong code.

- after fixing the code, press the <esc> to end revising the code.
  
![Image](fix1.png)

- `Fix Problem2`

![Image](problem2.png)

`<down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><down><left><left><left><left><left> <i> <backspace> <2> <esc>`

- The line that have error is located in 44 rows, which made me press down 29 times.

- Press the <i> to revise the code and press the <backspace> 1 times to delete the wrong code and then type in the 2.

- after fixing the code, press the <esc> to end revising the code.

![Image](fix2.png)

- to exit from vim: `:wq <enter>`

- meaning :wq is that exit with save from vim.
  
5. Run the tests, demonstrating that they now succeed.

`bash test.sh <enter>`

![Image](successtest.png)

6. Commit and push the resulting change to your Github account.

`<git add ListExamples.java> <enter> git commit <enter> error fixed <enter>`
 
 ![Image](gitmessage.png)
 
 ![Image](gitcommit2.png)

---


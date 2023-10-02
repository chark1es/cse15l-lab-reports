
# Lab Report
We learned a few commands with using the terminal, such as `cd`, `ls`, and `cat`.

Here are a few examples as to using these three commands:

# `cd` command
### No Arguments
Input:
```bash
cd
```

Output:

There is no output. The current working directory is `/home`. The reason why I got this output is because the command `cd` is meant to change the directory. If there is no directory given, it wont move me to a different directory and thus have no output.

### Directory as an argument

Input:
```bash
cd testFolder
```

Output:

```bash
[user@sahara ~/testFolder]$
```

This time there is no actual output, but it does change the current directory that I am in. This can be indicated with the folder name next to the username `~/testfolder$`. 
The current directory I was in is `/home`. 
I got this output because I changed the folder I was originally in and switched to a new folder.

### File as an argument

Input:
```bash
cd test1.txt
```

Output:
```bash
bash: cd: test1.txt: Not a directory
```

The above codeblock is my output. The current directory is `/home/testFolder`. I got this output because the `cd` command is meant to change directories, meaning change folders.
Since `test1.txt` is not a folder, it gives us an error.

# `ls` command

### No Arguments
Input:
```bash
ls
```

Output:
```bash
test1.txt  test2.txt
```
The above codeblock is my output The current directory is `/home/testFolder`. 
I got this output because the command `ls` is meant to list all folders and files listed in the current working directory.

### Directory as an argument
Input:
```bash
ls ..
```

Output:
```bash
testFolder
```
The above codeblock is my output. The current directory is `/home/testFolder`. 
I got this output because the command `ls` is meant to list all folders and files listed in the directory that it was provided. In this case, it would be the directory `/home`.

### File as an argument
Input:
```bash
ls test1.txt
```

Output:
```bash
test1.txt
```

The above codeblock is my output. The current directory is `/home/testFolder`. 
I got this output because when having a file as it's argument, it will just return (or print out) the file that you provided.
However, if the file does not exist, it will print out `ls: cannot access 'file.txt': No such file or directory` instead.

# `cat` command
### No arguments
Input:
```bash
cat
```

Output:
```bash

```
The above codeblock is my output. The current directory is `/home/testFolder`. 
The output is actually a little unique, as it takes in an input from the user and will print out whatever it was inputted. For example, if I inputted `bob`, it will print out `bob`.

### Directory as an argument
Input:
```bash
cat testFolder
```

Output:
```bash
cat: testFolder: Is a directory
```

The above codeblock is my output. The current directory is `/home`. 
The output just gives an error, since the `cat` command takes in files and not directories.

### File as an argument
Input:
```bash
cat test1.txt test2.txt
```

Output:
```bash
Hello
World
```

The above codeblock is my output. The current directory is `/home/testFolder`. 
The output will print out each file on a new line. In this case, `test1.txt` contains the word `Hello` while `test2.txt` contains the word `World`. It prints out the two words on a separate line.

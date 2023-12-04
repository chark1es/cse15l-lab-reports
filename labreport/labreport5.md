# Lab Report 5

## Part 1

### Student's Initial Question:

Hello! I'm currently having trouble when trying to compile my file using bash. Here is my the code to my java file:

```java
public class testScenario {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

and the code to my bash file:

```
rm testScenario.class
javac -cp .;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar *.java
java testScenario
```

This is the error I get:

```bash
cse15l-lab-reports/labreport/labreport5_scenario on  main [!?] via  v11.0.18
❯ bash test.sh
error: no source files
test.sh: line 2: lib/hamcrest-core-1.3.jar: Permission denied
test.sh: line 2: lib/junit-4.13.2.jar: Permission denied
Error: Could not find or load main class testScenario
Caused by: java.lang.ClassNotFoundException: testScenario
```

Can you help me address the problem?

### TA's Response:

Hello! Can you provide me with the following details?

-   Your OS
-   Your folder structure

### Student's Response:

My Operating System is MacOS.

My folder structure is:

```
labreport5_scenario
├── lib
│   ├── hamcrest-core-1.3.jar
│   └── junit-4.13.2.jar
├── test.sh
└── testScenario.java
```

### TA's Response

It seems like you have an error in your bash script. Remember, `;` is for windows while `:` is for MacOS.

### Student's Response

Thank you so much!

This is what my script now looks like:

```
rm testScenario.class
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java testScenario
```

And I get this result:

```bash
❯ bash test.sh
rm: testScenario.class: No such file or directory
Hello, World!
```

Thank you again!

### Summary:

File Structure:

```
labreport5_scenario
├── lib
│   ├── hamcrest-core-1.3.jar
│   └── junit-4.13.2.jar
├── test.sh
└── testScenario.java
```

Bugged Code:

```
rm testScenario.class
javac -cp .;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar *.java
java testScenario
```

Fixed Code:

```
rm testScenario.class
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java testScenario
```

How the code was fixed:

-   Replace the `;` with `:`

Command Line to trigger the bug:

```
bash test.sh
```

## Part 2

### My reflection

Something I learned that proved to be useful (and new) was learning how to access a remote computer without needing a password. I learned how to create a public key and private key, and

Its something that I find super useful as it can same time in the long run.

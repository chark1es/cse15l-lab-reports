# Lab Report 5

## Part 1

### Student:

Hello! I'm currently having trouble when trying to compile my file using bash. Here is my the code to my java file:

```java
public class testScenario {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

and the code to my bash file:

```bash
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java testScenario.java
```

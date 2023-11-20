# Lab Report 3 - Charles Nguyen

## Part 1

### Failure-inducing input

```java

@Test
  public void testNull() {
    int[] input1 = null;
    assertThrows(NullPointerException.class, () -> {
      ArrayExamples.reversed(input1);
    });
  }

```

### Code that does not contain a failure:

```java

 @Test
  public void testReversedNumbers() {
    int[] input1 = {3, 4, 5};
    assertArrayEquals(new int[]{ 5, 4, 3 }, ArrayExamples.reversed(input1));
  }

```

### Symptom:

```bash
╭╴at …\UCSD\CSE 15L\Lab4 on  main (  ) via ☕ v21.0.1
╰─ java -cp .;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar org.junit.runner.JUnitCore ArrayTests
JUnit version 4.13.2
.E..E.
Time: 0.011
There were 2 failures:
1) testNull(ArrayTests)
java.lang.NullPointerException: Cannot read the array length because "<parameter1>" is null
        at ArrayExamples.reversed(ArrayExamples.java:15)
        at ArrayTests.testNull(ArrayTests.java:28)
2) testReversedNumbers(ArrayTests)
arrays first differed at element [0]; expected:<5> but was:<0>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:418)
        at org.junit.Assert.assertArrayEquals(Assert.java:429)
        at ArrayTests.testReversedNumbers(ArrayTests.java:22)
        ... 30 trimmed
Caused by: java.lang.AssertionError: expected:<5> but was:<0>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 36 more

FAILURES!!!
Tests run: 4,  Failures: 2
```

### Bugged Code:

```java
public class ArrayExamples {

  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }

}
```

### Fixed Code:

```java
public class ArrayExamples {

  static int[] reversed(int[] arr) {
    if (arr == null) { return new int[] {}; }
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[arr.length - i - 1] = arr[i];
    }
    return newArray;
  }

}
```

### Symptom:

```bash
╭╴at …\UCSD\CSE 15L\Lab4 on  main (  ) via ☕ v21.0.1
╰─ java -cp .;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar org.juni
t.runner.JUnitCore ArrayTests
JUnit version 4.13.2
....
Time: 0.008

OK (4 tests)
```

#### Explanation:

The bug in the code was that it did not properly reverse the contents in the list. The reason for that was because when it loops through the list `arr`, it would override the array with an empty item from the `newArray` (since it was created with empty items with the same length as `arr`). My fix makes it to where it stores the item in the `newArray` in reverse order, by going backwards in the list. I also made it so when the value is null, it just returns an empty array.

## Part 2

The command I chose was the `find` command.

### -delete

What this argument does is that it finds the directories / files and deletes whichever matches the statement. This command is useful because it can delete folders / subfolders in bulk without needing to manually select anything.

#### File

```bash
find test.py -delete
```

No additional feedback was given. This function finds the specified file and tries to delete it. This command is useful because it deletes the file specified (and can be more advanced when using regex)

#### Directory

```bash
find test -delete
```

No additional feedback was given. This function finds the specified folder and tries to delete it. This command is useful because it deletes the folder specified (and can be more advanced when using regex)

### -empty

This arguments checks to see if there are any empty folders / files. This command can be useful, especially when paired up with the `-delete` argument to help clear up folders / files.

#### File

When a file is empty:

```bash
find test.py -empty

test.py
```

When a file is not empty:

```bash
find test.py -empty
```

This command finds any empty files, and if the file is empty, it will display the list of empty files. This is useful to get rid of any clutter or unneccessary files and can pair well witht the -delete argument.

#### Directory

When a directory is empty:

```bash
find test -empty

test
```

When a directory is not empty:

```bash
find test -empty
```

This command finds any empty folders, and if the folder is empty, it will display the list of empty folder. This is useful to get rid of any clutter or unneccessary files and can pair well witht the -delete argument.

### -iname

This argument is similar to the `-name` argument but it is case-insensitive. This command is useful to find general files or folders without needing to worry about how it is spelled out.

#### File

```bash
find . -iname "*.py"

./test.py
```

This command finds the file based on what we specify. This is useful when trying to locate where a specific file is when there is a bunch of files and folders.

#### Directory

```bash
find . -iname Test

./test
```

This command finds the folder based on what we specify. This is useful when trying to locate where a specific folder is when there is a bunch of files and folders.

### -regex

This command finds and matches any regex expressions that is provided. This command is useful when looking for specific file / folders names or file extensions

#### File

```bash

find . -regex ".*\.\(py\)"

./test.py

```

This command is useful because it allows us to find files using regex, which gives us a much broader range of control as to what we want to specify.

#### Directory

```bash

find . -regex '\./test'

./test
```

This command is useful because it allows us to find folders using regex, which gives us a much broader range of control as to what we want to specify.

### Sources

All arguments were found by using `man find` in a MacOS terminal. I also used the website **man7** `(https://man7.org/linux/man-pages/man1/find.1.html)` for a easier way to search (using `Ctrl + F`).

In terms of the placement of the arguments, it was simply done through trial and error in VS Code.

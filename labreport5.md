# Lab-Report5 - Putting it All Together

`part1: Debugging Scenario`

```
Subject: Issue with my Java Program

Hello,

I'm encountering an issue with the reverseInPlace method in my Java code.
The function is supposed to reverse the input array in-place, but it seems like there's a bug.
I've attached a screenshot of the problematic code below.

```
```
Error Code :
 // Changes the input array to be in reversed order
    static void reverseInPlace(int[] arr) {
        for (int i = 0; i < arr.length; i += 1) {
            arr[i] = arr[arr.length - i - 1];
        }
    }

```
```
Test Code :
 @Test
 public void testReverseInPlace() {
   int[] input1 = { 3, 4, 5, 6, 7 };
   ArrayExamples.reverseInPlace(input1);
   assertArrayEquals(new int[] { 7, 6, 5, 4, 3 }, input1);
 }
```

```
Description of the issue:
I suspect the issue is with the reverseInPlace method, but I can't quite figure out what's wrong. Any insights?
Thanks!
```
---

`2. A response from a TA asking a leading question or suggesting a command to try`

```
Hi there!

Thanks for reaching out. It looks like there might be an issue with your program.
But, I need more information to figure out what the problem is.
Could you run the program and share the output with me?

Thank you.
```
---

`3.Another screenshot/terminal output showing what information the student got from trying that, and a clear description of what the bug is.`

```
There was 1 failure:
1) testReverseInPlace(ArrayTests)
arrays first differed at element [3]; expected:<4> but was:<6>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:418)
        at org.junit.Assert.assertArrayEquals(Assert.java:429)
        at ArrayTests.testReverseInPlace(ArrayTests.java:10)
        ... 32 trimmed
Caused by: java.lang.AssertionError: expected:<4> but was:<6>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 38 more

FAILURES!!!
Tests run: 1,  Failures: 1
```
---
`A response from a TA asking a leading question or suggesting a command to try`

```
Hi there!

Thanks for reaching out. It looks like there might be an issue with your reverseInPlace method.
The logic you've shared seems to be modifying the array, but it might not be achieving the desired reversal.

Could you try replacing your reverseInPlace method with the following code and run your test again?
This code reverses the array by swapping elements up to the middle point. Give it a try and let me know how it goes!
```

```
Code:
  static void reverseInPlace(int[] arr) {
    for (int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```
---

```
Hey,

I tried the updated code for reverseInPlace, and it worked! The array is now being reversed as expected.
The test passed successfully. Thanks a lot for your help! Any idea why the original code was causing issues?
```

![Image](testok.png)

---
4.Bug Description:
```
The original reverseInPlace method was incorrectly modifying the array, leading to unexpected results.
The corrected code swaps elements up to the middle point, ensuring a proper in-place reversal.
```

---
5.At the end, all the information needed about the setup including:
- The file & directory structure needed

```
lab3
 -lib
  - ArrayExamples.java
  - ArrayTests.java
  - test.sh
```

- The contents of each file before fixing the bug

`1.ArrayExamples.java`

```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}
```
`2.ArrayTests.java`

```
@Test
public void testReverseInPlace() {
  int[] input1 = { 3, 4, 5, 6, 7 };
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[] { 7, 6, 5, 4, 3 }, input1);
}
```
`3.test.sh`

```
 javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java
 java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ArrayTests
```
- The full command line (or lines) you ran to trigger the bug

`bash test.sh`

- `A description of what to edit to fix the bug:`

`In the ArrayExamples.java file, update the reverseInPlace method to correctly reverse the array using a proper swapping technique:`

- made a new int temp to fix the problem.

```
  static void reverseInPlace(int[] arr) {
        for (int i = 0; i < arr.length / 2; i += 1) {
            int temp = arr[i];
            arr[i] = arr[arr.length - i - 1];
            arr[arr.length - i - 1] = temp;
        }
    }
```
`After making this change, recompile the code and run the test again using the same commands, and the test should pass successfully.`

---

`Part 2 – Reflection`

```
When I initially enrolled in this course, my knowledge of GitHub was limited.
However, through the course, I gained a comprehensive understanding of GitHub and learned valuable methods
like git push and git commit.
Utilizing tools like vim, I found it extremely beneficial to navigate and rectify errors in my code.
This course not only enhanced my proficiency in using GitHub but also provided insights into a more organized file system,
aiding in the identification and modification of files.
Overall, it has been a valuable experience, contributing significantly to my skill set and understanding of version control.
```

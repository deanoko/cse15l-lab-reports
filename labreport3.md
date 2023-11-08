# Lab-Report3

`part1: Bugs`

1. The Failure inducing input
   public void testReverseInPlace() {
    int[] input1 = { 3, 4, 5, 6, 7 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[] { 7, 6, 5, 4, 3 }, input1);

2. The symptome: Arrays first differed at element[0]; expected:<8> but was:<1>.

3. The Bug:

   reversed Changed:

   static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for (int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }

I interchanged newArray and the index for arr and replaced the return statement from arr to newArray.

The bug was that the new list was not having any values assigned to it.

arr[i] = newArray[arr.length - i - 1];

To this code

newArray[i] = arr[arr.length - i - 1];

![Image](notfixedbug.png)
 
![Image](fixedbug.png)


---

`part2:  Researching Commands`

'grep'

- The grep command allows you to search one file or multiple files for lines that contain a patter. Exit status is 0 if matches were found, 1 if no matches were found, and 2 if errors occurred.

1. The 'grep' command: Option -i

   - When searching igonre uppercase vs lowercase.

   - Useful: This Searches for the given string/pattern case insensitively. so it masthces all the words insensitiely as shown below.




---


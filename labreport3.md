# Lab-Report3

**part1: Bugs**

1. The Failure inducing input
```
public void testReverseInPlace() {
    int[] input1 = { 3, 4, 5, 6, 7 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[] { 7, 6, 5, 4, 3 }, input1);
```
3. The symptome: Arrays first differed at element[0]; expected:<8> but was:<1>.

4. The Bug:

   reversed Changed:
```
   static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for (int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
I interchanged newArray and the index for arr and replaced the return statement from arr to newArray.

The bug was that the new list was not having any values assigned to it.

`arr[i] = newArray[arr.length - i - 1];`

To this code

`newArray[i] = arr[arr.length - i - 1];`

---

`part2:  Researching Commands`

'grep'

- The grep command allows you to search one file or multiple files for lines that contain a patter. Exit status is 0 if matches were found, 1 if no matches were found, and 2 if errors occurred.

1. The 'grep' command: Option -i

   - When searching igonre uppercase vs lowercase.

   - Useful: This Searches for the given string/pattern case insensitively. so it masthces all the words insensitiely as shown below.

```
Dean@LAPTOP-TA1ANDA7 MINGW64 ~/docsearch (main)
$ grep -i "Korea" technical/*/*.txt
technical/911report/chapter-11.txt:                in Korea another. But these were attacks by major powers. While by no means as
technical/911report/chapter-11.txt:                the main focus (war in Korea), and as too unrealistic. As we pointed out in chapter
technical/911report/chapter-12.txt:                not experienced such a rapid surge in national security spending since the Korean
technical/911report/chapter-13.4.txt:                Khallad, Aug. 13, 2003; Apr. 5, 2004. According to Khallad, Thailand, South Korea,
technical/911report/chapter-5.txt:                Singapore, or Korea.) This part of the operation has been confirmed by Khallad, who
technical/911report/chapter-5.txt:                Thailand, South Korea, Hong Kong, or Malaysia, and using Yemenis who would not need
technical/911report/chapter-6.txt:                emphasized other issues such as North Korea and the Israeli- Palestinian peace
technical/911report/chapter-6.txt:                with the faltering Middle East peace process and North Korea. Clarke said that the
technical/biomed/1471-2148-2-17.txt:          Korea, and was previously considered a species of subg. 
technical/biomed/1471-2148-2-17.txt:          Europe and the Far East in Manchuria, Korea, and Japan.
technical/biomed/1471-2156-3-11.txt:          from SeeGene (Seoul, Korea). The 
technical/biomed/1472-6823-2-2.txt:          Jolla, CA; Sofia, Bulgaria; Seoul, South Korea and São
technical/biomed/1472-6823-2-2.txt:          Brazil; The Catholic University of Korea, Seoul, South
technical/biomed/1472-6823-2-2.txt:          Korea). No information that would identify the subjects
technical/biomed/1472-6920-2-3.txt:        South Korea [ 5 ] and for a Turkish medical school [ 6 ] .
technical/plos/journal.pbio.0020121.txt:        imported cases in the Republic of Korea, but surveillance has not been thorough in North

```

   I got all words include "Korea"
   
2.  Example 2: "Design"

```

Dean@LAPTOP-TA1ANDA7 MINGW64 ~/docsearch (main)
$ grep -i "Design" technical/*/*.txt

technical/biomed/1471-2474-2-1.txt:        Assuming an unmatched case control design with alpha = 0.05
technical/biomed/1471-2474-2-1.txt:        prophylaxis, an unmatched case-control study design was
technical/biomed/1471-2474-2-1.txt:        employed. This type of study design has the advantage of
technical/biomed/1471-2474-2-2.txt:          primers (Table 1) designed for osteocalcin, type I
technical/biomed/1471-2474-2-2.txt:          group respectively. The experiment was designed to have
technical/biomed/1471-2474-2-2.txt:          the four rats designated for study at 6 weeks after
technical/biomed/1471-2474-3-23.txt:        Various designs of interbody fusion cages have been
technical/biomed/1471-2474-3-23.txt:        dependent on the design of the cage. The single large
technical/biomed/1471-2474-3-23.txt:        cage design. In a study on calf and pig spine, two
technical/biomed/1471-2474-3-23.txt:        potential of the three cage designs, but the cylindrical
technical/biomed/1471-2474-3-23.txt:        cylindrical cages are designed to engage into the
technical/biomed/1471-2474-3-23.txt:        smooth surface, designed to fit the endplate contours.
technical/biomed/1471-2474-3-23.txt:        stability in lumbar spine after fixation with a new design
technical/biomed/1471-2474-3-23.txt:          The rectangular cage design
technical/biomed/1471-2474-3-23.txt:          The newly designed rectangular cage (Fig 1) (made by
technical/biomed/1471-2474-3-23.txt:          rectangular design to restore the lumbar lordosis. The
technical/biomed/1471-2474-3-23.txt:          designed to engage into the endplate to provide

```
- There are more results. I typed "Design", which finds instances of "design" because it ignores upper / lower cases.

---
2. The 'grep' command: Option -b

- Display the block number at the beginning of each line.

- Useful: -b is the option which prints the specified N lines before the match. When doing a grep on a huge file, it may be useful to see some lines after the match.

Example 1: "ucsd"
```

$ grep -b "ucsd" technical/*/*.txt
technical/biomed/1471-2121-2-22.txt:10005:        http://ncmir.ucsd.edu/~perkins/tBid. For example, it became
technical/biomed/1471-2164-3-18.txt:39874:          http://genome.ucsd.edu/index.html [ 54 55 ] . The

```
- 10005 and 39874 is the block number at the beggining of each line.

Example 2: "South Korea"
```
$ grep -b "South Korea" technical/*/*.txt
technical/911report/chapter-13.4.txt:35297:                Khallad, Aug. 13, 2003; Apr. 5, 2004. According to Khallad, Thailand, South Korea,
technical/911report/chapter-5.txt:38494:                Thailand, South Korea, Hong Kong, or Malaysia, and using Yemenis who would not need
technical/biomed/1472-6823-2-2.txt:4416:          Jolla, CA; Sofia, Bulgaria; Seoul, South Korea and São
technical/biomed/1472-6920-2-3.txt:426:        South Korea [ 5 ] and for a Turkish medical school [ 6 ] .
```
-The numbers are the block numbers [35297,38494,4416,426].

---
3. The 'grep' command: Option -w

- Display matching whole word.

- Useful: searching for whole word, so I can find only typing word will show out all the lines eventhought the word is normal.

Example 1:"Korea"
```
Dean@LAPTOP-TA1ANDA7 MINGW64 ~/docsearch (main)
$ grep -w "Korea" technical/*/*.txt
technical/911report/chapter-11.txt:                in Korea another. But these were attacks by major powers. While by no means as
technical/911report/chapter-11.txt:                the main focus (war in Korea), and as too unrealistic. As we pointed out in chapter
technical/911report/chapter-13.4.txt:                Khallad, Aug. 13, 2003; Apr. 5, 2004. According to Khallad, Thailand, South Korea,
technical/911report/chapter-5.txt:                Singapore, or Korea.) This part of the operation has been confirmed by Khallad, who
technical/911report/chapter-5.txt:                Thailand, South Korea, Hong Kong, or Malaysia, and using Yemenis who would not need
technical/911report/chapter-6.txt:                emphasized other issues such as North Korea and the Israeli- Palestinian peace
technical/911report/chapter-6.txt:                with the faltering Middle East peace process and North Korea. Clarke said that the
technical/biomed/1471-2148-2-17.txt:          Korea, and was previously considered a species of subg. 
technical/biomed/1471-2148-2-17.txt:          Europe and the Far East in Manchuria, Korea, and Japan.
technical/biomed/1471-2156-3-11.txt:          from SeeGene (Seoul, Korea). The 
technical/biomed/1472-6823-2-2.txt:          Jolla, CA; Sofia, Bulgaria; Seoul, South Korea and São
technical/biomed/1472-6823-2-2.txt:          Brazil; The Catholic University of Korea, Seoul, South
technical/biomed/1472-6823-2-2.txt:          Korea). No information that would identify the subjects
technical/biomed/1472-6920-2-3.txt:        South Korea [ 5 ] and for a Turkish medical school [ 6 ] .
technical/plos/journal.pbio.0020121.txt:        imported cases in the Republic of Korea, but surveillance has not been thorough in North
```
- Display "Korea" and "korea" whole word.

Example 2: "fbi"
```
$ grep -w "fbi" technical/*/*.txt
technical/911report/chapter-13.3.txt:                FBI" (online at www.fbi.gov/libref/historic/history/historymain.htm); the FBI's
technical/911report/chapter-13.3.txt:                updated June 18, 2003 (online at www.fas.org/irp/agency/doj/fbi/fbi_hist.htm). For
```
-Display "fbi" and "FBI" Whole word.


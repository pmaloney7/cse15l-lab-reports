# Lab Report 3

Method being tested:
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for (int i=0; i<arr.length; i++) {
    arr[i] = newArray[arr.length-i-1];
  }
  return arr;
} 
```
Failure inducing input:
```
@Test
public void myTestReverse() {
  int[] input1 = {1,2,3,4};
  int[] expected = {4,3,2,1};
  assertArrayEquals(expected, ArrayExamples.reversed(input1));
}
```
Input that doesn't induce failure:
```
@Test
public void myTestReverseSuccess() {
  int[] input1 = {0,0,0,0};
  int[] expected = {0,0,0,0};
  assertArrayEquals(expected, ArrayExamples.reversed(input1));
}
```
Symptom after running tests:
```
[user@sahara ~/lab3]$ javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java
[user@sahara ~/lab3]$ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ArrayTests
JUnit version 4.13.2
.E...
Time: 0.007
There was 1 failure:
1) myTestReverse(ArrayTests)
arrays first differed at element [0]; expected:<4> but was:<0>
   at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
   at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
   at org.junit.Assert.internalArrayEquals(Assert.java:534)
   at org.junit.Assert.assertArrayEquals(Assert.java:418)
   at org.junit.Assert.assertArrayEquals(Assert.java:429)
   at ArrayTests.myTestReverse(ArrayTests.java:23)
   ... 30 trimmed
Caused by: java.lang.AssertionError: expected:<4> but was:<0>
   at org.junit.Assert.fail(Assert.java:89)
   at org.junit.Assert.failNotEquals(Assert.java:835)
   at org.junit.Assert.assertEquals(Assert.java:120)
   at org.junit.Assert.assertEquals(Assert.java:146)
   at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
   at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
   ... 36 more

FAILURES!!!
Tests run: 4, Failures: 1


[user@sahara ~/lab3]$ javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java
[user@sahara ~/lab3]$ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ArrayTests
JUnit version 4.13.2
...
Time: 0.008
OK (3 tests)
```
The bug before fix:
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for (int i=0; i<arr.length; i++) {
    arr[i] = newArray[arr.length-i-1];
  }
  return arr;
} 
```
After fix:
```
static int[] reversed(int[] arr) {
  int[] newArray = new int[arr.length];
  for (int i=0; i<arr.length; i++) {
    newArray[i] = arr[arr.length-i-1];
  }
  return newArray;
} 
```

Originally, the method in question was copying the contents of newArray and organizing them into arr. newArray is created at the beginning of the method with the same size as arr, which automatically fills the contents of newArray with zeroes. When the loop iterates through newArray, it just copies over the zeroes to arr. The updated reversed method instead iterates through arr and copies over the value to newArray, which is blank. It then returns newArray, which has the updated values in correct reverse order.

## Grep commands
```
grep -n "string" <filename>
```
Searches for the term "string" inside `filename` and displays the line numbers in the output. Each matching line will be preceded by the line number in the file where it was found. -n is a flag that indicates to include line numbers in the output, and can be useful when needing the location of text within a file.
```
INPUT: $ grep -n "hypothesis" 1471-213X-2-1.txt
OUTPUT: 37: hypothesis that a balance exists between serine proteases 40: initiated to test this hypothesis 277: neuronal migration. This hypothesis is supported by our 354: data support the hypothesis that changes in enzymatic 399: on migration, strengthens our hypothesis that this serine

INPUT: $ grep -n “Canada” chapter-6.txt
OUTPUT: 125: Ahmed Ressam, 23, had illegally immigrated to Canada in 1994. Using a falsified 134: $12,000. Back in Canada, he went about procuring weapons, chemicals, and false 138: travel documents to enter Canada, Ressam decided to carry out the plan alone. By the 159: Canada, to Port Angeles, Washington. Ressam planned to drive to Seattle and meet 177: and then return to Canada. Impressed, Abu Zubaydah asked Ressam to get more genuine 392: controls on the Canadian border (including stepping up U.S.-Canada cooperation). The 624: undertaking a Joint Perimeter Defense program with Canada to establish
```



```
grep -l "string" <filename>
```
Searches for the term "string" inside `filename` and returns the name of the file if the input string is found. -l is a flap that indicates to output names of files with matching lines. This is useful when knowing the contents of the file but not the file in question.
```
INPUT: $ grep -l “Bin Laden” *
OUTPUT: chapter-11.txt chapter-13.3.txt chapter-13.4.txt chapter-13.5.txt chapter-6.txt

INPUT: $ grep -l “Lincoln” *
OUTPUT: chapter-13.5.txt chapter-3.txt
```



```
grep -i "string" <filename>
```
Searches for the term "string" inside `filename`, without being case sensitive. It will output text from the specified file with any variation of the search string. Notice how the text returned below includes "BMI", but when the command was run, "Bmi" was used as the parameter. -i is the flag that ignores case sensitivity.
```
INPUT: $ grep -i "Bmi" 1468-6708-3-1.txt
OUTPUT: between body mass index (BMI) and mortality, controlling excess risk for persons with very low BMI, but that persons with moderately high BMI had little or no extra risk except because few studies have examined the relation of BMI to events [ 10 ]. In this paper we study whether BMI at to BMI was calculated as measured weight in kilograms BMI of 18.5 to 24.9; overweight as 25 to 29.9; and separately the group with BMI between 18.5 and 20, which with BMI. To adjust for possible confounding we chose and likely to be related to BMI. Self-reported covariates plotted mean adjusted YOL and YHL against BMI, and tested for difference among BMI groups using confidence the effect size for each measure, comparing each BMI smokers. Black women had a higher mean BMI and higher percent obese (BMI ≥ 30) than the other three groups. Black statistically significant (p <.05) except for BMI and significant differences between black and white for BMI, the difference in BMI was no longer statistically significantly on BMI, BMI>30, weight loss since age 50, We next examined the relationship of BMI to YOL and YHL. BMI below 18.5, but averaged 6.6 years for women with a BMI only discrepancy is for men with BMI < 18.5, a category with BMI from 18.5 to 20 would be considered ‘normal’ by increase sample size for those with low BMI, we combined the two lower categories, defining underweight as a BMI BMI. For each BMI category the mean and its 95% confidence between BMI and YOL for BMI above 20. Underweight women normal group. The relationship of BMI to YHL for men is similar, but differences among BMI groups were not to the normal BMI group. The effect sizes are shown in et al proposed a desirable BMI 0. BMI Body mass index

INPUT: $ grep -i “hYpOtHeSiS” 1471-213X-2-1.txt
OUTPUT: hypothesis that a balance exists between serine proteases initiated to test this hypothesis neuronal migration. This hypothesis is supported by our data support the hypothesis that changes in enzymatic on migration, strengthens our hypothesis that this serine
```



```
grep -c "string" <filename>
```
Searches through the specified file and counts the number of lines in which "string" appears. -c is a flag that stands for "count" and the input string can be a word, phrase, or any expression. The output will be an integer representing the count of matching lines.
```
INPUT: $ grep -c “terrorism” chapter-6.txt
OUTPUT: 67

INPUT: $ grep -c “2001” chapter-9.txt
OUTPUT: 5
```



### Works Cited
“GREP Command in Unix/Linux.” GeeksforGeeks, GeeksforGeeks, 15 Nov. 2022, www.geeksforgeeks.org/grep-command-in-unixlinux/.

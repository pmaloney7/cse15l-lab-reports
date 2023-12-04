# Lab Report 5
1. Hello, I am trying to run the following code and am getting various different outputs than what I should be getting. I don't know what the failure-inducing output is, perhaps I should use an ArrayList instead of an array?
```
public class Bug {
    static int sumEvenIndices(int[] nums) {
        int sum = 0;
        for (int i=0; i<nums.length; i+=2) {
            sum+=nums[i+1];
        }
        return sum;
    }
}
```
2. TA RESPONSE: Hi Patrick, it looks like you are incrementing i by 2 every time your for loop runs. You are also summing sum with nums[i+1] which essentially means you are incrementing i by 3 every time your for loops runs. This could be why you received an error message for an input of [1], and would also explain why you received the wrong output for [2, 6].

3. Fixed Code:
```
public class Bug {
    static int sumEvenIndices(int[] nums) {
        int sum = 0;
        for (int i=0; i<nums.length; i+=2) {
            sum+=nums[i]; //changed i+1 to i as per TA response
        }
        return sum;
    }
}
```
Essentially, the bug was on line 5 of Bug.java. The value of nums[i+1] was being added to the variable sum, but in some cases either i+1 was out of bounds, or not the correct value to add to sum at all. The fixed code adds nums[i] to sum instead, which is both the correct value and in range every time.
![image](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/76cac845-db46-43b7-a092-d2d87ebdda60)

4.

File Strucutre:
```
-Lab5

  -lib
  
    -hamcrest-core-1.3.jar
    
    -junit-4.13.2.jar
    
  -Bug.class
  
  -Bug.java
  
  -Tester.class
  
  -Tester.java
  
  -test.sh
```
Contents of Bug.java:
```
public class Bug {
    static int sumEvenIndices(int[] nums) {
        int sum = 0;
        for (int i=0; i<nums.length; i+=2) {
            sum+=nums[i+1];
        }
        return sum;
    }
}
```
Contents of Tester.java:
```
import static org.junit.Assert.*;
import org.junit.*;

public class Tester {
    @Test
    public void tester1() {
        int[] a = new int[]{1};
        Bug example = new Bug();
        assertEquals(1, Bug.sumEvenIndices(a));
    }
    @Test
    public void tester2() {
        int[] b = new int[]{2, 6};
        Bug example = new Bug();
        assertEquals(2, Bug.sumEvenIndices(b));
    }
}
```
Contents of test.sh:
```
set -e
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore Tester
```

## Reflection
In the second half of this quarter, I learned how to implement my own test methods by using junit. Similar to what I did in this lab, one must create a test file with a method that compares an input with the expected output from the contents of the main file that is being tested. I also learned how to edit preexisting files from the terminal using vim, like what we did in skill demo 4 where we had to demonstrate that the unit tests failed, edit the test using vim and its various inputs, and then rerun the test to show that it now works after editing the file on the fly.

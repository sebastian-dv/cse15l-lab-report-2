# Part One
![Screenshot 2023-01-30 at 6 09 27 PM](https://user-images.githubusercontent.com/23327980/215642434-6d51328e-1dec-4e34-8462-75d69048eb67.jpg)
---
![Screenshot 2023-01-30 at 6 10 27 PM](https://user-images.githubusercontent.com/23327980/215642705-cc718199-a493-404c-beff-8954467bc2f6.jpg)
First, `handleRequest()` is called. The method then checks for the path and if it contains "/add-message". If it does, it splits the query at "=". Then it adds whats on the right of the equal sign to 'output', which is "Hello", and returns output. 
![Screenshot 2023-01-30 at 6 10 46 PM](https://user-images.githubusercontent.com/23327980/215642724-728e180b-a02c-4313-a721-6a8d15862739.jpg)
The same method as before is called, but this time since output contains the previous string that was added the server displays all of the previous strings added to output as well as the newest one, which in this case is "Done".
# Part Two
ArrayExamples Bugs
```
public void testReverseInPlace() {
    int[] input = { 3, 2, 1 };
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{ 1, 2, 3 }, input);
}
public void testReversed() {
    int[] input = { 3, 2, 1 };
    assertArrayEquals(new int[]{ 1, 2, 3 }, ArrayExamples.reversed(input));
}
```
# Part Three
One thing I learned from these past two labs was about the 'split()' method which can be used to split up strings at a certain character and put into an array.

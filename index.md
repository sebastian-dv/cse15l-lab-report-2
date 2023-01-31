# Part One
![Screenshot 2023-01-30 at 6 09 27 PM](https://user-images.githubusercontent.com/23327980/215642434-6d51328e-1dec-4e34-8462-75d69048eb67.jpg)
---
![Screenshot 2023-01-30 at 6 10 27 PM](https://user-images.githubusercontent.com/23327980/215642705-cc718199-a493-404c-beff-8954467bc2f6.jpg)
First, `handleRequest()` is called. The method then checks for the path and if it contains "/add-message". If it does, it splits the query at "=". Then it adds whats on the right of the equal sign to 'output', which is "Hello", and returns output. The url changes since I have added "add-message?s=Hello". Then the string output which starts off as an empty string gets "Hello" added to it as well as "\n" which will start a new line so that the next input in the url gets displayed below the previous output.
![Screenshot 2023-01-30 at 6 10 46 PM](https://user-images.githubusercontent.com/23327980/215642724-728e180b-a02c-4313-a721-6a8d15862739.jpg)
The same method as before is called, but this time since output contains the previous string that was added the server displays all of the previous strings added to output as well as the newest one, which in this case is "Done". This string gets added to output and is then displayed on the server below the previous output, "Hello". 
# Part Two: ArrayExamples Bugs
> Failure inducing test inputs
```
public void testReverseInPlace() {
    int[] input = { 3, 2, 1 };
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{ 1, 2, 3 }, input);
}
```
These inputs will cause a failure in the testing due to the bugs in the code.
> Broken code
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}
```
Even though the code contains bugs, there are inputs that will not result in a failure, which are:
```
public void testReverseInPlace() {
    int[] input = { 3 };
    ArrayExamples.reverseInPlace(input);
    assertArrayEquals(new int[]{ 3 }, input);
}
```
![Screenshot 2023-01-30 at 7 22 42 PM](https://user-images.githubusercontent.com/23327980/215654959-07baf277-072b-4f2b-a445-bba2a0ff1483.jpg)

Broken Code Before Fixing:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}
```
Code After Being Fixed:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
}
```
This fix addresses the issue because prior to the fix, the code would only copy the second half of the array to the first half, turning the array into a palindrome of integers. After the fix, the for loop only goes through half of the array, swapping the opposite integers with each other. Using a temp variable, I was able to keep the integer at one index after changing it to the value of the integer on the other side of the array. Then I assign the temp integer to the integer I did not alter, effectly swapping the vlaues of two opposite indices.

# Part Three
One thing I learned from these past two labs was about the 'split()' method which can be used to split up strings at a certain character and put into an array. I also learned that even if your code contains bugs, it could still pass some tests which could give you a false sense of success. This is why it's important to write multiple, well written tests that really try to push your code to failure rather than an easy test which will most likely pass regardless of how poor the code is.

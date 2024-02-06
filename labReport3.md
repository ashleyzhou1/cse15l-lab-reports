Ashley Zhou
Lab Report 3

Part 1

The program I am choosing is ArrayTests.java. 

Failure inducing input for `reverseInPlace()`:
```
int[] input2 = {1,2,3};
ArrayExamples.reverseInPlace(input2);
assertArrayEquals(new int[]{3,2,1}, input2);
```
Failure inducing input for `reversed()`:
```
int[] input2 = {1,2,3,4};
assertArrayEquals(new int[]{4,3,2,1}, ArrayExamples.reversed(input2));
```
Input that doesn't induce a failure for `reverseInPlace()`:
```
int[] input1 = { 3 };
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{ 3 }, input1);
```
Input that doesn't induce a failure for `reversed()`:
```
assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
```
The symptom: ![Image](3-1.png)

The bug
Before: 
```
  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
After:
```
// Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

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


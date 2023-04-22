Kirsten Bali

Lab Report: Bugs and Servers


Part 1: Web Server


Part 2: Bugs and Fixes

A failure inducing input for the method reversed():

    int[] input1 = {3, 2, 1};
    assertArrayEquals(new int[]{1, 2, 3}, ArrayExamples.reversed(input1));
    
An input that doesn't induce a failure for the method reversed():

    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
    
The symptom as the output of running the tests:


The before code of the method reversed(): 

static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }

The after code of the method reversed():

static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    int temp;
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }


Part 3: What I learned

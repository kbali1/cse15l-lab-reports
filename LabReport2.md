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
![Image](Lab3Part2.png)

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

Changing `arr[i] = newArray[arr.length-i-1]` to `newArray[i] = arr[arr.length-i-1]` and returning `arr` instead of `newArray` addresses the issue because the orginal code was origially returning an empty array. The array `newArray` orginially did not have any elements in it, so getting an element from `newArray` and initializing `arr[i]` to that element would actually mean the value is null. Initializing `newArray[i]` to `arr[arr.length-i-1]` means the first element in the empty array is set to the first element in the original array. The `newArray` that was originally empty becomes the reversed array of `arr`, so returning that array means the tests will pass.

Part 3: What I learned

I learned that every URL has a port, and it can be any number that has not been taken already. My partner and I tried to use 6025 but could not figure out why our website would not load. We found out that it was because that number was taken already, so we changed it to 4739. Changing our port allowed our website to load. It was interesting to see how a unique port is essential to deploying a web server.

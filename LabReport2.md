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
    


Part 3: What I learned

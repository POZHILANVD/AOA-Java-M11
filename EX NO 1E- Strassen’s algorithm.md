
# EX 1E Integer Multiplication using Divide and Conquer Approach(Strassen’s algorithm).
## DATE:

## AIM:
To write a Java program to for given constraints.
You are given two square matrices A and B of size n × n (where n is a power of 2). Your task is to compute their matrix product using Strassen’s Matrix Multiplication algorithm and return the resulting matrix.

Unlike traditional matrix multiplication which takes O(n3)O(n^3)O(n3) time, Strassen’s algorithm improves this by reducing the number of recursive multiplications from 8 to 7, achieving approximately O(n2.81)O(n^{2.81})O(n2.81) complexity.

## Algorithm

1.Start the program. Read the size n (power of 2) and input two n × n matrices A and B.

2.Divide each matrix into four submatrices: A11, A12, A21, A22 and B11, B12, B21, B22, each of size (n/2) × (n/2).

3.Compute seven intermediate products (M1 to M7) using Strassen’s formulas:

M1 = (A11 + A22) × (B11 + B22) M2 = (A21 + A22) × B11 M3 = A11 × (B12 - B22) M4 = A22 × (B21 - B11) M5 = (A11 + A12) × B22 M6 = (A21 - A11) × (B11 + B12) M7 = (A12 - A22) × (B21 + B22)

4.Combine the results to form the resulting submatrices:

C11 = M1 + M4 - M5 + M7
C12 = M3 + M5
C21 = M2 + M4
C22 = M1 + M3 - M2 + M6

Then merge C11, C12, C21, C22 to get the final matrix C.

5.Display the resultant matrix C as the product of A and B, and stop the program.

## Program:
```
/*
Program to implement Reverse a String
Developed by: POZHILAN V D
Register Number: 212223240118
*/

import java.util.Scanner;

public class StrassenMatrix {
    // Add two matrices
    static int[][] add(int[][] A, int[][] B) {
        int n = A.length;
        int[][] C = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                C[i][j] = A[i][j] + B[i][j];
        return C;
    }

    // Subtract matrix B from A
    static int[][] subtract(int[][] A, int[][] B) {
        int n = A.length;
        int[][] C = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                C[i][j] = A[i][j] - B[i][j];
        return C;
    }

    // Strassen recursive multiplication
    static int[][] strassen(int[][] A, int[][] B) {
        //Type code here...


                B12[i][j] = B[i][j+mid];
                B21[i][j] = B[i+mid][j];
                B22[i][j] = B[i+mid][j+mid];
            }
        }
                
            int[][] M1 =strassen(add(A11,A22),add(B11,B22));
            int[][] M2 =strassen(add(A21,A22),B11);
            int[][] M3 =strassen(A11,subtract(B12,B22));
            int[][] M4 =strassen(A22,subtract(B21,B11));
            int[][] M5 =strassen(add(A11,A12),B22);
            int[][] M6 =strassen(subtract(A21,A11),add(B11,B12));
            int[][] M7 =strassen(subtract(A12,A22),add(B21,B22));
            int[][] C11 = add(subtract(add(M1,M4),M5),M7);
            int[][] C12 = add(M3,M5);
            int[][] C21 = add(M2,M4);
            int[][] C22 = add(subtract(add(M1,M3),M2),M6);
            for (int i=0; i<mid;i++){
                for (int j=0;j<mid;j++) {
                    C[i][j] = C11[i][j];
                    C[i][j+mid] = C12[i][j];
                    C[i+mid][j] = C21[i][j];
                    C[i+mid][j+mid] = C22[i][j];
                }
            }
        
                return C;
            }
    // Function to print matrix
    static void printMatrix(int[][] matrix) {
        for (int[] row : matrix) {
            for (int val : row)
                System.out.print(val + " ");
            System.out.println();
        }
    }

    // Main method to get input and run Strassen multiplication
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Read size of matrix
        //System.out.print("Enter matrix size (power of 2): ");
        int n = sc.nextInt();

        int[][] A = new int[n][n];
        int[][] B = new int[n][n];

        // Input Matrix A
        //System.out.println("Enter elements of matrix A:");
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                A[i][j] = sc.nextInt();

        // Input Matrix B
        //System.out.println("Enter elements of matrix B:");
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                B[i][j] = sc.nextInt();

        // Multiply using Strassen
        int[][] result = strassen(A, B);

        // Output the result matrix
        System.out.println("Result of Strassen Matrix Multiplication:");
        printMatrix(result);
    }
}
```

## Output:

<img width="477" height="446" alt="image" src="https://github.com/user-attachments/assets/53f532fb-3c8b-4367-9cce-3b810c0357a3" />


## Result:
The program successfully implemented and the expected output is verified.



5.Display the computed median and stop the program.  

## Program:
```
/*
Program to implement Reverse a String
Developed by: POZHILAN V D
Register Number: 212223240118
*/

import java.util.Scanner;
public class Solution {
    private int p1 = 0, p2 = 0;
    // Get the smaller value between nums1[p1] and nums2[p2], and move the pointer forward
    private int getMin(int[] nums1, int[] nums2) {
        if (p1 < nums1.length && p2 < nums2.length) {
            return nums1[p1] < nums2[p2] ? nums1[p1++] : nums2[p2++];
        } else if (p1 < nums1.length) {
            return nums1[p1++];
        } else if (p2 < nums2.length) {
            return nums2[p2++];
        }
        return -1; // Should not reach here if input is valid
    }
    // Main logic to find median of two sorted arrays
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
       int m=nums1.length,n=nums2.length;
       if((m+n)%2==0){
           for(int i=0;i<(m+n)/2-1;++i){
               int tmp=getMin(nums1,nums2);
           }
           return (double) (getMin(nums1,nums2)+getMin(nums1,nums2))/2;
       }
       else{
           for(int i=0;i<(m+n)/2;++i){
               int tmp=getMin(nums1,nums2);
           }
           return getMin(nums1,nums2);
       }
    }
    // Main method with user input
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        // Input for nums1
        //System.out.print("Enter size of first sorted array: ");
        int m = sc.nextInt();
        int[] nums1 = new int[m];
        //System.out.println("Enter " + m + " sorted integers for first array:");
        for (int i = 0; i < m; i++) {
            nums1[i] = sc.nextInt();
        }
        // Input for nums2
        //System.out.print("Enter size of second sorted array: ");
        int n = sc.nextInt();
        int[] nums2 = new int[n];
        //System.out.println("Enter " + n + " sorted integers for second array:");
        for (int i = 0; i < n; i++) {
            nums2[i] = sc.nextInt();
        }

        // Find and display the median
        double median = sol.findMedianSortedArrays(nums1, nums2);
        System.out.println("Median of the two sorted arrays = " + median);
        
        sc.close();
    }
}

```

## Output:

<img width="874" height="323" alt="image" src="https://github.com/user-attachments/assets/1e73d8b1-abfe-459f-b6a3-b44d41850f78" />

## Result:
The program successfully implemented and the expected output is verified.

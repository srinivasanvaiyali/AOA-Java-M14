
# EX 4E Longest Increasing Subsequence - Dynamic Programming.
## DATE:
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.
Example 1:
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
## Algorithm
1.Input Reading: Read the number of elements n and the array nums[] containing integers.

2.Initialization: Create an array dp[] of size n and initialize all values to 1 (each element is an LIS of length 1 by itself).

3.Dynamic Programming Update: For each element nums[i] (from index 1 to n-1), compare it with all previous elements nums[j] (where 0 ≤ j < i). If nums[i] > nums[j], then update dp[i] = max(dp[i], dp[j] + 1).

4.Find Maximum Length: After filling the dp[] array, the length of the longest increasing subsequence is the maximum value in dp[].

5.Output: Print the maximum LIS length as the final result.  

## Program:
```
Program to implement Reverse a String
Developed by: SRINIVASAN V
Register Number:  212222043008
```
```
import java.util.*;

public class LongestIncreasingSubsequence {

    public static int lengthOfLIS(int[] nums) {
        int[] dp=new int[nums.length];
        Arrays.fill(dp,1);
        for(int i=1;i<nums.length;i++){
            for(int j=0;j<i;j++){
                if(nums[i]>nums[j]){
                    dp[i]=Math.max(dp[i],dp[j]+1);
                }
            }
        }
        int longest=0;
        for(int c:dp){
            longest=Math.max(longest,c);
        }
        return longest;
        
        
        // Type Your Code here...!
    }

public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt user input
        int n = scanner.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }

        // Calculate and display the length of LIS
        int result = lengthOfLIS(nums);
        System.out.println("Length of Longest Increasing Subsequence: " + result);

        scanner.close();
    }
}
```

## Output:

<img width="1120" height="241" alt="512237807-1629107c-406e-436d-85c9-549220cdc74a" src="https://github.com/user-attachments/assets/84353193-b96a-4727-b34b-8f76a37bd749" />


## Result:
The program successfully implemented and the expected output is verified.


# EX 4E Longest Increasing Subsequence - Dynamic Programming.
## DATE: 15.09.2026
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.
Example 1:
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
## Algorithm
1. Start and create a DP array dp[], initializing every value to 1.
2. For each element nums[i], compare it with all previous elements nums[j].
3. If nums[j] < nums[i], update dp[i] = max(dp[i], dp[j] + 1).
4. Keep track of the maximum value in dp[] as maxLen.
5. Return maxLen as the length of the Longest Increasing Subsequence.

## Program:
```
/*
Program to implement Reverse a String
Developed by: TIMMAPURAM YOGEESWAR
Register Number:  212223230233
*/
import java.util.*;

public class LongestIncreasingSubsequence {

    public static int lengthOfLIS(int[] nums) {
        
        
        // Type Your Code here...!
        int n = nums.length;
        
        int[] dp = new int[n];
        int maxLen = 1;
        
        Arrays.fill(dp,1);
        
        for(int i = 1;i<n;i++){
            for(int j = 0;j<i;j++){
                if(nums[j] < nums[i]){
                    dp[i] = Math.max(dp[i],dp[j] + 1);
                }
            }
           maxLen = Math.max(maxLen,dp[i]); 
        }
        return maxLen;
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

<img width="1108" height="235" alt="image" src="https://github.com/user-attachments/assets/51b91dc3-134e-42ee-9cd2-279e7f23c3b5" />



## Result:
The program successfully implemented and the expected output is verified.

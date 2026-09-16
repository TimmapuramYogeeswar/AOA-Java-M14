
# EX 4D Longest Common SubSequence - Dynamic Programming.
## DATE: 15.09.2026
## AIM:
To write a Java program to for given constraints.
Given two strings text1 and text2, return the length of their longest common subsequence. If there is no common subsequence, return 0.
A subsequence of a string is a new string generated from the original string with some characters (can be none) deleted without changing the relative order of the remaining characters.

For example, "ace" is a subsequence of "abcde".
A common subsequence of two strings is a subsequence that is common to both strings.

Input: text1 = "abcde", text2 = "ace" 
Output: 3  
Explanation: The longest common subsequence is "ace" and its length is 3.
Constraints:

1 <= text1.length, text2.length <= 1000
text1 and text2 consist of only lowercase English characters.

## Algorithm
1. Start and create a DP table of size (text1.length + 1) × (text2.length + 1).
2. Traverse both strings from right to left.
3. If the characters are equal, set dp[row][col] = 1 + dp[row+1][col+1].
4. If they are different, take the maximum of dp[row+1][col] and dp[row][col+1].
5. Return dp[0][0] as the length of the Longest Common Subsequence.

## Program:
```
/*
Program to implement Reverse a String
Developed by: TIMMAPURAM YOGEESWAR
Register Number:  212223230233
*/
import java.util.Scanner;

public class Solution {
  public int longestCommonSubsequence(String text1, String text2) {    
    //bottom-up approach
    //ADD YOUR CODE HERE
    int[][] dpGrid=new int[text1.length()+1][text2.length()+1];
    for(int col=text2.length()-1;col>=0;col--){
        for(int row=text1.length()-1;row>=0;row--){
            if(text1.charAt(row)==text2.charAt(col)){
                dpGrid[row][col]=1+dpGrid[row+1][col+1];
            }else{
                dpGrid[row][col]=Math.max(dpGrid[row+1][col],dpGrid[row][col+1]);
            }
        }
    }
    return dpGrid[0][0];
  }

    // Main method for input and output
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        String text1 = sc.nextLine().replaceAll("\"", "");
        String text2 = sc.nextLine().replaceAll("\"", "");

        int lcsLength = sol.longestCommonSubsequence(text1, text2);
        System.out.println("Length of Longest Common Subsequence: " + lcsLength);

        sc.close();
    }
}

```

## Output:

<img width="850" height="217" alt="image" src="https://github.com/user-attachments/assets/deb0cc68-7897-4d3a-80c3-09ca3c38c333" />



## Result:
The program successfully implemented and the expected output is verified.

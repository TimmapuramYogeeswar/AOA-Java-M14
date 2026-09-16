
# EX 4C Coin Change Problem - Dynamic Programming.
## DATE:15.09.2026
## AIM:
To write a Java program to for given constraints.
You are given an integer array coins representing coins of different denominations and an integer amount representing a total amount of money.

Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

You may assume that you have an infinite number of each kind of coin.

## Algorithm
1. Start and create a DP array dp of size amount + 1, initialized with a large value.
2. Set dp[0] = 0, since zero coins are needed to make amount 0.
3. For every amount from 1 to amount, check each available coin.
4. If the coin can be used, update dp[i] = min(dp[i], dp[i-coin] + 1).
5. Return dp[amount] if possible; otherwise return -1.

## Program:
```
/*
Program to implement Reverse a String
Developed by: TIMMAPURAM YOGEESWAR
Register Number:  212223230233
*/
import java.util.*;

public class Solution {
    public int coinChange(int[] coins, int amount) {
        //ADD YOUR CODE HERE
        int[] dp = new int[amount + 1];

    Arrays.fill(dp, amount + 1);

    dp[0] = 0;

    for (int i = 1; i <= amount; i++) {

        for (int coin : coins) {

            if (coin <= i) {
                dp[i] = Math.min(
                    dp[i],
                    dp[i - coin] + 1
                );
            }
        }
    }

    return dp[amount] > amount ? -1 : dp[amount];
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Solution solution = new Solution();
        String coinsLine = scanner.nextLine(); 
        String amountLine = scanner.nextLine();
        coinsLine = coinsLine.replaceAll("[^0-9,]", ""); 
        String[] coinsStr = coinsLine.split(",");
        int[] coins = new int[coinsStr.length];
        for (int i = 0; i < coinsStr.length; i++) {
            coins[i] = Integer.parseInt(coinsStr[i]);
        }
        int amount = Integer.parseInt(amountLine.replaceAll("[^0-9]", ""));
        int result = solution.coinChange(coins, amount);
        System.out.println(result);

        scanner.close();
    }
}

```

## Output:

<img width="372" height="231" alt="image" src="https://github.com/user-attachments/assets/0794e14e-a197-4f3e-9556-3f8a9280414f" />



## Result:
The program successfully implemented and the expected output is verified.

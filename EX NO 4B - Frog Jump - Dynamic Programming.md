
# EX 4B Frog Jump - Dynamic Programming.
## DATE: 15.09.2026
## AIM:
To write a Java program to for given constraints.
A Frog Jump 1 or 2 steps at a time.
Problem Statement:

A frog is at the bottom of the stairs with n steps. It can jump either 1 or 2 steps at a time. Write a program to find the number of distinct ways the frog can reach the top (n-th step).

Input Format:

A single integer n (1 ≤ n ≤ 45) – number of steps.
 Output Format:

A single integer – number of distinct ways to reach step n.

## Algorithm
1. Start and take the number of stairs n as input.
2. If n ≤ 2, return n as the number of possible ways.
3. Initialize prev2 = 1 and prev1 = 2 for the first two stairs.
4. For each stair from 3 to n, calculate current = prev1 + prev2 and update the previous values.
5. Return prev1 as the total number of ways to reach the nth stair.

## Program:
```
/*
Program to implement Reverse a String
Developed by: TIMMAPURAM YOGEESWAR
Register Number:  212223230233
*/
import java.util.Scanner;

public class FrogJump {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
       
        int n = scanner.nextInt();
        scanner.close();

        System.out.println(countWays(n));
    }

   
    public static int countWays(int n) {
       //Type your code here
       if (n <= 2) {
        return n;
    }

    int prev2 = 1;
    int prev1 = 2;

    for (int i = 3; i <= n; i++) {
        int current = prev1 + prev2;
        prev2 = prev1;
        prev1 = current;
    }

    return prev1;
       
    }
}

```

## Output:

<img width="316" height="176" alt="image" src="https://github.com/user-attachments/assets/52526634-82f0-448e-8329-f50fd26dbac8" />



## Result:
The program successfully implemented and the expected output is verified.

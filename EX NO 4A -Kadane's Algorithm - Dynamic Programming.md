
# EX 4A Kadane's Algorithm - Dynamic Programming. 
## DATE: 15.09.2026
## AIM:
To Write a Java program to solve the below problem using Kadane's Algorithm.
A solar company installs solar panels around a circular grid of n buildings. Each building either generates or consumes net energy, represented by integers (+ve for generated, -ve for consumed).

The company wants to find a contiguous sequence of buildings (possibly wrapping around from the end to the beginning) that maximizes the total net energy.

Write a program to compute the maximum net energy that can be collected from any contiguous block of buildings on the circular grid.

Input Format:
First line: Integer n (number of buildings)

Second line: n space-separated integers: net energy for each building

Output Format:
A single integer: Maximum net energy collectable from a contiguous block (wrapping allowed)

Constraints:
1 <= n <= 10^6
## Algorithm
1. Start and calculate the total sum of the array while finding the maximum subarray sum using Kadane’s algorithm.
2. At the same time, find the minimum subarray sum using Kadane’s algorithm.
3. Calculate the circular sum as total − minSum, which represents the maximum sum wrapping around the array.
4. If all elements are negative, return the maximum subarray sum instead of the circular sum.
5. Return the maximum of maxSum and total − minSum as the maximum circular energy.

## Program:
```
/*
Program to implement Reverse a String
Developed by: TIMMAPURAM YOGEESWAR
Register Number:  212223230233
*/
import java.util.*;

public class SolarEnergyMaximizer {

    public static int maxCircularEnergy(int[] energy)     {
        //Type your code
        int total = 0;
    int maxSum = energy[0], currentMax = energy[0];
    int minSum = energy[0], currentMin = energy[0];

    for (int i = 0; i < energy.length; i++) {
        total += energy[i];

        if (i > 0) {
            currentMax = Math.max(energy[i], currentMax + energy[i]);
            maxSum = Math.max(maxSum, currentMax);

            currentMin = Math.min(energy[i], currentMin + energy[i]);
            minSum = Math.min(minSum, currentMin);
        }
    }

    if (maxSum < 0) {
        return maxSum;
    }

    return Math.max(maxSum, total - minSum);
    }

    
    

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] energy = new int[n];
        for (int i = 0; i < n; i++) {
            energy[i] = sc.nextInt();
        }
        System.out.println(maxCircularEnergy(energy));
    }
}

```

## Output:
<img width="382" height="212" alt="image" src="https://github.com/user-attachments/assets/94f2d653-238f-44de-8c3f-5131aba1d305" />



## Result:
The program successfully Implemented and the output is verified. 

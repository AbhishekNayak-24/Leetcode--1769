# Leetcode--1769
Minimum  Number Of Operations To Move All Balls to Each Box
// code in java
public class Solution {
    public int[] minOperations(String boxes) {
        int n = boxes.length();
        int[] answer = new int[n];
        
        // Left to right pass
        int count = 0, operations = 0;
        for (int i = 0; i < n; i++) {
            answer[i] = operations;
            count += boxes.charAt(i) - '0';
            operations += count;
        }
        
        // Right to left pass
        count = 0;
        operations = 0;
        for (int i = n - 1; i >= 0; i--) {
            answer[i] += operations;
            count += boxes.charAt(i) - '0';
            operations += count;
        }
        
        return answer;
    }
}


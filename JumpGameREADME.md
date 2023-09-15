# leet-day63

# Problem Description

You are given an integer array `nums`. You are initially positioned at the array's first index, and each element in the array represents your maximum jump length at that position.

The task is to determine whether you can reach the last index of the array or not. In other words, you need to check if there exists a sequence of jumps starting from the first index and ending at the last index, such that you can jump to each index within the jump range defined by the value at that index.

Consequently, you need to return `true` if it's possible to reach the last index, and `false` otherwise.

## Example

```
Input: nums = [2,3,1,1,4]
Output: true
Explanation: You can jump 1 step from index 0 to 1, then 3 steps to the last index.

Input: nums = [3,2,1,0,4]
Output: false
Explanation: You will always arrive at index 3 no matter what. Its maximum jump length is 0, which makes it impossible to reach the last index.
```

# Approach

The problem can be efficiently solved using a greedy approach. The key idea is to keep track of the farthest position you can reach from each index. While iterating through the array, you update this farthest reachable position, and if at any point, you reach a position that is not reachable (i.e., the current index is greater than the farthest position you can reach), you know it's impossible to reach the end, and you return `false`. If you successfully reach the end, you return `true`.

Here's the step-by-step algorithm:
1. Initialize a variable `farthest` to 0. This variable represents the farthest position you can reach from the current index.
2. Iterate through the array from left to right, from index 0 to the last index:
   - If the current index is greater than `farthest`, return `false` because you can't reach this index.
   - Update `farthest` as the maximum of its current value and the sum of the current index and the value at that index (`farthest = max(farthest, i + nums[i])`).
   - If `farthest` is greater than or equal to the last index, return `true` because you can reach the end.
3. If the loop completes without returning `true`, return `true` as it means you can reach the end.

# Complexity Analysis

The time complexity for this solution is O(n), where n is the length of the `nums` array, as you iterate through the array only once. The space complexity is O(1) because you use a constant amount of extra space.

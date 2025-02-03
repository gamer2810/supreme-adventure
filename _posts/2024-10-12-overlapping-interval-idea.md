---
title: Overlapping Interval Idea
date: October 12, 2024 12:53 AM
categories: LeetCode
tags:
  - algorithm
  - leetcode
description: "Solving LeetCode problem 2406: Divide Intervals Into Minimum Number of Groups"
comments: true
---

Example problem
https://leetcode.com/problems/divide-intervals-into-minimum-number-of-groups/description/

Approach

To find out how many intervals are overlapping on a position, we can follow the following steps:

\- Create an array with size \[minRange, maxRange]

\- For each interval \[a,b]:

- Add one to array\[a]: Signaling a new interval starts at this position
- Minus one to array\[b+1]: Signaling an interval ended at this position

\- Then we can use prefix sum on the array to find out how many intervals are overlapping.

For this particular problem, we just need to find the max value of the prefix sum found above.

Code:

```java
class Solution {

    public int minGroups(int[][] intervals) {
        if(intervals.length == 1) {
            return 1;
        }
        // sort
        int[] count = new int[1000005];
        int intervalMax = 0;
        int max = 0;
        for(int i = 0; i < intervals.length; i++) {
            count[intervals[i][0]]++;
            count[intervals[i][1]+1]--;
            if(intervalMax < intervals[i][1]) {
                intervalMax = intervals[i][1];
            }
        }

        int prefix = 0;
        for(int i = 0; i < intervalMax; i++){
            prefix += count[i];
            if(prefix > max) {
                max = prefix;
            }
        }

        return max;
    }
}
```

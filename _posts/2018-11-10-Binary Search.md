---
layout:     post
title:      Binary Search
subtitle:   二分法
date:       2018-11-10
author:     HY
header-img: img/post-bg-desk.jpg
catalog: true
tags:
    - 算法
    
---

>九章算法班 第二节：Binary Search

# time complexity O(log n), space complexity O(1)

# 二分法模板四要素
    1.start + 1 < end
    2.start + (end – start) / 2
    3.A[mid] ==, <, >
    4.A[start] A[end] ? target

# Lintcode 14. First Position of Target
#### For a given sorted array (ascending order) and a target number, find the first index of this number in O(log n) time complexity. If the target number does not exist in the array, return -1.
    class Solution:
    """
    @param nums: The integer array.
    @param target: Target to find.
    @return: The first position of target. Position starts from 0.
    """
    def binarySearch(self, nums, target):
        if not nums:
            return -1
    
        start, end = 0, len(nums) - 1
        while start + 1 < end:
            mid = start + (end - start) // 2
            if nums[mid] < target:      ***
                start = mid
            else:
                end = mid
    
        if nums[start] == target:   #find first 就先判断start
            return start
        elif nums[end] == target:
            return end
        return -1
       
# Lintcode 458. Last Position of Target
#### Find the last position of a target number in a sorted array. Return -1 if target does not exist.
    class Solution:
    """
    @param nums: An integer array sorted in ascending order
    @param target: An integer
    @return: An integer
    """
    def lastPosition(self, nums, target):
        if not nums:
            return -1
        
        start = 0; end = len(nums) - 1
        while start + 1 < end:
            mid = start + (end - start) // 2
            if nums[mid] <= target:     ***
                start = mid
            else:
                end = mid
        
        if nums[end] == target:     #find last 就先判断end
            return end
        elif nums[start] == target:
            return start
        return -1
        
        

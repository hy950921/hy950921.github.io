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

# O(logn) time complexity

# 二分法模板四要素
    1.start + 1 < end
    2.start + (end – start) / 2
    3.A[mid] ==,
    4.A[start] A[end] ? target

# Lintcode 14. First Position of Target 
#### For a given sorted array (ascending order) and a target number, find the first index of this number in O(log n) time complexity. If the target number does not exist in the array, return -1.
    def binarySearch(self, nums, target):
        if not nums:
            return -1

        start, end = 0, len(nums) - 1
        while start + 1 < end:
            mid = start + (end - start) // 2
            if nums[mid] >= target:
                end = mid
            else:
                start = mid

        if nums[start] == target:
            return start
        elif nums[end] == target:
            return end
        return -1

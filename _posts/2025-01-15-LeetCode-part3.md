---
layout: post
title: LeetCode Adventures Part 3
date: 2025-01-15
tags: [leetcode]
---

## My LeetCode journey part 3

I have completed a few more exercises from NeetCodes listed problems - almost complete with the first item, which is Arrays and HashMaps.

What I can say for certain is that this has had the effect of making me more efficient in my ability to think through the problem, and I can see why this is needed, since while most programmers wants to be always satisfied, the act of leetcode dragging them kicking and screaming by the collar, so to speak. I think is beneficial. I'll expound on my thought in a later date, however I am enjoying my time so far.

# Group Anagrams - `Medium`

Difficulty: Medium
Hint: Use a HashMap to store the character frequencies as the key by using a tuple to store the same char frequencies i.e. anagrams. once stored return the value list from the key value pair in the HashMap
Status: Done
Try again: Not started

```python
class Solution(object):
    def groupAnagrams(self, strs):
        """
        :type strs: List[str]
        :rtype: List[List[str]]
        """

        freq = {}

        for word in strs:
            values = [0] * 26
            for char in word:
                values[ord(char) - 97] += 1

            temp = tuple(values)
            if temp not in freq:
                freq[temp] = [word]
            else: 
                freq[temp].append(word)
        

        return freq.values()
```

## Why this works - time space complexity

The time complexity of this algorithm is O(n), since we only need to iterate over the `strs` once as we save each char in the HashMap via their character frequency.

The space complexity for this algorithm would be O(n) as well, since we need to allocate extra memory that is equal to the length of `n`

# Top K frequent elements

Difficulty: Medium
Hint: Use a hashmap to store the frequency of the number, sort and return the element up to K
Space Complexity: O(n)
Status: Done
Time Complexity: O(2*n)
Try again: Not started

Solution:

```python
class Solution(object):
    def topKFrequent(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: List[int]
        """
        
        dictionary = {}

        final = []

        for i in range(0, len(nums)):
            if nums[i] not in dictionary:
                dictionary[nums[i]] = 1
            else:
                dictionary[nums[i]] += 1
 
        sorted_dict = sorted(dictionary.items(), key=lambda item: item[1], reverse=True)

        for n in sorted_dict[:k]:
            final.append(n[0])

        return final

```

**Why this works** - time and space complexity

Initially iterating over the `nums` arr to get the number frequency, sort the dictionary by value of the key and then return the keys up to K. This will be around O(2*n +k), but this will simplify to O(N) since I don’t do nested iterations.

Space complexity is going to be O(N + K) since we will store the final output in an array the length of K and a HashMap to the atleast the length of N.

# Product of Array Except Self

Difficulty: Medium
Hint: Prefix and suffix, can use multiple sequential iteration statements
Status: Done

**Solution**

```python
class Solution(object):
    def productExceptSelf(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        
        res = [1] * len(nums)
        
        prefix = 1
        for i in range(1, len(nums)):
            prefix *= nums[i - 1]
            res[i] = prefix

        postfix = 1
        for i in range(len(nums) - 1, -1, -1):
            res[i] *= postfix
            postfix *= nums[i]

        return res
```

**Why this works** - Time and space complexity 

Since the response array doesn’t count towards the space complexity, the space complexity will remain at `O(1)` since we only use the array that’s passed in via the parameters. For us to get the sum of products we will need to iterate of the `nums` array first, using a variable `prefix` this starts from “technically” index -1 and holds a 1 in order to neutralise the prefix information, imagine `arr[-1] == 1` so to speak, this will then get used to multiply the prefix value with the `nums[i - 1]` value as we start from index 1 (second element in the array).

Once that is complete we then us a postfix with a similar idea, just starting from the back and multiplying the postfix by the `nums[i]`  and then multiply the response array `res[i]` element with the postfix.

> I HATE THIS ONE SO MUCH - Me

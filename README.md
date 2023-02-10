# Find-First-and-Last-Position-of-Element-in-Sorted-Array
Find First and Last Position of Element in Sorted Array - two approaches

There is an analysis with two approaches, one is interactive method and the other is recursive method.  It is found that the interactive method is faster than the recursive method

The challenge is as follows:

Given an array of integers nums sorted in non-decreasing order, find the starting and ending position of a given target value.

If target is not found in the array, return [-1, -1].

You must write an algorithm with O(log n) runtime complexity.

 

Example 1:

Input: nums = [5,7,7,8,8,10], target = 8
Output: [3,4]
Example 2:

Input: nums = [5,7,7,8,8,10], target = 6
Output: [-1,-1]
Example 3:

Input: nums = [], target = 0
Output: [-1,-1]
 

Constraints:

0 <= nums.length <= 105
-109 <= nums[i] <= 109
nums is a non-decreasing array.
-109 <= target <= 109

APPROACH 1 iterative method

1. The code starts with the definition of the main function named "searchRange". This function takes two parameters - a list of integers named "nums" and an integer "target". This function returns a list of two integers, which will contain the starting and ending position of the target in the array.

2. The "searchRange" function calls two helper functions - "search_left" and "search_right" - to find the left and right boundaries of the target in the array, respectively.

3. The "search_left" function takes two parameters - the list of integers "nums" and the target integer. This function returns the left boundary of the target in the array.

4. Inside the "search_left" function, two variables "l" and "r" are defined. These two variables are used as the left and right pointers in the binary search algorithm. Initially, "l" is set to 0 and "r" is set to the length of the "nums" list minus 1.

5. The binary search algorithm starts with a while loop. The loop continues as long as "l" is less than or equal to "r".

6. In each iteration of the loop, a variable "m" is defined as the middle value of "l" and "r".

7. If the value at index "m" in the "nums" list is greater than or equal to the target, "r" is updated to "m - 1". Otherwise, "l" is updated to "m + 1".

8. The loop continues until "l" is greater than "r". The final value of "l" is returned as the left boundary of the target in the array.

9. The "search_right" function works similarly to the "search_left" function. The only difference is that the "r" pointer is updated to "m - 1" if the value at index "m" is less than or equal to the target, and "l" is updated to "m + 1" if the value at index "m" is greater than the target.

10. After finding the left and right boundaries of the target in the array, the code checks if the target was found in the array. If the target was not found, the function returns [-1, -1]. Otherwise, the function returns the list [l, r], which contains the starting and ending position of the target in the array.

The code for iterative method(approach 1) is here[code1]

APPROACH 2: RECURSIVE METHOD

1. The function searchRange takes in two arguments - nums, an array of integers, and target, the value we're trying to find the starting and ending positions of in nums.

2. Inside the searchRange function, two helper functions are defined - search_left and search_right. These functions are used to find the starting and ending positions, respectively, of target in nums.

3. The search_left function takes in four arguments - nums, target, l, and r. l and r represent the left and right boundaries of the search space.

4. Inside the search_left function, a base case is defined - if l is greater than r, the function returns l.

5. A variable m is defined as the average of l and r. This is used to determine which half of the search space to continue searching in.

6. If nums[m] is greater than or equal to target, the function returns a recursive call to search_left with r set to m - 1. This narrows the search space to the left half, as nums[m] is greater than target.

7. If nums[m] is less than target, the function returns a recursive call to search_left with l set to m + 1. This narrows the search space to the right half, as nums[m] is less than target.

8. The search_right function is similar to search_left, with the only difference being that it returns r when l is greater than r, and it returns a recursive call to search_right with l set to m + 1 if nums[m] is less than or equal to target. If nums[m] is greater than target, the function returns a recursive call to search_right with r set to m - 1.

9. In the searchRange function, a variable l is defined as the result of search_left(nums, target, 0, len(nums) - 1).

10. If l is equal to len(nums) or nums[l] is not equal to target, the function returns [-1, -1] as target was not found in nums.

11. If nums[l] is equal to target, a variable r is defined as the result of search_right(nums, target, 0, len(nums) - 1). The function then returns [l, r] as the starting and ending positions of target in nums.

On 1 millon iterators, the iterative method(approach 1) took 8.46 seconds and the recursive method (approach 2) took 13.22 seconds.  

The code for recursive method is [here](code2)

The conclusion is that the iterative method is faster than the recursive method.





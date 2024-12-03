# 160_GFG_Day1
Given an array of positive integers arr[], return the second largest element from the array. If the second largest element doesn't exist, return -1.  Note: The second largest element should not be equal to the largest element.
🎯 My Approach:
1.Tracking Largest and Second Largest:
Initialize two variables, first and second, to the smallest possible values.
Traverse through the array:
If the current element is greater than first, update second to first, and then set first to the current element.
If the current element is less than first but greater than second, update second.
If no valid second largest element is found, return -1.
2.Edge Cases:
If all elements are the same, return -1.
If the array has only two distinct elements, return the smaller of the two if it’s not equal to the largest.
Code (Python)
class Solution:
    def getSecondLargest(self, arr):
        first = float('-inf')
        second = float('-inf')

        for num in arr:
            if num > first:
                second = first
                first = num
            elif num > second and num < first:
                second = num

        return -1 if second == float('-inf') else second

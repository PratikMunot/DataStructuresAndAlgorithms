# Binary Search Algorithm

Binary Search Algorithm uses Divide and Conquer strategy to find the search the element in an array. In order to search an element in array the primary conditon is array needs to be sorted in Binary search.
In this algorithm we first identify the mid and using that mid we compare it with target. If the arr[mid] is less than the target than the target then second half of array is searched again and if arr[mid] is greater then the target then first half of array is sorted. This process is repeated until arr[mid] is equal to the target and if not then we return -1.

#### Time Complexity: O(logn). Space Complexity: O(1) [for iterative algorithm].
```
def binary_search(arr, target):
    left = 0  # Initialize the left pointer at the beginning of the array
    right = len(arr) - 1  # Initialize the right pointer at the end of the array

    while left <= right:
        mid = (left + right) // 2  # Find the middle index of the current search range

        if arr[mid] == target:
            return mid  # Found the target, return its index
        elif arr[mid] < target:
            left = mid + 1  # Target is in the right half, adjust the left pointer
        else:
            right = mid - 1  # Target is in the left half, adjust the right pointer

    return -1  # Target is not in the array, return -1

# Example usage:
my_list = [11, 12, 22, 25, 64]
target = 22
result = binary_search(my_list, target)

if result != -1:
    print(f"Element {target} found at index {result}.")
else:
    print(f"Element {target} not found in the array.")

```

Explanation of each step:

left = 0 and right = len(arr) - 1: We initialize two pointers, left and right, which represent the current search range within the array. left starts at the beginning of the array (index 0), and right starts at the end of the array (index len(arr) - 1).

We enter a while loop that continues as long as the left pointer is less than or equal to the right pointer. This loop is the essence of binary search and iteratively narrows down the search range.

mid = (left + right) // 2: We calculate the middle index, mid, of the current search range by averaging the left and right pointers.

We compare the element at the mid index with the target value:

If they are equal (arr[mid] == target), we have found the target element, and we return its index (mid).
If the element at mid is less than the target value (arr[mid] < target), we know that the target is in the right half of the current search range. Therefore, we adjust the left pointer to mid + 1.
If the element at mid is greater than the target value (arr[mid] > target), we know that the target is in the left half of the current search range. Therefore, we adjust the right pointer to mid - 1.
We continue the loop until either we find the target element or the left pointer becomes greater than the right pointer, indicating that the target is not in the array.

If we exit the loop without finding the target, we return -1 to indicate that the target is not in the array.

Finally, we provide an example usage of the binary_search function to search for a target value within a sorted list (my_list) and print the result.

Binary search is an efficient algorithm for finding elements in a sorted array because it reduces the search space by half in each iteration.




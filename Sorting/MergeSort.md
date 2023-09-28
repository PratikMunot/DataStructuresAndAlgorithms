# Merge Sort Algorithm

In Merge Sort Algorithm we divide the list into 2 sub parts. These 2 sub-arrays 


Merge sort is an example of the divide and conquer strategy.
• Merging is the process of combining two sorted files to make one bigger sorted file.
• Selection is the process of dividing a file into two parts: k smallest elements and n k largest elements.
• Selection and merging are opposite operations
○ selection splits a list into two lists
○ merging joins two files to make one file
• Merge sort is Quick sort’s complement
• Merge sort accesses the data in a sequential manner
• This algorithm is used for sorting a linked list
• Merge sort is insensitive to the initial order of its input
• In Quick sort most of the work is done before the recursive calls. Quick sort starts
with the largest subfile and finishes with the small ones and as a result it needs
stack. Moreover, this algorithm is not stable. Merge sort divides the list into two
parts; then each part is conquered individually. Merge sort starts with the small
subfiles and finishes with the largest one. As a result it doesn’t need stack. This
algorithm is stable.
Implementation



```
def merge_sort(arr):
    # Step 1: Check if the input list can be divided further
    if len(arr) > 1:
        # Divide the input list into two halves
        mid = len(arr) // 2
        left_half = arr[:mid]
        right_half = arr[mid:]

        # Recursively sort both halves
        merge_sort(left_half)
        merge_sort(right_half)

        # Step 2: Merge the sorted halves
        i = j = k = 0

        # Compare and merge elements from left_half and right_half into the original list
        while i < len(left_half) and j < len(right_half):
            if left_half[i] < right_half[j]:
                arr[k] = left_half[i]
                i += 1
            else:
                arr[k] = right_half[j]
                j += 1
            k += 1

        # Check if any elements were left in either half and add them to the original list
        while i < len(left_half):
            arr[k] = left_half[i]
            i += 1
            k += 1

        while j < len(right_half):
            arr[k] = right_half[j]
            j += 1
            k += 1

# Example usage:
my_list = [64, 25, 12, 22, 11]
merge_sort(my_list)
print("Sorted array is:", my_list)

```

Explanation of each step:

if len(arr) > 1:: We start by checking if the input list arr can be divided further. If it contains only one or zero elements, it is already sorted, so we don't need to do anything.

mid = len(arr) // 2: We find the middle index of the array to divide it into two halves.

left_half = arr[:mid] and right_half = arr[mid:]: We split the input array into two halves: left_half and right_half.

We recursively apply the merge_sort function to both left_half and right_half, which sorts them independently.

After both halves are sorted, we merge them back together:

a. Initialize three pointers (i, j, and k) for the left half, right half, and the original array, respectively.

b. Compare elements from left_half and right_half and copy the smaller element to the original array. Move the corresponding pointers.

c. Continue this process until we've merged all elements from both halves.

Finally, after the merge operation is complete, the entire array will be sorted in ascending order, and we print the sorted array.

Merge sort is a divide-and-conquer sorting algorithm that works well for large lists and is known for its stability and efficiency.



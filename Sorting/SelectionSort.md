# Selection Sort Algorithm

Selection sort is a simple in-place sorting algorithm that repeatedly finds the minimum (or maximum) element from the unsorted portion of the list and moves it to the beginning. Selection sort works well for small files. It is used
for sorting the files with very large values and small keys. This is because selection is made
based on keys and swaps are made only when required.

### Algorithm
1. Assume first element is the smallest and compare it with rest of the list.
1. While comparing Find the minimum value in the list
2. Swap it with that minimum value with the current position
3. Repeat this process for all the elements until the entire array is sorted
#### Advantages
1. Easy to implement
2. In-place sort (requires no additional storage space)


### Time Complexity of Selection Sort Algorithm
> - Worst case complexity : O(n2)
> - Best case complexity : O(n2)
> - Average case complexity : O(n2)
> - Worst case space complexity: O(1) auxiliary

```
def selection_sort(arr):
    # Step 1: Iterate through the entire array
    for i in range(len(arr)):
        # Assume the current index 'i' has the minimum value
        min_index = i

        # Step 2: Compare the element at index 'i' with all the elements to its right
        for j in range(i + 1, len(arr)):
            # If we find a smaller element, update 'min_index'
            if arr[j] < arr[min_index]:
                min_index = j

        # Step 3: Swap the minimum element (at 'min_index') with the current element (at 'i')
        # This moves the smallest unsorted element to its correct position in the sorted part of the array
        arr[i], arr[min_index] = arr[min_index], arr[i]


# Example usage:
my_list = [64, 25, 12, 22, 11]
selection_sort(my_list)
print("Sorted array is:", my_list)

```




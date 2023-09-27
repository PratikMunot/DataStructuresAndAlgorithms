# Bubble Sort Algorithm




```
def bubble_sort(arr):
    # Step 1: Get the length of the input array
    n = len(arr)

    # Step 2: Perform multiple passes through the array
    for i in range(n):
        # Step 3: In each pass, compare adjacent elements and swap them if they are in the wrong order
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]  # Swap the elements if they are out of order

# Example usage:
my_list = [64, 25, 12, 22, 11]
bubble_sort(my_list)
print("Sorted array is:", my_list)

```

```
Explanation of each step:

n = len(arr): We start by getting the length of the input array arr to determine how many elements need to be sorted.

for i in range(n):: This outer loop represents the number of passes through the array. In each pass, the largest unsorted element will "bubble up" to the end of the array.

for j in range(0, n-i-1): This inner loop iterates through adjacent elements in the array, comparing them and swapping them if they are in the wrong order. The -i in n-i-1 ensures that we don't need to compare elements that have already been sorted in previous passes.

if arr[j] > arr[j+1]:: We compare the current element arr[j] with the next element arr[j+1] to check if they are out of order.

arr[j], arr[j+1] = arr[j+1], arr[j]: If the elements are out of order, we swap them using tuple unpacking. This step "bubbles up" the larger element towards the end of the array.

The inner loop continues until we've compared and potentially swapped all adjacent elements for the current pass.

After completing the inner loop for each pass, the largest unsorted element will have moved to the end of the array.

Repeat this process for all passes until the entire array is sorted.

Finally, after the outer loop completes, the entire array will be sorted, and we print the sorted array.

Bubble sort is not the most efficient sorting algorithm, especially for large lists, but it's useful for understanding the basic concept of sorting algorithms.


```


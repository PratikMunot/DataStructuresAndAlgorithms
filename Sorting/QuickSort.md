# Quick Sort Algorithm

Quick sort is an example of a divide-and-conquer algorithmic technique. It is also called partition exchange sort. It uses recursive calls for sorting the elements, and it is one of the famous algorithms among comparison-based sorting algorithms.
Divide: The array A[low ...high] is partitioned into two non-empty sub arrays A[low ...q] and A[q+ 1... high], such that each element of A[low ... high] is less than or equal to each element of A[q+ 1... high]. The index q is computed as part of this partitioning procedure.
Conquer: The two sub arrays A[low ...q] and A[q + 1 ...high] are sorted by recursive calls to Quick sort.
Algorithm
The recursive algorithm consists of four steps:
1) If there are one or no elements in the array to be sorted, return.
2) Pick an element in the array to serve as the “pivot” point. (Usually the left-most element in the array is used.)
3) 3 new arrays are formed where first array will hold elements less than pivot. Second array will hold element equal to pivot and third array will hold element greater than pivot.
4) Using a for loop start arranging each element in the respective array. 
5) Recursively repeat the algorithm for both halves of the original array.


### Time Complexity of Quick sort Algorithm
> - Worst case Complexity: O(n2)
> - Best case Complexity: O(nlogn)
> - Average case Complexity: O(nlogn)
> - Worst case space Complexity: O(1)

```
def quick_sort(arr):
    # Step 1: Check if the input list is empty or has only one element (base case)
    if len(arr) <= 1:
        return arr

    # Step 2: Choose a pivot element (usually the first element)
    pivot = arr[0]

    # Step 3: Partition the array into three sub-arrays: elements less than, equal to, and greater than the pivot
    less_than_pivot = []
    equal_to_pivot = []
    greater_than_pivot = []

    for element in arr:
        if element < pivot:
            less_than_pivot.append(element)
        elif element == pivot:
            equal_to_pivot.append(element)
        else:
            greater_than_pivot.append(element)

    # Step 4: Recursively sort the sub-arrays
    sorted_less = quick_sort(less_than_pivot)
    sorted_greater = quick_sort(greater_than_pivot)

    # Step 5: Combine the sorted sub-arrays with the pivot element in the middle
    return sorted_less + equal_to_pivot + sorted_greater

# Example usage:
my_list = [64, 25, 12, 22, 11]
sorted_list = quick_sort(my_list)
print("Sorted array is:", sorted_list)

```

Explanation of each step:

if len(arr) <= 1:: We start by checking if the input list arr is empty or contains only one element. In such cases, there is nothing to sort, so we return the input list as it is (base case).

pivot = arr[0]: We choose a pivot element. In this implementation, we use the first element of the array as the pivot. The choice of the pivot can affect the efficiency of the quick sort algorithm.

We partition the array into three sub-arrays: elements less than the pivot, elements equal to the pivot, and elements greater than the pivot. We use for loops and conditional statements to categorize elements into these sub-arrays.

We recursively apply the quick_sort function to the sub-arrays containing elements less than the pivot and elements greater than the pivot. This step sorts these sub-arrays independently.

Finally, we combine the sorted sub-arrays with the pivot element in the middle to produce the final sorted array. This is done by concatenating the sorted less-than array, the equal-to-pivot array, and the sorted greater-than array.

The result of this process is a sorted array in ascending order. Quick sort is known for its efficiency and is a widely used sorting algorithm in practice.





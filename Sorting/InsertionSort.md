# Insertion Sort Algorithm

Insertion sort is a simple and efficient comparison sort. In this algorithm, each iteration removes an element from the input data serially and inserts it into the correct position in the list being sorted. This process is repeated until all input elements have gone through.

### Advantages
> 1. Simple implementation
> 2. Efficient for small data
> 3. Adaptive: If the input list is presorted [may not be completely] then insertions sort takes O(n + d), where d is the number of inversions
> 4. Practically more efficient than selection and bubble sorts, even though all of them have O(n2) worst case complexity
> 5. Stable: Maintains relative order of input data if the keys are same
> 6. In-place: It requires only a constant amount O(1) of additional memory space
> 7. Online: Insertion sort can sort the list as it receives it

### Algorithm
Every repetition of insertion sort removes an element from the input data, and inserts it into the
correct position in the already-sorted list until no input elements remain. Sorting is typically done
in-place. The resulting array after k iterations has the property where the first k + 1 entries are
sorted.

```
def insertion_sort(arr):
    # Step 1: Start with the second element (index 1) since the first element (index 0) is considered sorted.
    for i in range(1, len(arr)):
        # Step 2: Store the current element to be inserted into the sorted part of the array.
        current_element = arr[i]
        
        # Step 3: Start from the last element of the sorted part (index i-1) and move towards the beginning.
        j = i - 1
        
        # Step 4: Compare the current element with the elements in the sorted part.
        # If the current element is smaller, move the larger element to the right.
        while j >= 0 and current_element < arr[j]:
            arr[j + 1] = arr[j]  # Shift the larger element to the right.
            j -= 1  # Move one position to the left in the sorted part.

        # Step 5: Place the current element in its correct position within the sorted part.
        arr[j + 1] = current_element

# Example usage:
my_list = [64, 25, 12, 22, 11]
insertion_sort(my_list)
print("Sorted array is:", my_list)


```

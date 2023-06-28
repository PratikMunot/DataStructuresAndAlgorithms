# Insertion Sort
To sort an array of size N in ascending order iterate over the array and compare the current element (key) to its predecessor, if the key element is 
smaller than its predecessor, compare it to the elements before. Move the greater elements one position up to make space for the swapped element.

Consider an example: arr = [4,3,2,10,12,1,5,6]

```
def insertion_sort(arr):
    k = len(arr)
    while k > 0:
        for i in range(1,k):
            if arr[i] < arr[i-1]: arr[i],arr[i-1] = arr[i-1],arr[i]
        k -= 1



arr = [4,3,2,10,12,1,5,6]
insertion_sort(arr)
print(arr)
```










# Random-Pivot-Quick-Sort-for-Numbers-and-Strings-49-100
import random

def partition(A, left_index, right_index):
    pivot = A[left_index]
    i = left_index + 1
    for j in range(left_index + 1, right_index):
        if A[j] < pivot:
            A[j], A[i] = A[i], A[j]
            i += 1
    A[left_index], A[i - 1] = A[i - 1], A[left_index]
    return i - 1

def quick_sort_random(A, left, right):
    if left < right:
        pivot = random.randint(left, right - 1)
        A[pivot], A[left] = A[left], A[pivot]  # switch pivot with leftmost element
        pivot_index = partition(A, left, right)
        quick_sort_random(A, left, pivot_index)        # left subarray
        quick_sort_random(A, pivot_index + 1, right)  # right subarray

# Test case 1
nums = [4, 3, 5, 1, 2]
quick_sort_random(nums, 0, len(nums))
print(nums)

# Test case 2
nums = [5, 9, 10, 3, -4, 5, 178, 92, 46, -18, 0, 7]
quick_sort_random(nums, 0, len(nums))
print(nums)

# Test case 3
nums = [1.1, 1, 0, -1, -1.1, 0.1]
quick_sort_random(nums, 0, len(nums))
print(nums)

# Test case 4
nums = ['z', 'a', 'y', 'b', 'x', 'c']
quick_sort_random(nums, 0, len(nums))
print(nums)

 =============
[1, 2, 3, 4, 5]
[-18, -4, 0, 3, 5, 5, 7, 9, 10, 46, 92, 178]
[-1.1, -1, 0, 0.1, 1, 1.1]
['a', 'b', 'c', 'x', 'y', 'z']


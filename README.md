def shell_sort(arr):
    n = len(arr)
    gap = n // 2
    while gap > 0:
        for i in range(gap, n):
            temp = arr[i]
            j = i
            while j >= gap and arr[j - gap] > temp:
                arr[j] = arr[j - gap]
                j -= gap
            arr[j] = temp
        gap //= 2

# Example usage:
arr = [64, 25, 12, 22, 11]
shell_sort(arr)
print("Sorted array is:", arr)
##########################################################################
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    less = [x for x in arr if x < pivot]
    equal = [x for x in arr if x == pivot]
    greater = [x for x in arr if x > pivot]
    return quick_sort(less) + equal + quick_sort(greater)

# Example usage:
arr = [64, 25, 12, 22, 11]
sorted_arr = quick_sort(arr)
print("Sorted array is:", sorted_arr)
###########################################################################

def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left_half = merge_sort(arr[:mid])
    right_half = merge_sort(arr[mid:])
    return merge(left_half, right_half)

def merge(left, right):
    merged = []
    l, r = 0, 0
    while l < len(left) and r < len(right):
        if left[l] < right[r]:
            merged.append(left[l])
            l += 1
        else:
            merged.append(right[r])
            r += 1
    merged.extend(left[l:])
    merged.extend(right[r:])
    return merged

# Example usage:
arr = [64, 25, 12, 22, 11]
sorted_arr = merge_sort(arr)
print("Sorted array is:", sorted_arr)
################################################################

def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key

# Example usage:
arr = [64, 25, 12, 22, 11]
insertion_sort(arr)
print("Sorted array is:", arr)
##################################################################
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_idx = i
        for j in range(i+1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]

# Example usage:
arr = [64, 25, 12, 22, 11]
selection_sort(arr)
print("Sorted array is:", arr)
#####################################################################
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]

# Example usage:
arr = [64, 25, 12, 22, 11]
bubble_sort(arr)
print("Sorted array is:", arr)
########################################################################################################################################3

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class Stack:
    def __init__(self):
        self.top = None
        self.size = 0

    def is_empty(self):
        return self.size == 0

    def push(self, item):
        new_node = Node(item)
        new_node.next = self.top
        self.top = new_node
        self.size += 1

    def pop(self):
        if self.is_empty():
            return None
        popped_item = self.top.data
        self.top = self.top.next
        self.size -= 1
        return popped_item

    def peek(self):
        if self.is_empty():
            return None
        return self.top.data

    def stack_size(self):
        return self.size
########################################################################

class Queue:
    def __init__(self):
        self.items = []

    def is_empty(self):
        return len(self.items) == 0

    def enqueue(self, item):
        self.items.append(item)

    def dequeue(self):
        if self.is_empty():
            return None
        else:
            return self.items.pop(0)

    def peek(self):
        if self.is_empty():
            return None
        else:
            return self.items[0]

    def size(self):
        return len(self.items)

queue = Queue()
print(queue.size())
print(queue.is_empty())
queue.enqueue(4)
print(queue.dequeue())
################################################################

def next_day(day, month, year):
    days_in_month = [31, 28 + (year % 4 == 0 and (year % 100 != 0 or year % 400 == 0)), 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    day += 1
    if day > days_in_month[month - 1]:
        day = 1
        month += 1
        if month > 12:
            month = 1
            year += 1
    return f"{day}/{month}/{year}"

# Test cases
print(next_day(3, 7, 2023))   # Output: 4/7/2023
print(next_day(31, 12, 2023))  # Output: 1/1/2024
print(next_day(28, 2, 2020))   # Output: 29/2/2020
#################################################################
def sum_of_even_numbers(numbers_list):
    sum = 0
    for number in numbers_list:
        if number % 2 == 0:
            sum += number
    return sum

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print("Sum of even numbers in the list:", sum_of_even_numbers(numbers))
#######################################################

def print_odd_numbers(numbers_list):
    for number in numbers_list:
        if number % 2 != 0:
            print(number)

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print("Odd numbers in the list:")
print_odd_numbers(numbers)
##########################################################################


Question 1 →

Armstrong Numbers →

For a given 3 digit number, find whether it is Armstrong number or not. An Armstrong number of three digits is an integer such that the sum of the cubes of its digits is equal to the number itself. Return “Yes” if it is a Armstrong number else return “No”.
NOTE: 371 is an Armstrong number since 33 + 73 + 13 = 371


def is_armstrong_number(number):
    if not isinstance(number, int) or number < 100 or number > 999:
        return "No"

    digit1 = number % 10
    digit2 = (number // 10) % 10
    digit3 = number // 100

    sum_of_cubes = digit1 ** 3 + digit2 ** 3 + digit3 ** 3

    if sum_of_cubes == number:
        return "Yes"
    else:
        return "No"


Question 2 →

Find duplicates in an array - >

Given an array a of size N which contains elements from 0 to N-1, you need to find all the elements occurring more than once in the given array. Return the answer in ascending order. If no such element is found, return list containing [-1].

Note: The extra space is only for the array to be returned. Try and perform all operations within the provided array.


def findDuplicateElements(a, n):
    count = [0] * (n + 1)

    for num in a:
        count[num] += 1

    duplicates = [i for i, freq in enumerate(count) if freq > 1]

    return sorted(duplicates)


# Taking input from the user
n = int(input("Enter the length of the array: "))
input_array = []
for i in range(n):
    element = int(input(f"Enter element {i + 1}: "))
    input_array.append(element - 1)  # Decrement by 1 to use as an index

result = findDuplicateElements(input_array, n)
if result:
    print("Duplicate elements:", result)
else:
    print("No duplicate elements found. [-1]")



Question 3 →

Reverse a linked list →

Given a linked list of N nodes. The task is to reverse this list.

class ListNode:
    def __init__(self, value):
        self.value = value
        self.next = None

def reverseList(head):
    prev = None
    current = head

    while current is not None:
        next_node = current.next
        current.next = prev
        prev = current
        current = next_node

    return prev

# Helper function to print linked list
def print_linked_list(head):
    current = head
    while current is not None:
        print(current.value, end=" -> ")
        current = current.next
    print("None")

# Taking input from the user to create the linked list
input_list = list(map(int, input("Enter elements of the linked list separated by spaces: ").split()))
head = None
prev_node = None

for val in input_list:
    new_node = ListNode(val)
    if head is None:
        head = new_node
    if prev_node is not None:
        prev_node.next = new_node
    prev_node = new_node

print("\nOriginal linked list:")
print_linked_list(head)

reversed_head = reverseList(head)

print("\nReversed linked list:")
print_linked_list(reversed_head)



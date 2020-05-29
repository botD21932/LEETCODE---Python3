# Linked List

Здесь будут выкладываться задачи, помеченные тегом **Linked List** на сайте **LEETCODE**. Полный их список можно найти [здесь](https://leetcode.com/problemset/all/?topicSlugs=linked-list). В блоках кода будут находиться только решения задач. Определение **Linked List** выглядит следующим образом:

```python

class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

```


# Список задач:

+ [Add Two Numbers](#add-two-numbers)

# Решения задач:

## Add Two Numbers

https://leetcode.com/problems/add-two-numbers/

```python

def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
    fakehead = ListNode(0)
    firstPointer = l1
    secondPointer = l2
    current = fakehead
    carry = 0
    while firstPointer and secondPointer:
        sum = carry + firstPointer.val + secondPointer.val
        carry = sum // 10
        current.next = ListNode(sum % 10)
        current = current.next
        firstPointer = firstPointer.next
        secondPointer = secondPointer.next
    while firstPointer:
        sum = carry + firstPointer.val
        carry = sum // 10
        current.next = ListNode(sum % 10)
        current = current.next
        firstPointer = firstPointer.next
    while secondPointer:
        sum = carry + secondPointer.val
        carry = sum // 10
        current.next = ListNode(sum % 10)
        current = current.next
        secondPointer = secondPointer.next
    if carry > 0:
        current.next = ListNode(carry)
    return fakehead.next


```

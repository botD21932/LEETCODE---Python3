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
+ [Remove Nth Node From End of List](#remove-nth-node-from-end-of-list)
+ [Merge Two Sorted Lists](#merge-two-sorted-lists)
+ [Merge k Sorted Lists](#merge-k-sorted-lists)
+ [Swap Nodes in Pairs](#swap-nodes-in-pairs)
+ [Reverse Nodes in k-Group](#reverse-nodes-in-k-group)
+ [Reverse Nodes in k-Group](#reverse-nodes-in-k-group)
+ [Rotate List](#rotate-list)
+ [Remove Duplicates from Sorted List II](#remove-duplicates-from-sorted-list-ii)
+ [Remove Duplicates from Sorted List](#remove-duplicates-from-sorted-list)
+ [Partition List](#partition-list)
+ [Reverse Linked List II](#reverse-linked-list-ii)
+ [Convert Sorted List to Binary Search Tree](#convert-sorted-list-to-binary-search-tree)
+ [Copy List with Random Pointer](#copy-list-with-random-pointer)
+ [Linked List Cycle](#linked-list-cycle)
+ [Linked List Cycle II](#linked-list-cycle-ii)
+ [Reorder List](#reorder-list)
+ [Insertion Sort List](#insertion-sort-list)
+ [Sort List](#sort-list)
+ [Intersection of Two Linked Lists](#intersection-of-two-linked-lists)
+ [Remove Linked List Elements](#remove-linked-list-elements)
+ [Reverse Linked List](#reverse-linked-list)
+ [Palindrome Linked List](#palindrome-linked-list)
+ [Delete Node in a Linked List](#delete-node-in-a-linked-list)
+ [Odd Even Linked List](#odd-even-linked-list)
+ [Plus One Linked List](#plus-one-linked-list)
+ [Design Phone Directory](#design-phone-directory)
+ [Convert Binary Search Tree to Sorted Doubly Linked List](#convert-binary-search-tree-to-sorted-doubly-linked-list)
+ [Flatten a Multilevel Doubly Linked List](#flatten-a-multilevel-doubly-linked-list)
+ [Add Two Numbers II](#add-two-numbers-ii)
+ [Design Linked List](#design-linked-list)
+ [Insert into a Sorted Circular Linked List](#insert-into-a-sorted-circular-linked-list)
+ [Split Linked List in Parts](#split-linked-list-in-parts)
+ [Linked List Components](#linked-list-components)
+ [Middle of the Linked List](#middle-of-the-linked-list)
+ [Next Greater Node In Linked List](#next-greater-node-in-linked-list)
+ [Remove Zero Sum Consecutive Nodes from Linked List](#remove-zero-sum-consecutive-nodes-from-linked-list)
+ [Convert Binary Number in a Linked List to Integer](#convert-binary-number-in-a-linked-list-to-integer)
+ [Linked List in Binary Tree](#linked-list-in-binary-tree)

# Решения задач

## Add Two Numbers

https://leetcode.com/problems/add-two-numbers/

## Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list/

```python
def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
    start = ListNode(0)
    start.next = head
    firstPoint = start
    secondPoint = start
    for i in range(1,n+2):
        firstPoint = firstPoint.next
    while firstPoint:
        firstPoint = firstPoint.next
        secondPoint = secondPoint.next
    secondPoint.next = secondPoint.next.next
    return start.next
    
```

## Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/

```python
def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
    head = ListNode(0)
    pointer = head
    while l1 and l2:
        if l1.val < l2.val:
            pointer.next = l1
            l1 = l1.next
        else:
            pointer.next = l2
            l2 = l2.next
        pointer = pointer.next
    if not l1:
        pointer.next = l2
    if not l2:
        pointer.next = l1
    return head.next
 
```

## Merge k Sorted Lists

https://leetcode.com/problems/merge-k-sorted-lists/

## Swap Nodes in Pairs

https://leetcode.com/problems/swap-nodes-in-pairs/

## Reverse Nodes in k-Group

https://leetcode.com/problems/reverse-nodes-in-k-group/

## Reverse Nodes in k-Group

https://leetcode.com/problems/reverse-nodes-in-k-group/

## Rotate List

https://leetcode.com/problems/rotate-list/

## Remove Duplicates from Sorted List II

https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/

## Remove Duplicates from Sorted List

https://leetcode.com/problems/remove-duplicates-from-sorted-list/

## Partition List

https://leetcode.com/problems/partition-list/

```python
def partition(self, head: ListNode, x: int) -> ListNode:
    if not head:
        return head
    lowerHead = ListNode(0)
    currentLower = lowerHead
    biggerHead = ListNode(0)
    currentBigger = biggerHead
    while head:
        if head.val < x:
            currentLower.next = ListNode(head.val)
            currentLower = currentLower.next
        else:
            currentBigger.next = ListNode(head.val)
            currentBigger = currentBigger.next
        head = head.next
    if lowerHead.next:
        currentLower.next = biggerHead.next
        return lowerHead.next
    else:
        return biggerHead.next

```

## Reverse Linked List II

https://leetcode.com/problems/reverse-linked-list-ii/

## Convert Sorted List to Binary Search Tree

https://leetcode.com/problems/convert-sorted-list-to-binary-search-tree/

## Copy List with Random Pointer

https://leetcode.com/problems/copy-list-with-random-pointer/

## Linked List Cycle

https://leetcode.com/problems/linked-list-cycle/

```python
def hasCycle(self, head: ListNode) -> bool:
    if not head:
        return False
    slowPointer = head
    fastPointer = head.next
    while fastPointer and fastPointer != slowPointer:
        fastPointer = fastPointer.next
        if not fastPointer:
            return False
        slowPointer = slowPointer.next
        fastPointer = fastPointer.next
    if slowPointer == fastPointer:
        return True
    return False

```

## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

```python
def detectCycle(self, head: ListNode) -> ListNode:
    if not head:
        return None
    slowPointer = head
    fastPointer = head.next
    while fastPointer and fastPointer != slowPointer:
        fastPointer = fastPointer.next
        if not fastPointer:
            return None
        slowPointer = slowPointer.next
        fastPointer = fastPointer.next
    if slowPointer == fastPointer:
        current = head
        fastPointer = fastPointer.next
        while current != fastPointer:
            current = current.next
            fastPointer = fastPointer.next
        return current
    return None

```
## Reorder List

https://leetcode.com/problems/reorder-list/

```python
def reorderList(self, head: ListNode) -> None:
    if not head:
        return head
    nodeList = []
    currentNode = head
    begin = 0
    end = -1
    while currentNode:
        nodeList.append(currentNode)
        currentNode = currentNode.next
        end = end + 1
    while begin < end:
        nodeList[begin].next = nodeList[end]
        begin = begin + 1
        if begin >= end:
            break
        nodeList[end].next = nodeList[begin]
        end = end - 1
    nodeList[end].next = None


def reorderList(self, head: ListNode) -> None:
    if not head:
        return head
    fastPoint = head
    slowPoint = head
    while fastPoint and fastPoint.next:
        slowPoint = slowPoint.next
        fastPoint = fastPoint.next.next
    tail = slowPoint
    previous = None
    half = slowPoint.next
    while half:
        slowPoint.next = previous
        previous = slowPoint
        slowPoint = half
        half = half.next
    slowPoint.next = previous
    current = None
    while current != tail:
        current = head.next
        head.next = slowPoint
        head = slowPoint
        slowPoint = current

```

## Insertion Sort List

https://leetcode.com/problems/insertion-sort-list/

## Sort List

https://leetcode.com/problems/sort-list/

```python
def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
    head = ListNode(0)
    pointer = head
    while l1 and l2:
        if l1.val < l2.val:
            pointer.next = l1
            l1 = l1.next
        else:
            pointer.next = l2
            l2 = l2.next
        pointer = pointer.next
    if not l1:
        pointer.next = l2
    elif not l2:
        pointer.next = l1
    return head.next


def middleNode(self, head: ListNode) -> ListNode:
    firstPoint = head
    secondPoint = head
    while secondPoint.next and secondPoint.next.next:
        firstPoint = firstPoint.next
        secondPoint = secondPoint.next.next
    return firstPoint


def sortList(self, head: ListNode) -> ListNode:
    if not head or not head.next:
        return head
    middle = self.middleNode(head)
    rightList = self.sortList(middle.next)
    middle.next = None
    leftList = self.sortList(head)
    return self.mergeTwoLists(leftList, rightList)

```

## Intersection of Two Linked Lists

https://leetcode.com/problems/intersection-of-two-linked-lists/

```python
def getIntersectionNode(self, headA: ListNode, headB: ListNode) -> ListNode:
    pointA = headA
    pointB = headB
    while(pointA != pointB):
        if not pointA:
            pointA = headB
        else:
            pointA = pointA.next
        if not pointB:
            pointB = headA
        else:
            pointB = pointB.next
    return pointA

```

## Remove Linked List Elements

https://leetcode.com/problems/remove-linked-list-elements/

## Reverse Linked List

https://leetcode.com/problems/reverse-linked-list/

```python
def reverseList(self, head: ListNode) -> ListNode:
    previous = None
    current = head
    while current:
        nextTemp = current.next
        current.next = previous
        previous = current
        current = nextTemp
    return previous

```

## Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/

```python
def reverseList(self, head: ListNode) -> ListNode:
    previous = None
    current = head
    while current:
        nextTemp = current.next
        current.next = previous
        previous = current
        current = nextTemp
    return previous


def isEqual(self, firstHalf: ListNode, secondHalf: ListNode) -> bool:
    while secondHalf:
        if secondHalf.val != firstHalf.val:
            return False
        secondHalf = secondHalf.next
        firstHalf = firstHalf.next
    return True


def isPalindrome(self, head: ListNode) -> bool:
    if not head or not head.next:
        return True
    firstPoint = head
    secondPoint = head
    while secondPoint.next and secondPoint.next.next:
        firstPoint = firstPoint.next
        secondPoint = secondPoint.next.next
    if not secondPoint.next:
        secondHalf = copy.copy(firstPoint)
    else:
        secondHalf = copy.copy(firstPoint.next)
    firstPoint.next = None
    firstHalf = self.reverseList(head)
    return self.isEqual(firstHalf, secondHalf)

```

## Delete Node in a Linked List

https://leetcode.com/problems/delete-node-in-a-linked-list/

## Odd Even Linked List

https://leetcode.com/problems/odd-even-linked-list/

## Plus One Linked List

https://leetcode.com/problems/plus-one-linked-list

## Design Phone Directory

https://leetcode.com/problems/design-phone-directory

## Convert Binary Search Tree to Sorted Doubly Linked List

https://leetcode.com/problems/convert-binary-search-tree-to-sorted-doubly-linked-list/

## Flatten a Multilevel Doubly Linked List

https://leetcode.com/problems/flatten-a-multilevel-doubly-linked-list/

## Add Two Numbers II

https://leetcode.com/problems/add-two-numbers-ii/

## Design Linked List

https://leetcode.com/problems/design-linked-list/

## Insert into a Sorted Circular Linked List

https://leetcode.com/problems/insert-into-a-sorted-circular-linked-list/

## Split Linked List in Parts

https://leetcode.com/problems/split-linked-list-in-parts/

## Linked List Components

https://leetcode.com/problems/linked-list-components/

## Middle of the Linked List

https://leetcode.com/problems/middle-of-the-linked-list/

```python
def middleNode(self, head: ListNode) -> ListNode:
    firstPointer = head
    secondPointer = head
    while secondPointer and secondPointer.next:
        firstPointer = firstPointer.next
        secondPointer = secondPointer.next.next
    return firstPointer

```

## Next Greater Node In Linked List

https://leetcode.com/problems/next-greater-node-in-linked-list/

## Remove Zero Sum Consecutive Nodes from Linked List

https://leetcode.com/problems/remove-zero-sum-consecutive-nodes-from-linked-list/

## Convert Binary Number in a Linked List to Integer

https://leetcode.com/problems/convert-binary-number-in-a-linked-list-to-integer/

## Linked List in Binary Tree

https://leetcode.com/problems/linked-list-in-binary-tree/

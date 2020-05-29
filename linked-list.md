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

## Merge Two Sorted Lists

https://leetcode.com/problems/merge-two-sorted-lists/

## Merge k Sorted Lists

https://leetcode.com/problems/merge-k-sorted-lists/

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


def mergeKLists(self, lists: List[ListNode]) -> ListNode:
    if lists == []:
        return
    amount = len(lists)
    interval = 1
    while interval < amount:
        for i in range(0, amount - interval, interval * 2):
            lists[i] = self.mergeTwoLists(lists[i], lists[i + interval])
        interval *= 2
    return lists[0]

```

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

## Reverse Linked List II

https://leetcode.com/problems/reverse-linked-list-ii/

## Convert Sorted List to Binary Search Tree

https://leetcode.com/problems/convert-sorted-list-to-binary-search-tree/

## Copy List with Random Pointer

https://leetcode.com/problems/copy-list-with-random-pointer/

## Linked List Cycle

https://leetcode.com/problems/linked-list-cycle/

## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii/

## Reorder List

https://leetcode.com/problems/reorder-list/

## Insertion Sort List

https://leetcode.com/problems/insertion-sort-list/

# Sort List

https://leetcode.com/problems/sort-list/

## Intersection of Two Linked Lists

https://leetcode.com/problems/intersection-of-two-linked-lists/

## Remove Linked List Elements

https://leetcode.com/problems/remove-linked-list-elements/

## Reverse Linked List

https://leetcode.com/problems/reverse-linked-list/

## Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list/

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

## Next Greater Node In Linked List

https://leetcode.com/problems/next-greater-node-in-linked-list/

## Remove Zero Sum Consecutive Nodes from Linked List

https://leetcode.com/problems/remove-zero-sum-consecutive-nodes-from-linked-list/

## Convert Binary Number in a Linked List to Integer

https://leetcode.com/problems/convert-binary-number-in-a-linked-list-to-integer/

## Linked List in Binary Tree

https://leetcode.com/problems/linked-list-in-binary-tree/

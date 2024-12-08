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

```python
def deleteDuplicates(self, head: ListNode) -> ListNode:
    if not head or not head.next:
        return head
    current = head
    while current and current.next:
        if current.val == current.next.val:
            while current.next and current.val == current.next.val:
                current.next = current.next.next
            if current == head:
                head = current.next
            else:
                previous.next = current.next
                current = current.next
        else:
            previous = current
            current = current.next
    return head

```

## Remove Duplicates from Sorted List

https://leetcode.com/problems/remove-duplicates-from-sorted-list/

```python
def deleteDuplicates(self, head: ListNode) -> ListNode:
    current = head
    while current and current.next:
        if current.val == current.next.val:
            current.next = current.next.next
        else:
            current = current.next
    return head

```

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

```python
def reverseBetween(self, head: ListNode, m: int, n: int) -> ListNode:
    fakeHead = ListNode(0)
    fakeHead.next = head
    tail = fakeHead
    for i in range(m - 1):
        tail = tail.next
    previous = None
    current = tail.next
    newTail = current
    next = None
    for i in range(n - m + 1):
        next = current.next
        current.next = previous
        previous = current
        current = next
    tail.next = previous
    newTail.next = current
    return fakeHead.next

```

## Convert Sorted List to Binary Search Tree

https://leetcode.com/problems/convert-sorted-list-to-binary-search-tree/

```python
def sortedListToBST(self, head: ListNode) -> TreeNode:
    if not head:
        return None
    if not head.next:
        return TreeNode(head.val)
    slowPointer = head
    fastPointer = head
    while fastPointer and fastPointer.next:
        fastPointer = fastPointer.next.next
        if not fastPointer or not fastPointer.next:
            rightPart = slowPointer.next.next
            result = TreeNode(slowPointer.next.val)
            slowPointer.next = None
        slowPointer = slowPointer.next
    result.right = self.sortedListToBST(rightPart)
    result.left = self.sortedListToBST(head)
    return result

```

## Copy List with Random Pointer

https://leetcode.com/problems/copy-list-with-random-pointer/

```python
def copyRandomList(self, head: 'Node') -> 'Node':
    return copy.deepcopy(head)

```

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

```python
def bump(self, head: ListNode, elem: ListNode) -> ListNode:
    current = head
    while current.next and current.next.val <= elem.val:
        current = current.next
    elem.next = current.next
    current.next = elem
    return head


def insertionSortList(self, head: ListNode) -> ListNode:
    if not head or not head.next:
        return head
    fakeHead = ListNode(0)
    sortedList = head
    current = head.next
    head.next = None
    fakeHead.next = head
    while current:
        nextNode = current.next
        current.next = None
        fakeHead = self.bump(fakeHead, current)
        current = nextNode
    return fakeHead.next

```

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

```python
def removeElements(self, head: ListNode, val: int) -> ListNode:
    if not head:
        return head
    while head and head.val == val:
        head = head.next
    current = head
    while current and current.next:
        if current.next.val == val:
            current.next = current.next.next
        else:
            current = current.next
    return head

```

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

```python
def deleteNode(self, node):
    node.val = node.next.val
    node.next = node.next.next

```

## Odd Even Linked List

https://leetcode.com/problems/odd-even-linked-list/

```python
def oddEvenList(self, head: ListNode) -> ListNode:
    if not head:
        return head
    oddCurrent = head
    evenHead = head.next
    evenCurrent = head.next
    while oddCurrent.next and evenCurrent.next:
        oddCurrent.next = oddCurrent.next.next
        oddCurrent = oddCurrent.next
        evenCurrent.next = evenCurrent.next.next
        evenCurrent = evenCurrent.next
    oddCurrent.next = evenHead
    return head

```

## Plus One Linked List

https://leetcode.com/problems/plus-one-linked-list

## Design Phone Directory

https://leetcode.com/problems/design-phone-directory

## Convert Binary Search Tree to Sorted Doubly Linked List

https://leetcode.com/problems/convert-binary-search-tree-to-sorted-doubly-linked-list/

## Flatten a Multilevel Doubly Linked List

https://leetcode.com/problems/flatten-a-multilevel-doubly-linked-list/

```python
def flatten(self, head: 'Node') -> 'Node':
    if not head:
        return head
    if head.child:
        tail = head.next
        head.next = self.flatten(head.child)
        head.child = None
        if head.next:
            head.next.prev = head
        current = head.next
        while current and current.next:
            current = current.next
        current.next = self.flatten(tail)
        if current.next:
            current.next.prev = current
    else:
        head.next = self.flatten(head.next)
    return head

```

## Add Two Numbers II

https://leetcode.com/problems/add-two-numbers-ii/

```python
def toNumber(self, head: ListNode, accum: int) -> int:
    if not head.next:
        return accum + head.val
    return self.toNumber(head.next, (accum + head.val) * 10)


def toList(self, number: int) -> ListNode:
    line = str(number)
    head = ListNode(line[0])
    current = head
    for i in range(1, len(line)):
        current.next = ListNode(line[i])
        current = current.next
    return head


def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
    return (self.toList(self.toNumber(l1, 0) + self.toNumber(l2, 0)))

```

## Design Linked List

https://leetcode.com/problems/design-linked-list/

```python
class Node:
    def __init__(self, val):
        self.val = val


class MyLinkedList:

    def __init__(self):
        self.head = self.tail = None

    def get(self, index: int) -> int:
        current = self.head
        while current and current != self.tail and index:
            current = current.next
            index -= 1
        if current and not index:
            return current.val
        return -1

    def addFirst(self, val: int) -> None:
        node = Node(val)
        self.head = self.tail = node.next = node.pre = node

    def addAtHead(self, val: int) -> None:
        if not self.head:
            return self.addFirst(val)
        node = Node(val)
        node.next = self.head
        node.pre = self.tail
        self.tail.next = self.head.pre = node
        self.head = node

    def addAtTail(self, val: int) -> None:
        if not self.head:
            return self.addFirst(val)
        node = Node(val)
        node.next = self.head
        node.pre = self.tail
        self.tail.next = self.head.pre = node
        self.tail = node

    def addAtIndex(self, index: int, val: int) -> None:
        if index == 0:
            return self.addAtHead(val)
        if not self.head:
            return
        index = index - 1
        current = self.head
        while current and current != self.tail and index:
            current = current.next
            index = index - 1
        if index > 0:
            return
        node = Node(val)
        node.next = current.next
        node.pre = current
        current.next.pre = node
        current.next = node
        if current == self.tail:
            self.tail = node

    def deleteAtIndex(self, index: int) -> None:
        if not self.head:
            return
        if self.head == self.tail and not index:
            self.head = self.tail = None
            return
        current = self.head
        while current and current != self.tail and index:
            current = current.next
            index = index - 1
        if not index:
            current.pre.next = current.next
            current.next.pre = current.pre
            if current == self.head:
                self.head = current.next
            if current == self.tail:
                self.tail = current.pre

```

## Insert into a Sorted Circular Linked List

https://leetcode.com/problems/insert-into-a-sorted-circular-linked-list/

## Split Linked List in Parts

https://leetcode.com/problems/split-linked-list-in-parts/

```python
    def splitListToParts(self, root: ListNode, k: int) -> List[ListNode]:
        current = root
        counter = 0
        while current:
            current = current.next
            counter = counter + 1
        width, add = divmod(counter, k)
        result = []
        current = root
        for i in range(k):
            head = current
            for j in range(width + (i < add) - 1):
                if current: 
                    current = current.next
            if current:
                nextTemp = current.next
                current.next = None
                current = nextTemp
            result.append(head)
        return result
  
  ```

## Linked List Components

https://leetcode.com/problems/linked-list-components/

```python
def numComponents(self, head: ListNode, G: List[int]) -> int:
    current = head
    counter = 0
    while current:
        if current.val in G:
            while current and current.val in G:
                current = current.next
            counter = counter + 1
        else:
            current = current.next
    return counter

```

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

```python
def nextLargerNodes(self, head: ListNode) -> List[int]:
    listnode = []
    length = 0
    while head:
        listnode.append(head.val)
        head = head.next
        length = length + 1
    result = [0]*length
    stack = []
    for i in range(length):
        while stack and listnode[stack[-1]] < listnode[i]:
            result[stack.pop()] = listnode[i]
        stack.append(i)
    return result

```

## Remove Zero Sum Consecutive Nodes from Linked List

https://leetcode.com/problems/remove-zero-sum-consecutive-nodes-from-linked-list/

```python
def removeZeroSumSublists(self, head: ListNode) -> ListNode:
    fakeHead = ListNode(-1)
    fakeHead.next = head
    sums = {0: fakeHead}
    current = fakeHead.next
    currentSum = 0
    while current:
        currentSum = currentSum + current.val
        if currentSum in sums:
            deleteNode = sums[currentSum].next
            sums[currentSum].next = current.next
            deleteSum = currentSum
            while deleteNode.next != current.next:
                deleteSum = deleteSum + deleteNode.val
                del sums[deleteSum]
                deleteNode = deleteNode.next
        else:
            sums[currentSum] = current
        current = current.next
    return fakeHead.next

```

## Convert Binary Number in a Linked List to Integer

https://leetcode.com/problems/convert-binary-number-in-a-linked-list-to-integer/

```python
def getDecimalValue(self, head: ListNode) -> int:
    if not head:
        return 0
    counter = 0
    while head:
        counter = 2*counter + head.val
        head = head.next
    return counter

```

## Linked List in Binary Tree

https://leetcode.com/problems/linked-list-in-binary-tree/

```python
def isSubPath(self, head: ListNode, root: TreeNode) -> bool:
    if not head:
        return True
    if not root:
        return False
    return self.helper(head, root) or self.isSubPath(head, root.left) or self.isSubPath(head, root.right)


def helper(self, head: ListNode, root: TreeNode) -> bool:
    if not head:
        return True
    if not root:
        return False
    return (head.val == root.val) and (self.helper(head.next, root.left) or self.helper(head.next, root.right))

```

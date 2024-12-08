# Two Pointers

Здесь будут выкладываться задачи, помеченные тегом **Two Pointers** на сайте **LEETCODE**. Полный их список можно найти [здесь](https://leetcode.com/problemset/all/?topicSlugs=two-pointers).

# Список задач

+ [Longest Substring Without Repeating Characters](#longest-substring-without-repeating-characters)
+ [Container With Most Water](#container-with-most-water)
+ [3Sum](#3sum)
+ [3Sum Closest](#3sum-closest)
+ [4Sum](#4sum)
+ [Remove Nth Node From End of List](#remove-nth-node-from-end-of-list)
+ [Remove Duplicates from Sorted Array](#remove-duplicates-from-sorted-array)
+ [Remove Element](#remove-element)
+ [Implement strStr()](#implement-strstr)
+ [Substring with Concatenation of All Words](#substring-with-concatenation-of-all-words)
+ [Trapping Rain Water](#trapping-rain-water)
+ [Rotate List](#rotate-list)
+ [Sort Colors](#sort-colors)
+ [Minimum Window Substring](#minimum-window-substring)
+ [Remove Duplicates from Sorted Array II](#remove-duplicates-from-sorted-array-ii)
+ [Partition List](#partition-list)
+ [Merge Sorted Array](#merge-sorted-array)
+ [Valid Palindrome](#valid-palindrome)
+ [Linked List Cycle](#linked-list-cycle)
+ [Linked List Cycle II](#linked-list-cycle-ii)
+ [Longest Substring with At Most Two Distinct Characters](#longest-substring-with-at-most-two-distinct-characters)
+ [Two Sum II - Input array is sorted](#two-sum-ii-input-array-is-sorted)
+ [Minimum Size Subarray Sum](#minimum-size-subarray-sum)
+ [Palindrome Linked List](#palindrome-linked-list)
+ [3Sum Smaller](#3sum-smaller)
+ [Move Zeroes](#move-zeroes)
+ [Find the Duplicate Number](#find-the-duplicate-number)
+ [Reverse String](#reverse-string)
+ [Reverse Vowels of a String](#reverse-vowels-of-a-string)
+ [Intersection of Two Arrays](#intersection-of-two-arrays)
+ [Intersection of Two Arrays II](#intersection-of-two-arrays-ii)
+ [Sort Transformed Array](#sort-transformed-array)
+ [Longest Repeating Character Replacement](#longest-repeating-character-replacement)
+ [Circular Array Loop](#circular-array-loop)
+ [Max Consecutive Ones II](#max-consecutive-ones-ii)
+ [Longest Word in Dictionary through Deleting](#longest-word-in-dictionary-through-deleting)
+ [K-diff Pairs in an Array](#k-diff-pairs-in-an-array)
+ [Permutation in String](#permutation-in-string)
+ [Smallest Range Covering Elements from K Lists](#smallest-range-covering-elements-from-k-lists)
+ [Subarray Product Less Than K](#subarray-product-less-than-k)
+ [Candy Crush](#candy-crush)
+ [Partition Labels](#partition-labels)
+ [Most Profit Assigning Work](#most-profit-assigning-work)
+ [Count Unique Characters of All Substrings of a Given String](#count-unique-characters-of-all-substrings-of-a-given-string)
+ [Push Dominoes](#push-dominoes)
+ [Backspace String Compare](#backspace-string-compare)
+ [Longest Mountain in Array](#longest-mountain-in-array)
+ [Boats to Save People](#boats-to-save-people)
+ [Fruit Into Baskets](#fruit-into-baskets)
+ [3Sum With Multiplicity](#3sum-with-multiplicity)
+ [Long Pressed Name](#long-pressed-name)
+ [Binary Subarrays With Sum](#binary-subarrays-with-sum)
+ [Squares of a Sorted Array](#squares-of-a-sorted-array)
+ [Interval List Intersections](#interval-list-intersections)
+ [Subarrays with K Different Integers](#subarrays-with-k-different-integers)
+ [Max Consecutive Ones III](#max-consecutive-ones-iii)
+ [Statistics from a Large Sample](#statistics-from-a-large-sample)
+ [Intersection of Three Sorted Arrays](#intersection-of-three-sorted-arrays)
+ [Replace the Substring for Balanced String](#replace-the-substring-for-balanced-string)
+ [Count Number of Nice Subarrays](#count-number-of-nice-subarrays)

# Решения задач

## Longest Substring Without Repeating Characters

https://leetcode.com/problems/longest-substring-without-repeating-characters

## Container With Most Water

https://leetcode.com/problems/container-with-most-water

## 3Sum

https://leetcode.com/problems/3sum

## 3Sum Closest

https://leetcode.com/problems/3sum-closest

## 4Sum

https://leetcode.com/problems/4sum

## Remove Nth Node From End of List

https://leetcode.com/problems/remove-nth-node-from-end-of-list

## Remove Duplicates from Sorted Array

https://leetcode.com/problems/remove-duplicates-from-sorted-array

## Remove Element

https://leetcode.com/problems/remove-element

## Implement strStr()

https://leetcode.com/problems/implement-strstr

## Substring with Concatenation of All Words

https://leetcode.com/problems/substring-with-concatenation-of-all-words

```python
def findSubstring(self, s: str, words: List[str]) -> List[int]:
    if not words:
        return []
    wordLength = len(words[0])
    concatLength = wordLength * len(words)
    wordsStack = copy.copy(words)
    result = []
    for i in range(len(s) - concatLength + 1):
        for j in range(len(words)):
            currentWord = s[i + j * wordLength: i + (j + 1) * wordLength]
            if currentWord in wordsStack:
                wordsStack.remove(currentWord)
            else:
                break
        if not wordsStack:
            result.append(i)
        wordsStack = copy.copy(words)
    return result

```

## Trapping Rain Water

https://leetcode.com/problems/trapping-rain-water

```python
def trap(self, height: List[int]) -> int:
    if not height:
        return 0
    maxHeight = max(height)
    result = 0
    for i in range(1, maxHeight + 1):
        left = 0
        right = len(height) - 1
        while height[left] < i:
            left = left + 1
        while height[right] < i:
            right = right - 1
        # print(i, left, right, result)
        while left < right:
            if height[left] < i:
                result = result + 1
                # print(i,  height[left], left, right, result)
            left = left + 1
    return result


def trap(self, height: List[int]) -> int:
    result = 0
    for i in range(1, len(height)):
        left = height[i]
        for j in range(i):
            left = max(left, height[j])
        right = height[i]
        for j in range(i+1, len(height)):
            right = max(right, height[j])
        result = result + min(left, right) - height[i]
    return result

```

## Rotate List

https://leetcode.com/problems/rotate-list

## Sort Colors

https://leetcode.com/problems/sort-colors

```python
def sortColors(self, nums: List[int]) -> None:
    i = 0
    j = 0
    n = len(nums)-1
    while j <= n:
        if nums[j] < 1:
            nums[i], nums[j] = nums[j], nums[i]
            i = i + 1
            j = j + 1
        elif nums[j] > 1:
            nums[j], nums[n] = nums[n], nums[j]
            n = n - 1
        else:
            j = j + 1

```

## Minimum Window Substring

https://leetcode.com/problems/minimum-window-substring

## Remove Duplicates from Sorted Array II

https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii

```python
def removeDuplicates(self, nums: List[int]) -> int:
    slowPoint = 0
    fastPoint = 0
    while fastPoint < len(nums):
        if fastPoint < 2:
            fastPoint = fastPoint + 1
            slowPoint = slowPoint + 1
            continue
        if nums[fastPoint] > nums[slowPoint - 2]:
            nums[slowPoint] = nums[fastPoint]
            slowPoint = slowPoint + 1
        fastPoint = fastPoint + 1
    return slowPoint

```

## Partition List

https://leetcode.com/problems/partition-list

## Merge Sorted Array

https://leetcode.com/problems/merge-sorted-array

## Valid Palindrome

https://leetcode.com/problems/valid-palindrome

```python
def isPalindrome(self, s: str) -> bool:
    letters = "abcdefghijklmnopqrstuvwxyz1234567890"
    s = s.lower()
    left = 0
    right = len(s) - 1
    while left < right:
        while left < right and s[left] not in letters:
            left = left + 1
        while left < right and s[right] not in letters:
            right = right - 1
        if left < right and s[left] != s[right]:
            return False
        left = left + 1
        right = right - 1
    return True

```

## Linked List Cycle

https://leetcode.com/problems/linked-list-cycle

## Linked List Cycle II

https://leetcode.com/problems/linked-list-cycle-ii

## Longest Substring with At Most Two Distinct Characters

https://leetcode.com/problems/longest-substring-with-at-most-two-distinct-characters

## Two Sum II - Input array is sorted

https://leetcode.com/problems/two-sum-ii-input-array-is-sorted

```python
def twoSum(self, numbers: List[int], target: int) -> List[int]:
    numbers = [elem for elem in enumerate(numbers)]
    begin = 0
    end = len(numbers) - 1
    while begin != end:
        if numbers[begin][1] + numbers[end][1] == target:
            return [numbers[begin][0] + 1, numbers[end][0] + 1]
        elif numbers[begin][1] + numbers[end][1] < target:
            begin = begin + 1
        else:
            end = end - 1

```

## Minimum Size Subarray Sum

https://leetcode.com/problems/minimum-size-subarray-sum

## Palindrome Linked List

https://leetcode.com/problems/palindrome-linked-list

## 3Sum Smaller

https://leetcode.com/problems/3sum-smaller

## Move Zeroes

https://leetcode.com/problems/move-zeroes

```python
def moveZeroes(self, nums: List[int]) -> None:
    counter = 0
    i = 0
    while i < len(nums):
        if nums[i] == 0:
            nums.remove(0)
            counter = counter + 1
        else:
            i = i + 1
    nums = nums.extend([0]*counter)

```

## Find the Duplicate Number

https://leetcode.com/problems/find-the-duplicate-number

```python
for i in range(1, len(nums)):
    if nums[i] in nums[0:i]:
        return nums[i]


def findDuplicate(self, nums: List[int]) -> int:
    nums.sort()
    for i in range(len(nums) - 1):
        if nums[i] == nums[i + 1]:
            return nums[i]


def findDuplicate(self, nums: List[int]) -> int:
    tortoise = nums[0]
    hare = nums[0]
    tortoise = nums[tortoise]
    hare = nums[nums[hare]]
    while tortoise != hare:
        tortoise = nums[tortoise]
        hare = nums[nums[hare]]
    tortoise = nums[0]
    while tortoise != hare:
        tortoise = nums[tortoise]
        hare = nums[hare]
    return hare

```

## Reverse String

https://leetcode.com/problems/reverse-string

## Reverse Vowels of a String

https://leetcode.com/problems/reverse-vowels-of-a-string

```python
def reverseVowels(self, s: str) -> str:
    if not s or len(s) == 1:
        return s
    vowels = "AaEeIiOoUu"
    left = 0
    right = len(s) - 1
    resultLeft = []
    resultRight = []
    while left < right:
        while left < right + 1 and s[left] not in vowels:
            resultLeft.append(s[left])
            left = left + 1
        while left < right and s[right] not in vowels:
            resultRight.insert(0, s[right])
            right = right - 1
        if left < right and s[right] in vowels:
            resultLeft.append(s[right])
            resultRight.insert(0, s[left])
            left = left + 1
            right = right - 1
        if left == right:
            resultLeft.append(s[left])
    return ''.join(resultLeft + resultRight)

```

## Intersection of Two Arrays

https://leetcode.com/problems/intersection-of-two-arrays

## Intersection of Two Arrays II

https://leetcode.com/problems/intersection-of-two-arrays-ii

## Sort Transformed Array

https://leetcode.com/problems/sort-transformed-array

## Longest Repeating Character Replacement

https://leetcode.com/problems/longest-repeating-character-replacement

## Circular Array Loop

https://leetcode.com/problems/circular-array-loop

## Max Consecutive Ones II

https://leetcode.com/problems/max-consecutive-ones-ii

## Longest Word in Dictionary through Deleting

https://leetcode.com/problems/longest-word-in-dictionary-through-deleting

## K-diff Pairs in an Array

https://leetcode.com/problems/k-diff-pairs-in-an-array

## Permutation in String

https://leetcode.com/problems/permutation-in-string

## Smallest Range Covering Elements from K Lists

https://leetcode.com/problems/smallest-range-covering-elements-from-k-lists

## Subarray Product Less Than K

https://leetcode.com/problems/subarray-product-less-than-k

## Candy Crush

https://leetcode.com/problems/candy-crush

## Partition Labels

https://leetcode.com/problems/partition-labels

```python
def partitionLabels(self, S):
    last = {c: i for i, c in enumerate(S)}
    j = anchor = 0
    answer = []
    for i, c in enumerate(S):
        j = max(j, last[c])
        if i == j:
            answer.append(i - anchor + 1)
            anchor = i + 1
    return answer

```

## Most Profit Assigning Work

https://leetcode.com/problems/most-profit-assigning-work

```python
def maxProfitAssignment(self, difficulty, profit, worker):
    jobs = list(zip(difficulty, profit))
    jobs.sort()
    answer = 0
    i = 0
    best = 0
    for skill in sorted(worker):
        while i < len(jobs) and skill >= jobs[i][0]:
            best = max(best, jobs[i][1])
            i = i + 1
        answer = answer + best
    return answer

```

## Count Unique Characters of All Substrings of a Given String

https://leetcode.com/problems/count-unique-characters-of-all-substrings-of-a-given-string

## Push Dominoes

https://leetcode.com/problems/push-dominoes

## Backspace String Compare

https://leetcode.com/problems/backspace-string-compare

```python
def toString(self, S: str) -> str:
    result = []
    for elem in S:
        if elem != '#':
            result.append(elem)
        elif result:
            result.pop()
    return "".join(result)


def backspaceCompare(self, S: str, T: str) -> bool:
    return self.toString(S) == self.toString(T)

```

## Longest Mountain in Array

https://leetcode.com/problems/longest-mountain-in-array

```python
def longestMountain(self, A: List[int]) -> int:
    length = len(A)
    result = base = 0
    while base < length:
        end = base
        if end + 1 < length and A[end] < A[end + 1]:
            while end + 1 < length and A[end] < A[end + 1]:
                end = end + 1
            if end + 1 < length and A[end] > A[end + 1]:
                while end + 1 < length and A[end] > A[end + 1]:
                    end = end + 1
                result = max(result, end - base + 1)
        base = max(end, base + 1)
    return result

```

## Boats to Save People

https://leetcode.com/problems/boats-to-save-people

```python
def numRescueBoats(self, people: List[int], limit: int) -> int:
    people.sort()
    result = 0
    firstPoint = 0
    secondPoint = len(people) - 1
    while firstPoint <= secondPoint:
        result = result + 1
        if people[firstPoint] + people[secondPoint] <= limit:
            firstPoint = firstPoint + 1
        secondPoint = secondPoint - 1
    return result

```

## Fruit Into Baskets

https://leetcode.com/problems/fruit-into-baskets

```python
def totalFruit(self, tree: List[int]) -> int:
    blocks = [(k, len(list(v))) for k, v in itertools.groupby(tree)]
    answer = i = 0
    while i < len(blocks):
        types, weight = set(), 0
        for j in range(i, len(blocks)):
            types.add(blocks[j][0])
            weight = weight + blocks[j][1]
            if len(types) >= 3:
                i = j - 1
                break
            answer = max(answer, weight)
        else:
            break
    return answer

```

## 3Sum With Multiplicity

https://leetcode.com/problems/3sum-with-multiplicity

## Long Pressed Name

https://leetcode.com/problems/long-pressed-name

```python
def isLongPressedName(self, name: str, typed: str) -> bool:
    firstPoint = secondPoint = 0
    while secondPoint < len(typed):
        if firstPoint < len(name):
            previousLetter = name[firstPoint]
        else:
            return False
        while firstPoint < len(name) and secondPoint < len(typed) and name[firstPoint] == typed[secondPoint]:
            previousLetter = name[firstPoint]
            firstPoint = firstPoint + 1
            secondPoint = secondPoint + 1
        if secondPoint < len(typed) and typed[secondPoint] != previousLetter:
            return False
        else:
            while secondPoint < len(typed) and typed[secondPoint] == previousLetter:
                secondPoint = secondPoint + 1
    if firstPoint == len(name):
        return True
    else:
        return False

```

## Binary Subarrays With Sum

https://leetcode.com/problems/binary-subarrays-with-sum

```python
def numSubarraysWithSum(self, A: List[int], S: int) -> int:
    l = [0]
    for elem in A:
        l.append(l[-1] + elem)
    count = collections.Counter()
    result = 0
    for elem in l:
        result = result + count[elem]
        count[elem + S] = count[elem + S] + 1
    return result

```

## Squares of a Sorted Array

https://leetcode.com/problems/squares-of-a-sorted-array

```python
def sortedSquares(self, A: List[int]) -> List[int]:
    return sorted([x*x for x in A])

```

## Interval List Intersections

https://leetcode.com/problems/interval-list-intersections

```python
def isIntersected(self, A: List[int], B: List[int]) -> List[int]:
    if max(A[0], B[0]) <= min(A[1], B[1]):
        return [max(A[0], B[0]), min(A[1], B[1])]
    else:
        return None


def intervalIntersection(self, A: List[List[int]], B: List[List[int]]) -> List[List[int]]:
    if not A or not B:
        return []
    i = j = 0
    result = []
    while i < len(A) and j < len(B):
        if self.isIntersected(A[i], B[j]):
            result.append(self.isIntersected(A[i], B[j]))
        if A[i][1] < B[j][1]:
            i = i + 1
        else:
            j = j + 1
    return result

```

## Subarrays with K Different Integers

https://leetcode.com/problems/subarrays-with-k-different-integers

## Max Consecutive Ones III

https://leetcode.com/problems/max-consecutive-ones-iii

## Statistics from a Large Sample

https://leetcode.com/problems/statistics-from-a-large-sample

## Intersection of Three Sorted Arrays

https://leetcode.com/problems/intersection-of-three-sorted-arrays

## Replace the Substring for Balanced String

https://leetcode.com/problems/replace-the-substring-for-balanced-string

## Count Number of Nice Subarrays

https://leetcode.com/problems/count-number-of-nice-subarrays

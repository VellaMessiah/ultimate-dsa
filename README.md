# 🚀 ULTIMATE DSA
Your ultimate DSA interview cheat code — a no-fluff vault of the most frequently asked questions.  
If it’s not here, chances are, you won’t be asked.

A hand-picked compilation of questions from across top platforms — complete with clear explanations, multiple solution approaches, and a smart preparation roadmap.  
Direct practice links are included so you can sharpen your skills where it matters most.

---



### 🗺 High-Level Preparation Roadmap
Topics are grouped into **independent blocks**, but the blocks themselves should be tackled **in order** for maximum efficiency:

**Block 1** — Math, Arrays, Linked Lists, Stacks, Queues  
**Block 2** — Searching, Sorting, Hashing, Strings
**Block 3** — Heaps 
**Block 4** — Trees, Graphs  
**Block 5** — Design ( Combines all the above - especially important for Google)  
**Block 6** — Greedy, Dynamic Programming, Design  
**Block 7** — Hard Problems ( For Uber, Meta etc)


---



### ✅ Block-Wise Checklist (with Gist!)
A block-by-block list of problems with:
- **Links** to solve them directly.
- **Gist summaries** for lightning-fast revision — perfect for that final 1–2 day sprint before an interview.  
Decide whether to code them again based on your confidence and remaining time.

#### Block 1 Math, Arrays, Linked Lists, Stacks, Queues 

**Linked Lists**
 - Rearrangement is the name of the game here. Questions like reverse a linked lists ( constant memory), k-reverse linked lists, merge sort on linked lists - all require a mastery over the concept of rearrangement. I have attached images for Linked lists in particular to help visualize the re-arrangement so that you can memorize the concept instead of the code.
 - I cannot emphasise this enough. ALWAYS CREATE A DUMMY HEAD of the linked lists. Return Dummy head -> next if you have to but it is always easier to create a dummy head ( In the beginning just make this a practise and soon while solving some of the more advanced problems like LRU cache, you will see why I emphasised this)
 - Linked List questions can often benefit from having two pointers move at different speeds ( How about mid-point of a linked list? Cycle Detection?)
 - Linked List cyclicity is the other most important concept - hence I will clearly explain the algorithm and why it works? Learn the why part carefully - good companies with smart people and a good culture will ask this instead of asking fancy super-hard rated problems
 - The whole purpose of Linked lists is dynamic allocation to save memory so always practice every question in an O(1) space way - even if it means sacrificing Performance ( within reason)

_Reversing a Linked List: TITH Algorithm_
Assume first node is the dummy head. We are trying to do this visually:
<img width="2198" height="1256" alt="image" src="https://github.com/user-attachments/assets/1c52ac58-6485-4286-a24e-bd8f3537aa95" />
The algorithm roughly looks like:

After you understand why this works - for speed, you can memorize this algorithm

```
        ListNode* itr = dummyHead->next;
        ListNode* temp = NULL;
        while(itr && itr->next){
            temp = itr->next; // T
            itr->next = temp->next; // I
            temp->next = dummyHead->next; // T
            dummyHead->next = temp; // H
        }

        return dummyHead->next;
```
We can reverse the same algorithm to reverse a sublist! just perform the step in the loop n = size of sublist times!

_Linked List Cyclicity: Algorith and why it works_
The algo maintains two pointers. One moves twice the speed of other - if there is a cycle in the linked list, both will eventually enter the cycle and in the cycle, the faster pointer will catch up to it. If it does, we know for sure that there is a cycle. This is purely logical.

![floyd_cycle_finding](https://github.com/user-attachments/assets/dfc663e3-f843-41c4-8ed9-345755a930cf)

Finding the start of the cycle is where the algorithm gets tricky. It states that wherever the fast and slow pointers met, set a pointer there and another at the start of the list. Start moving them step by step. Where they meet is the start of the cycle.
Why does this work?
Assume that length from start of the list to the start of the cycle is X. From the start of the cycle to meeting point is Y and from meeting point to the start ( in forward direction) is Z. Length of cycle C  = Y + Z.
We need to prove that set the pointer at start and another at the collision point, the latter will loop around the circle a few times and then collide with the start of the loop.

or X = aC + Z


the slow pointer will never complete a full loop before the fast pointer catches it. The collision is guaranteed to happen during the slow pointer's first traversal of the loop.
Because every step, the the fast closes 1 space between them and worst case the space is C-1 ( when fast is just one step ahead when slow enters the loop). Fast will close this gap in C-1 seconds and in the same time slow will be 1 step behind completing the loop. Hence if slow cannot complete a circle in worst case, it cannot complete circle in any other case.

So, Distance covered by slow 
```
Dslow = X + Y
```

Fast loops around the circle a zero or more times before travelling Y more steps to meet fast
```
Dfast = X + nC + Y
```

Since fast moves 2x the speed of slow, 
```
2 X Dslow = Dfast
2X + 2Y = X + nC + Y
X + Y = nC
X = nC - Y
X = (n-1)C + (C-Y)
X = (n-1)C + Z
X = kC + Z
```

Distance travelled by fast pointer

They can only meet at the start of the cycle if for some number n X = n(C) + Z. If we can prove this equation, then we have proof that the algorithm works. 

| Problem Name | Link | Gist |
|---|---:|---|
| Reverse a Linked List | [Reverse a Linked List](https://leetcode.com/problems/reverse-linked-list/description/) | Algo shared above |
| Reverse a Linked List II | [Reverse a Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/description/) | Gist shared above - use dummy head to get to the start element and then perform the iteration right-left times|
| K reverse Linked List | [K Reverse Linked List](https://leetcode.com/problems/reverse-nodes-in-k-group/description/) | Use dummy head and perform k-1 reversals at a time, but we need to reach the start of the next group - store the next pointer before reversal - after reversal this will be at the end of that group. Now about the remainder group at the end, can we check if num of reversals performed < k-1? If yes, just reverse it back out | 
| Remove Nth node from end of List| [Remove Nth from End](https://leetcode.com/problems/remove-nth-node-from-end-of-list/description/) | Use a pointer with a N headstart and another pointer  |
| Linked List Cycle | [Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/description/) | Algo discussed above |
| Start of Cycle Linked List | [Remove Cycle](https://leetcode.com/problems/linked-list-cycle-ii/description/) | Algo discussed above |
| Middle of Linked List | [Middle](https://leetcode.com/problems/middle-of-the-linked-list/description/) | Can we use fast and slow pointers here?|
| Check if Linked List is a Palindrom | [Palindrome List](https://leetcode.com/problems/palindrome-linked-list/description/) | use concepts from Midpoint and reverse here | 
| Reorder Linked List | [Reorder List ](https://leetcode.com/problems/reorder-list/description/) | Find the element just before midpoint, reverse list from here and disconnect two halves and then interleave the lists |
| Sort a Linked List | [Sort List](https://leetcode.com/problems/sort-list/description/) | Combine concepts of midpoint and merge 2 sorted lists to perform this -> remember when you call merge sort on left and right to reassign the headers h1 = mergeSort(h1), h2 = mergeSort(h2) return mergeTwoSortedLists(h1,h2)|
| Copy List with Random Pointer | [Copy List with Random Pointer](https://leetcode.com/problems/copy-list-with-random-pointer/description/) | Culmination of all rearrangement questions - uses all the concepts|
| Flatten a 2d List | [Flatten a Multilevel Doubly Linked List](https://leetcode.com/problems/flatten-a-multilevel-doubly-linked-list/description/) | Can we leveragethe concept of merge sort or recursion here? | 
| Merge k sorted lists | [Merge K sorted lists](https://leetcode.com/problems/merge-k-sorted-lists/description/) | We should do both a compute optimized and a space optimized way | 

**Queues**
| Problem Name | Link | Gist |
|---|---:|---|
| Reverse first k elements in a queue | [Reverse K](https://www.geeksforgeeks.org/problems/reverse-first-k-elements-of-queue/1) | 
| Sliding Window Maximum | [Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/) | Do not pay attention to the difficulty. This is a medium problem at worse - just a very common pattern in queues - BE CAREFUL WHILE POPPING FROM QUEUE COMPARING WITH CURRENT - DO NOT USE <= as this creates complications on repeat elements - we want to main both copies of repeats in the queue - think example - [7,5,7,1,6,0], k = 3|
|Sum of min and max of subarrays of size k| [Sum of Min Max](https://www.geeksforgeeks.org/dsa/sum-minimum-maximum-elements-subarrays-size-k/) | Just need two queues maintaining sliding max and min respectively |

**Stacks**
- These are used when we want to analyze a linear sequence but lookback closed characters first
- Consider a stack when a solution depends on resolving the most recent state before or after the current state
  
| Problem Name | Link | Gist |
|---|---:|---|
|Remove All adjacent duplicates | [Remove all adjacent duplicates](https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string/description/) | Check if stack top is duplicate with current, if yes keep popping. Push to stack if you did not perform any pop |
| Simplify Directory Path | [Simplify Path](https://leetcode.com/problems/simplify-path/description/) | Be careful of the several edge cases here namely: We have to take care not to push empty string or "." or ".." unto stack, then when removing trailing '/' we have to make sure the string isn't simply "/" |
| Sort a stack using another stack| [Sort stack](https://www.geeksforgeeks.org/dsa/sort-stack-using-temporary-stack/) | |
| Min stack | [Min stack](https://leetcode.com/problems/min-stack/description/) |  Whenever we want to store two numbers in the same place, we apply some trick. Remember the trick we applied for A[i]=A[A[i]]. Here if x<y, x + x < x+y , 2x-y < x. Therefore if we get a minimum < current minimum, we can push 2*min - cur_min unto stack. Whenever the stack's top is < the minimum, we know the minimum is getting removed. Then top = 2*cur_min - prev_min. prev_min = 2*cur_min - top, thus we can easily get the prev min. Only thing is what we try to push INT_MAX? Can we operate with longs instead then? |
| Redundant Brackets | [Redundant Brackets](https://www.interviewbit.com/problems/redundant-braces/) | Generally the way to handle brackets is start computing as soon as you encounter a closed bracket. Now when is a bracket redundant? ((a+b)) => we encounter only 1 expression between brackets when we reach the outer bracket = redundant. (a + (a+b)) = 2 expressions in outermost brackets = not redundant. |
| Evaluate Post Fix Expression| [Evaluate Reverse Polish Expression](https://leetcode.com/problems/evaluate-reverse-polish-notation/description/) | Every operator operates on the nearest two previous operands available ( these operands can be result of a previous operation too) |
| Infix to PostFix | [Infix to Postfix](https://www.geeksforgeeks.org/problems/infix-to-postfix-1587115620/1) | |
| Basic Calculator II | [Basic Calculator II](https://leetcode.com/problems/basic-calculator-ii/description/) | |
| Basic Calculator III | [Basic Calculator III](https://leetcode.com/problems/basic-calculator-iii/description/) | | 
| Nearest Smaller Element| [Nearest Smaller Element](https://www.interviewbit.com/problems/nearest-smaller-element/) | if array = a...b and b<a then for any element post a cannot be the nearest smaller element on the left hence we can completely discard|
| Largest Rectangle in a Histogram | [Largest Rectangle](https://leetcode.com/problems/largest-rectangle-in-histogram/description/) | The largest rectangle that can be formed with a bar in the histogram is (dist between next smaller on left and right) * (height of the bar)| 
| MAX MIN | [Sum of differences of max and min of all subarrays](https://www.geeksforgeeks.org/dsa/sum-of-absolute-difference-of-maximum-and-minimum-of-all-subarrays/)| |
| Max XOR | [Find maximum value of XOR of max and 2nd max amongst all subarrays ](https://www.scaler.com/academy/mentee-dashboard/class/20833/homework/problems/1157?navref=cl_tt_lst_nm) | |

#

#### Block 2 - Strings, Hashing, Searching, Sorting

**Hashing**
- Most basic form of key-value memorization

| Problem Name | Link | Gist |
|---|---:|---|
| Subarray sum equals k| [Subarray sum equals k](https://leetcode.com/problems/subarray-sum-equals-k/) | We know given a array with prefix sums, sum of subarray between i..j = prefix[j] - prefix[i-1]. So if prefix[j] - prefix[i-1] ==k for some i,j where i<j then prefix[i-1] = prefix[j] -k. Therefore if we track prefix sum of array and find if prefix_sum -k can also be found previously as prefix sum in any point in the array then we can increment answer by the number of times we found that sum. Can you store prefix sums in hash table to make this easier? |
| Find the longest subarray with sum 0 | [Longest with sum 0 ](https://www.geeksforgeeks.org/problems/largest-subarray-with-0-sum/1)| Same principles as above but maybe only store the index instead of count this time? And that too the first occurence so we get the leftmost element with sum = prefix -k? Edge case: Account for a prefix subarray of sum zero ( perhaps hash firstOccurencr[0] as -1? |
| Longest Consecutive Sequence | [Longest Consecutive Subsequence](https://leetcode.com/problems/longest-consecutive-sequence/description/) | append count of the series to terminal ends. Take special care of edge cases: what if an element is repeated? what if a middle element is repeated? |
| Distinct Numbers in Window | [Distinct Numbers in Window](https://www.interviewbit.com/problems/distinct-numbers-in-window/) | Simple hash question, every time you increase count of current also reduce count of i-Bth element. If count of it is <=0, remove it. At every point size of hash map is the answer |
| Relative Sort Array | [Relative Sort Array](https://leetcode.com/problems/relative-sort-array/description/) | store ranks according to second array in hash map. Now how we use these ranks in std::sort ? use lambda capture syntax |
| Count Right Triangles | [Count Right triangles](https://www.geeksforgeeks.org/dsa/count-of-right-angled-triangle-formed-from-given-n-points-whose-base-or-perpendicular-are-parallel-to-x-or-y-axis/) | |
| Count Rectangles | [Count Rectangles Gfg](https://www.geeksforgeeks.org/dsa/count-of-pairs-from-arrays-a-and-b-such-that-element-in-a-is-greater-than-element-in-b-at-that-index/) | Use concepts from right triangle here |
| Longest substring without repeat | [Longest substring without repeating characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/) | |
| Max points on a line | [Max points on a line ](https://leetcode.com/problems/max-points-on-a-line/description/)| | 
| Minimum Window substring | [Min Window](https://leetcode.com/problems/minimum-window-substring/description/) | |
| Compare sorted subarrays | [Compare sorted subarrays](https://www.scaler.com/academy/mentee-dashboard/class/18030/homework/problems/522?navref=cl_tt_lst_nm)| The concept of rolling hashes !|


**String**
- There is only one pattern of "string" problems and that is pattern-matching in linear time. Any other problem is an array problem.
- For pattern matching, there are only two algorithms both are unintuitive and require memorization with the latter requiring knowledge on rolling hashes ( and being slightly more intuitive) - 1) Z-Algorithm 2) Rabin Karp Algorithm. Yes, I know there are other algorithms like KMP but I'm sorry if I'm learning an algorithm, it better be the shorter one like Z.
- The one advantage that rolling hashes offer is less space utilization
- Yet another non-sensical algorithm called Manacher's algorithm exists. It is for a very very specific use case of finding palindromes in the middle of a string. No need to learn this. For most cases using Rabin Karp siffuces ( see Shortest Palindrom below)

_Explanation of Rabin Karp Algorithm_

Rabin–Karp uses **rolling hashes** for efficient substring search.
- **Hash of substring** \([l,r]\):  
  \[
  H[l,r] = \sum_{i=l}^{r} s[i]\cdot p^i
  \]  
  where \(p\) is a prime base (e.g., 23).

- _Properties_:  
  \[
  H[l,r] = H[l,r-1] + H[r,r], \quad H[l,r] = H[l-1,r]-H[l-1,l-1]
  \]  

- **Sliding the window** (shift by 1):  
  \[
  H_{new} = H_{prev}\cdot p
  \]

- **Modular arithmetic**: Use a large prime modulus (e.g., \(10^9+7\)) to prevent overflow.

At iteration \(i\) (window ending at \(i\), pattern length \(M\)):

\[
H_r = (H_r - s[i-M]\cdot p^{i-M} + MOD)\bmod MOD
\]  
(remove char leaving window)

\[
H_r = (H_r + s[i]\cdot p^i)\bmod MOD
\]  
(add new char entering window)

\[
H_p = (H_p\cdot p)\bmod MOD
\]  
(update pattern hash)

Finally, compare **\(H_r\)** and **\(H_p\)**.

| Problem Name | Link | Gist |
|---|---:|---|
| String Pattern matching | [Find first occurence of string](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/description/) | Standard pattern matching algorithm - use any of Rabin Karp or Z Algorithm|
| Shortest Palindrome | [Shortest Palindrome](https://leetcode.com/problems/shortest-palindrome/description/) | Use rolling hashes or pattern matching algorithms to do this. Main a running forward and reverse hash, keep updating limit whenever they are equal. Your answer is reverse(substr(lim,end)) + ans|

**Sorting**
- Sometimes order the elements is the clear way to go. Whenever you observe a Linear Sequence, one of the options when you think algorithmically is 'Can I do this efficiently if the linear sequence was sorted?'
- Know the following algorithms really well: Merge Sort, Quick Sort, Quick Select ( For tutorials on the same - Refer Stanford DSA videos)
- Merge Sort in particular due to it's divide and conquer nature offers other advanced applications like counting inversions in an Array! The intuition here is if I had the array in current order as well as sorted order and I could compare both, then would my solution become simpler?
- Do not bother with in-place merge sort, it is slower.
- Unless asked to implement sort, just use your in-built sorting algorithm and obviously know what it does underneath. For instance std::sort is introsort, a hybrid of quicksort, heapsort, and insertion sort. Should be ideally nLogn
- Pivot Randomization is very important in Quicksort/Quickselect algorithms. Some test cases are designed to fail on selecting the first or last element all the time. To get a random number use the below piece of code
```
srand((unsigned int)time(0)) // Seed random with current time
int pivot = rand()%(y-x+1) + x
```
- Also in merge sort/quick-sort, never use >= or <= but always use strict > or < as it can have disastrous results ( Take quick select over [99,99] for instance, you get stuck in a loop )
- Know how to sort an array of custom objects or custom sorting logic over primitives in your language of choice

| Problem Name | Link | Gist |
|---|---:|---|
|Kth Smallest Element | [Kth Largest Element](https://leetcode.com/problems/kth-largest-element-in-an-array/description/) | Simple Quick select |
|MaxMod | [MaxMod](https://www.geeksforgeeks.org/dsa/find-the-maximum-possible-value-of-ai-aj-over-all-pairs-of-i-and-j/) | If a%b is [0,b-1], and if b>a then a%b is always a. If you then think about it, isn't this always the second largest element ( not equal to the largest )? Now it just about handling the edge case|
|Largest Number |[Largest Number](https://leetcode.com/problems/largest-number/description/) | Custom Sorting: string(n1)+string(n2)>string(n2)+string(n1). Just be sure to handle the edge case where every element is 0.|
|Inversion Count | [Count Inversions](https://www.hackerrank.com/challenges/ctci-merge-sort/problem) | Merge Sort with extra computation. When we merge the sorted halves if i is in first half and j is in second half and  A[i]>A[j] then inversions = inversions + (m-i+1). An important point to consider is why are we incrementing inversion count by (m-i+1) and not (j-m) ? Think via example! Consider two sorted arrays 3,5,7 | 1,4,8 . If we consider only j-m then we would be counting only 1 for when we are at the first element of both arrays which is incorrect since all elements of left are greater than the first element, we should be counting 3! | 
| K closest points to origin | [K closest](https://leetcode.com/problems/k-closest-points-to-origin/) | Custom sorting - can be done more efficiently with a heap| 
| Reverse Pairs | [Reverse Pairs](https://leetcode.com/problems/reverse-pairs/) |  Like Count inversions except we need to do two loops over the sorted half. Once will count the reverse pairs and other will actually merge the sorted arrays |
| Sum of max or number of such sequences difference accross all subsequences | [Number of Subsequences That Satisfy the Given Sum Condition](https://leetcode.com/problems/number-of-subsequences-that-satisfy-the-given-sum-condition/description/) | |
| Maximum Unsorted Subarray | [Maximum Unsorted Subarray](https://leetcode.com/problems/shortest-unsorted-continuous-subarray/description/) | This looks simple but is deceptive. It is not simply about find the first and last unsorted element. For instance consider 4,13,15,17,13,17. Trivial algos would return incorrect solution here. Find the rightmost element by tracking max in the forward loop and then leftmost element by tracking min in a reverse loop.|

#

#### Block 3 - Heaps
- To Declare a min Heap of integers
```
priority_queue<int, vector<int>, greater<int>> minQ
```
- To Declare a heap on a custom class, we need a Compare class with a public implementation of the operator() method. Note that the condition must be reverse of what you would provide while custom sorting.
For instance the below piece of code can be used to declare a max heap of vector<int> where each vector is a point on x-y plane and we consider distance of the point from origin as the criteria for max heap
```
long dist(const vector<int> &v){
    return v[0]*v[0] + v[1]*v[1];
}

class Compare {
public:
    bool operator()(vector<int>&v1, vector<int>&v2){
        return dist(v1) < dist(v2);
    }
};

priority_queue<vector<int>, vector<vector<int>>, Compare> maxQ;
```

#

#### Block 4 - Trees and Graphs
**Trees**
| Problem Name | Link | Gist |
|---|---:|---|
| Binary Tree from inorder and preorder| [Binary Tree from inorder and postorder](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal) | Imagine if we were to construct a tree only from preorder. Then first element would be root and then we would need to know the number of elements in the left subtree at each step. Imagine the same for inorder. At every step if we were told the position of the root, we would be able to split the array into left and right subtree. Now isn't the first element of preorder traversal the root? We can find the root in the inorder traversal. This allows us to find the number of elements in the left subtree and right subtree. We use this information to then recurse further. Remember, in such questions: inorder is only dependant on root while preorder or postorder's next recursion is dependant on number of elements only  |
| Binary Tree from inorder and postorder | [Binary Tree from inorder and postorder](https://leetcode.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal/description/) | Same as above, except we determine the number of element in the right subtree first. |
| Lowest Common Ancestor | [LCA](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/description/) | If we put traversal data of two nodes in a stack, wouldn't LCA be the first equal node? |

**Graphs**
| Problem Name | Link | Gist |
|---|---:|---|
| Word Ladder | [Word Ladder](https://leetcode.com/problems/word-ladder/description/) | |
| Word Ladder II | [Word Ladder II](https://leetcode.com/problems/word-ladder-ii/description/)

#

#### Block 5 - Design
- Python specific tip since a lot of questions require a sorted container. Use heapq module with heapify, heappush, heappop. Remember when you need a max heap, use negatives. Heaps can be declared with list of tuples, in which case python compares element by element left to right.
- Use bisect.insort_left or bisect.insert_right to insert into sorted lists.


| Problem Name | Link | Gist |
|---|---:|---|
| LRU Cache | [LRU Cache](https://leetcode.com/problems/lru-cache/description/) | You should probably do hash maps. if you haven't - do that first and then come back to this question. We can design this as Doubly Linked List + HashMap to search Keys. head->next is always the lru key and tail is the most recent. Caveats: What if the value you are trying to move is already the tail? Do not increment size on put() if key exists. For safety, do not remove lru if head->next is null already. Do not forget to change the value in the node when put() is valled to the value in the argument. When removing the LRU node, do not forget to remove it from the search index too  |
| Max Frequency Stack| [Max Frequency Stack](https://leetcode.com/problems/maximum-frequency-stack/description/)| |
| Design a Circular Queue | [Design a circular queue](https://leetcode.com/problems/design-circular-queue/) | Yes this is a question of just managing a fixed size array with 2 pointers for start and end. Remember that modular arithemetic is very useful here ( remember (-a )%b is (-a + b)%b ) But edge cases are very important here. For simplicity we init start and end at 0. This means start = where the start element is going to be. end = where the end element is going to be. The readjustment in both operations can be summarized as follows: When the queue was empty and one element just enqueued, start must be the end element. Now since start and end start from the same index, we can keep enqueue logic as -> (increment end, set arr[end] = enqueued value, if queue was empty previously, set start = the new end )|
| Design a Circular Dequeue | [Design a circular Deque](https://leetcode.com/problems/design-circular-deque/description/?envType=problem-list-v2&envId=design)| The edge case from circular queue really blows up here. If the concern is that on 0 or 1 elements, the start and end should align, why don't we encapsulate that in a function and call it at the end of each kind of insertion or deletion? Also Modular arithmetic is much more useful here. Since both front boundary and end boundary can shrink.  |
| Design a hit counter | Design a hit counter | queue to keep a track of hits. on each getHits() call, clean up older hits out of threshold. size of queue is the hits |
| Logger Rate Limiter | [Logger Rate Limiter](https://leetcode.com/problems/logger-rate-limiter/?envType=problem-list-v2&envId=data-stream) |  Since messages are coming in chronologically, you need not a data structure that maintains items in sorted form, a FIFO linear data structure where popping from one end is O(1) needed -> queue. We can also maintain a hash table ( Only set) of values within the threshold window. At the start of every call, clean up from queue and hash table all the values out of threshold. If the message attempted is present in hash table then it was attempted within threshold and cannot be printed else it should be-> Then add an item to the end of the queue and in hash table and print the message |
| Stock fluctuation | [Stock Price Fluctuation](https://leetcode.com/problems/stock-price-fluctuation/description/) | We need ability to search a key ( timestamp ) easily hence a hash table. Then against each key we need a sorted store of values hence sorted set or BST. Given an update, remove that node from tree if it exists and then put the updated or new value in the sorted store|
| Time-based Key-value store | [Time based KV store](https://leetcode.com/problems/time-based-key-value-store) | We need to easily search a key so Hash. But we need a sorted by timestamp listed of values for each key-> how about a BST?. Then value for a timestmap t is the one previous of upper_bound(t). Since you are using upper_bound Be careful of the limits here. If timestamp being queried is less than min Ts available for the key, then value is "". Similarly is it is being searched for a value > max ts available, then value is the one corresponding to max ts. During set, handle the case where key doesn't exist |
| Design Memory Allocator | [Design Memory Allocator](https://leetcode.com/problems/design-memory-allocator) | |
| Design a Trie | | |
| Search Autocomplete system | [Design Autocomplete System](https://leetcode.com/problems/design-memory-allocator) | |
| Online Stock span | [Stock Span](https://leetcode.com/problems/online-stock-span) | If let's say prices and spans given p1,s1 p2,s2 and now we get a price p3. If p3 > any previous price  say p2 then that previous price becomes irrelevant as a) any price p4 > p3 will also be >p2. b) The condition that p4<p3 but p4>p2 is irrelevant as we are only considering consecutive backwards days. so if condition fails at p3 then p2 is irrelevant. Hence this is a natural candidate for stacks! use stack to store pairs of prices and spans! Pop from stack on a new price and keep adding spans from the popped elements. Add back the current price and span to stack |
| Design Browser History | [Design Browser History](https://leetcode.com/problems/design-browser-history/) | This is a simple doubly linked list use-case but instead we only maintain pointers for current node and head. Now, take special care of the boundaries as forward can be > the number pages available ahead and back can be > number of pages available previously.|
| Design URL shortener | [Encode and Decode TinyURL](https://leetcode.com/problems/encode-and-decode-tinyurl/) | This is a simple problem of hashing and store short to long URL mappings. Now hash() usually produces a very large string/int depending on the algorithm used ( like sha1 etc). This wastes a lot of space. Remember there are 62 different characters available and event at 7 character length we can store about 60 billion strings. So we don't need a very large string. at average 40 bytes ( calculated using example URL provided) per URL and 1 GB memory assumed, we can only store about 25 million strings. Now there are two such ways available. One is do base 62 encoding -> this will always produce a small result. Other is hash to a int or simplest has available, then take first n digits. Assuming a space of 100 million ( since we need to store upto 25 million strings) = 10^8 or 8 digit hash of numbers [0-9]. This is much simpler. However, we need to handle collisions here. Thus keep hashing till you get a collision free result. Collision should be highly improabable in in a 9 digit number anyway. |
| Design Twitter | [Design Twitter](https://leetcode.com/problems/design-twitter/submissions/1770953176/) | The caveat here is that published tweets are not necessarily in chronological order so a tweet with greater tweet_id could be older. Now you need: 1) a fast access to sorted set of tweets of each user -> You can use a hash map of user_id to list of (timestamp, tweet_id). use bisect.insert_left to add to this. 2) Fast access to user's follows NOT followers in unordered form ( use a hash map of user_id to hash set of follows). 3) When getting the news feed, create a heap of iterators to each follow's + the user's tweets starting last index. so heap will contain tuple of (-timestamp, tweet_id, index, user_id). -timestamp for max heap according to timestamp. tweet_id for adding to list of news feed, index and user_id to access tweets of the user_id at index-1 for pushing back into heap ( Yes this is very similar to merge k sorted lists)  |
| Design a Tree Iterator | | |
| Two-sum BST using Tree Iterator | | |
| Evaluate Division | | |
| Design Front Middle Back Queue | [Front Middle Back Queue](https://leetcode.com/problems/design-front-middle-back-queue/submissions/1771652900/) | Maintain 2 queues with left being larger by upto 1 size. Manage popping, pushing and middle based on even or odd size|
| Insert Delete Get Random | | |
| Simple Bank System | [Simple Bank System](https://leetcode.com/problems/simple-bank-system/) | The only thing that matters here is locking since that is the only thing the interviewer would be concerned about. Now one simple approach is lock the entire system. But this is pretty bad for performance. How about we have an individual lock for each account and only lock the accounts necessary? |
| Design a Leaderboard | [Design Leaderboard](https://leetcode.com/problems/design-a-leaderboard)  | You need a sorted container of scores and player ids ( multiset should work here - you will need a custom compare class). Also you need to search by a playerId, so can maintain a hash of playerId to multiset iterator. Now One thing you need to watch out for is that scores are additive if existing. |
| Design a Log Storage System | [Design Log Storage System](https://leetcode.com/problems/design-log-storage-system/) | You can create a Container class for timestamps that gives lower and upper limit representations for the granularity. Add a comparator in it and you can no maintain timestamps in a sorted container. Maintain pairs or tuples of Timestamps and ids and return lower_limit(start_ts), upper_limit(end_ts)|
| Design a File System | [Design File System](https://leetcode.com/problems/design-file-system/description/) | Classic Trie Question. The only problem is the edge cases. If the child is not found during createPath, create it if it is the last token, else return False. In the end it is important to return false since we are to return false if path already exists. For get, keep updating the return value starting from -1 as you keep traversing |
| Find pairs with certain sum | [Finding Pairs With a Certain Sum](https://leetcode.com/problems/finding-pairs-with-a-certain-sum) | |
| Flatten Nested List Iterator | [Flatten Nested List Iterator](https://leetcode.com/problems/flatten-nested-list-iterator) | |
| Design a Task Manager | [Design a Task Manager](https://leetcode.com/problems/design-task-manager/description/?envType=problem-list-v2&envId=design) | Need a sorted container ( multiset) of Task struct sorted by priority first and then taskId. Also need a hash map of Task id to multiset iterator.|
| Snapshot Array | [Snapshot Array](https://leetcode.com/problems/snapshot-array/description/?envType=problem-list-v2&envId=design) | You need for each index, a list of sorted pairs of snap_id, value sorted by first. Or a map<int,int>. When querying for a key, if empty or min_key is greater than the snap queried for, return default value (0) or return the upper_bound snap -1 's value|
| Throne Inheritance | [Throne Inheritance](https://leetcode.com/problems/throne-inheritance) | |



#

#### Block 6 Greedy, Dynamic Programming
**Greedy**
- Remember when given a sequence of numbers or intervals that sorting a certain way could lead to an optimal answer
- If sorting is not an option and we are given a sequence, perhaps we can use a stack or a queue to remove unoptimal elements?
- If you cannot solve the Greedy question outright, try with DP first! Most of the times this works. Then try to optimize the DP question to Greedy

| Problem Name | Link | Gist |
|---|---:|---|
| Jump Game | [Jump Game](https://leetcode.com/problems/jump-game/) | Track the furthest reachable index in linear time. |
| Gas Station | [Gas Station](https://leetcode.com/problems/gas-station/) | If total gas ≥ total cost a solution exists; track running surplus to find the start. |
| Jump Game II | [Jump Game II](https://leetcode.com/problems/jump-game-ii/) | Think like BFS — greedy expansion by range to minimize jumps. |
| Remove Duplicate Letters | [Remove Duplicate Letters](https://leetcode.com/problems/remove-duplicate-letters/) | Use a stack to maintain lexicographically smallest result while ensuring required counts remain. |
| Wiggle Subsequence | [Wiggle Subsequence](https://leetcode.com/problems/wiggle-subsequence/) | Can be solved greedily (track up/down slopes) or with DP. |
| Remove K Digits | [Remove K Digits](https://leetcode.com/problems/remove-k-digits/) |Greedy + stack: pop larger previous digits when a smaller digit appears to minimize leftmost digits, then strip leading zeros. |
| Queue Reconstruction by Height | [Queue Reconstruction by Height](https://leetcode.com/problems/queue-reconstruction-by-height/) | |
| Non-overlapping Intervals | [Non-overlapping Intervals](https://leetcode.com/problems/non-overlapping-intervals/) | Sort by end time and greedily choose intervals that finish earliest. |
| Minimum Number of Arrows to Burst Balloons | [Minimum Number of Arrows to Burst Balloons](https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons/) | Interval greedy: sort by end coordinate and pick minimally overlapping groups. |
| Task Scheduler | [Task Scheduler](https://leetcode.com/problems/task-scheduler/) | Model as filling slots determined by most frequent task; use math or heap to compute idle slots. |
| Maximum Length of Pair Chain | [Maximum Length of Pair Chain](https://leetcode.com/problems/maximum-length-of-pair-chain/) | Sort by end and greedily pick non-overlapping pairs (earliest finish first). |
| Split Array into Consecutive Subsequences | [Split Array into Consecutive Subsequences](https://leetcode.com/problems/split-array-into-consecutive-subsequences/) | |
| Maximum Swap | [Maximum Swap](https://leetcode.com/problems/maximum-swap/) | Swap the leftmost number with the maximum number on the right. |
| Monotone Increasing Digits | [Monotone Increasing Digits](https://leetcode.com/problems/monotone-increasing-digits/) |  |
| Partition Labels | [Partition Labels](https://leetcode.com/problems/partition-labels/) | |
| Reorganize String | [Reorganize String](https://leetcode.com/problems/reorganize-string/) |  |
| Increasing Triplet Subsequence | [Increasing Triplet Subsequence](https://leetcode.com/problems/increasing-triplet-subsequence/) |  |
| Max Increase to Keep City Skyline | [Max Increase to Keep City Skyline](https://leetcode.com/problems/max-increase-to-keep-city-skyline/) | |
| Score After Flipping Matrix | [Score After Flipping Matrix](https://leetcode.com/problems/score-after-flipping-matrix/) |  |
| Hand of Straights | [Hand of Straights](https://leetcode.com/problems/hand-of-straights/) |  |
| Minimum Add to Make Parentheses Valid | [Minimum Add to Make Parentheses Valid](https://leetcode.com/problems/minimum-add-to-make-parentheses-valid/) | Maintain counter for unmatched left, if this drops below zero, add to answer and reset to zero. Add this counter to the ans at the end |
| Advantage Shuffle | [Advantage Shuffle](https://leetcode.com/problems/advantage-shuffle/) |  |
| Minimum Increment to Make Array Unique | [Minimum Increment to Make Array Unique](https://leetcode.com/problems/minimum-increment-to-make-array-unique/) | |


#

#### Block 7 Hard Problems

| Problem Name | Link | Gist |
|---|---:|---|
| Median of 2 sorted arrays | [Median of two sorted arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/description/) | Number of elements in the left-half ( including median) of a sorted array is (N+1)/2. Additionally all the elements in the left half are <= right half. Thus we can just binary search over the number of elements to include from first array, let's say m1. Then the number of elements to include from the other array is m2  = (N+1)/2 - m1. Now we must compare the boundaries i.e take the element on the boundries ( m1-1 and m2-1) is a and b. The elements just beyond the boundary ( m1 and m2) is c and d. Then a<=d and b<=c, If yes, we can find our median ( odd = max(a,b), even = (max(a,b) + min(c,d))/2 |

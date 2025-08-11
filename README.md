# 🚀 ULTIMATE DSA
Your ultimate DSA interview cheat code — a no-fluff vault of the most frequently asked questions.  
If it’s not here, chances are, you won’t be asked.

A hand-picked compilation of questions from across top platforms — complete with clear explanations, multiple solution approaches, and a smart preparation roadmap.  
Direct practice links are included so you can sharpen your skills where it matters most.

---



### 🗺 High-Level Preparation Roadmap
Topics are grouped into **independent blocks**, but the blocks themselves should be tackled **in order** for maximum efficiency:

**Block 1** — Math, Arrays, Linked Lists, Stacks, Queues  
**Block 2** — Searching, Sorting, Hashing  
**Block 3** — Strings  
**Block 4** — Trees, Graphs  
**Block 5** — Greedy, Dynamic Programming, Design  


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

_Reversing a Linked List_
Assume first node is the dummy head. We are trying to do this visually:
<img width="2198" height="1256" alt="image" src="https://github.com/user-attachments/assets/1c52ac58-6485-4286-a24e-bd8f3537aa95" />
The algorithm roughly looks like:

After you understand why this works - for speed, you can memorize this algorithm

```
        ListNode* itr = dummyHead->next;
        ListNode* temp = NULL;
        while(itr && itr->next){
            temp = itr->next;
            itr->next = temp->next;
            temp->next = dummyHead->next;
            dummyHead->next = temp;
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

They can only meet at the start of the cycle if for some number n X = n(C) + Z. If we can prove this equation, then we have proof that the algorithm works. 

| Problem Name | Link | Gist |
|---|---:|---|
| Reverse a Linked List | [Reverse a Linked List](https://leetcode.com/problems/reverse-linked-list/description/) | Algo shared above |
| Reverse a Linked List II | [Reverse a Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/description/) | Gist shared above - use dummy head to get to the start element and then perform the iteration right-left times|
| K reverse Linked List | [K Reverse Linked List](https://www.scaler.com/academy/mentee-dashboard/class/18036/assignment/problems/380?navref=cl_tt_lst_nm) | Use dummy head and perform k reversals at a time | 
| Remove Nth node from end of List| [Remove Nth from End](https://leetcode.com/problems/remove-nth-node-from-end-of-list/description/) | Use a pointer with a N headstart and another pointer  |
| Linked List Cycle | [Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/description/) | Algo discussed above |
| Start of Cycle Linked List | [Remove Cycle](https://leetcode.com/problems/linked-list-cycle-ii/description/) | Algo discussed above |
| Reorder Linked List | [Reorder List ](https://leetcode.com/problems/reorder-list/description/) | Rearrangement practice
| Middle of Linked List | [Middle](https://leetcode.com/problems/middle-of-the-linked-list/description/) | Can we use fast and slow pointers here?|
| Check if Linked List is a Palindrom | [Palindrome List](https://leetcode.com/problems/palindrome-linked-list/description/) | use concepts from Midpoint and reverse here | 
| Sort a Linked List | [Sort List](https://leetcode.com/problems/sort-list/description/) | Combine concepts of midpoint and merge 2 sorted lists to perform this|
| Copy List with Random Pointer | [Copy List with Random Pointer](https://leetcode.com/problems/copy-list-with-random-pointer/description/) | Culmination of all rearrangement questions - uses all the concepts|
| LRU Cache | [LRU Cache](https://leetcode.com/problems/lru-cache/description/) | You should probably do hash maps. if you haven't - do that first and then come back to this question | 
| Flatten a 2d List | [Flatten a Multilevel Doubly Linked List](https://leetcode.com/problems/flatten-a-multilevel-doubly-linked-list/description/) | Can we leveragethe concept of merge sort or recursion here? | 
| Merge k sorted lists | [Merge K sorted lists](https://leetcode.com/problems/merge-k-sorted-lists/description/) | We should do both a compute optimized and a space optimized way | 

#

#### Block 5 Greedy, Dynamic Programming
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

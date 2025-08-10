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

_Reversing a Linked Lists_
Assume first node is the dummy head. We are trying to do this visually:
<img width="2198" height="1256" alt="image" src="https://github.com/user-attachments/assets/1c52ac58-6485-4286-a24e-bd8f3537aa95" />
The algorithm roughly looks like:

_Linked List Cyclicity: Algorith and why it works_
The algo maintains two pointers. One moves twice the speed of other - if there is a cycle in the linked list, both will eventually enter the cycle and in the cycle, the faster pointer will catch up to it. If it does, we know for sure that there is a cycle. This is purely logical.
![floyd_cycle_finding](https://github.com/user-attachments/assets/dfc663e3-f843-41c4-8ed9-345755a930cf)

Finding the start of the cycle is where the algorithm gets tricky. It states that wherever the fast and slow pointers met, set a pointer there and another at the start of the list. Start moving them step by step. Where they meet is the start of the cycle.
Why does this work?
Assume that length from start of the list to the start of the cycle is X. From the start of the cycle to meeting point is Y and from meeting point to the start ( in forward direction) is Z. Length of cycle C  = Y + Z.

They can only meet at the start of the cycle if for some number n X = n(C) + Z. If we can prove this equation, then we have proof that the algorithm works. 

| Problem Name | Link | Gist |
|---|---:|---|


#### Block 5 Greedy, Dynamic Programming
**Greedy**

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

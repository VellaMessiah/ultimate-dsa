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
| Maximum Swap | [Maximum Swap](https://leetcode.com/problems/maximum-swap/) |  |
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

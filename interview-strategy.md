# Interview strategy

## Pattern first

Name the pattern before you invent a solution: two pointers, sliding window, hash map, binary search, stack, BFS/DFS, heap, interval, DP, or backtracking. Most mediums are a pattern plus one twist.

## Talk track

1. Restate inputs, outputs, and constraints.
2. Give a correct brute force and its complexity.
3. Name the optimized approach and the invariant that makes it correct.
4. State time and space, including recursion and auxiliary maps or heaps.
5. List edge cases, then code, then walk a small example.

## Timeboxes

- Easy: about 20 minutes, including tests you would run by hand.
- Medium: 30–35 minutes. If you are stuck at 15 minutes, say the brute force and the bottleneck, then ask for a hint.

## Error log

After each problem, write one line: pattern, the bug, and the fix. Review the log before the next session. Re-solve misses from scratch two days later.

## Clarifying questions

- Is the input sorted? Are duplicates allowed?
- Are we dealing with Unicode characters or raw bytes?
- May I mutate the input? Should I return a new value, an index, or nil when there is no answer?
- What are the size limits, and is an empty input possible?

## Tests to mention

Empty input, a single element, and duplicates. For graphs and lists, also try a disconnected node and a cycle.

## Volume

Prioritize mediums. Target 80–120 problems you can explain without notes, not a larger set you only half remember.

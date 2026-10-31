# How to approach a problem

Use this sequence on one problem. Timeboxes, volume, and the error log stay in [Interview strategy](interview-strategy.md). Recurring Go pitfalls are also listed in [Checklist](checklist.md).

## Before coding

Restate the problem in one sentence: the input, the output, and what makes an answer correct.

Clarify the input before you pick a structure:

- Is it sorted? Are duplicates allowed?
- Can a value be missing, nil, or empty?
- May you mutate the input, or do you return a new value?
- Do you return an index, the value, a count, or nil / -1 when there is no answer?
- For text, are the elements Unicode characters or raw bytes? For numbers, are negatives, zeros, and overflow in scope?
- What are the size limits?

Ask for one example and name the output you will return (`indexes`, `length`, `the start of the window`). That name is what the function returns.

## Work an example by hand

Step through the example and write the state after each move: the window bounds, the map, the stack, or one row of a table.

Say the invariant in one sentence. That is the fact that stays true after every step. You re-check it when a test fails.

- Two Sum: after each index, the map holds that value and every value before it, each with its index.
- Sliding window: every index inside `[left, right]` still satisfies the window rule.
- Daily Temperatures: indexes on the stack increase from bottom to top, and their temperatures strictly decrease.

## Brute force, then the cost to remove

Give a correct slow solution and its complexity. Then name the work you are trying to remove.

- A nested scan for a partner is O(n^2) comparisons. A map removes the inner scan.
- A forward scan from each index for the next greater value is O(n^2). A monotonic stack removes the repeated looks.
- Trying every coin combination is exponential. A table removes the repeated sub-amounts.

If that brute force is already linear, or O(n log n) and the limits are small, say so and code it.

## Pattern checklist

Match a signal in the statement to one pattern, then open a local sample and compare the shape.

- Fast lookup, a frequency count, or a complement: hash map. Check the complement before you store the current value when a value must not pair with itself. `easy/1-two-sum`, `medium/560-subarray-sum-equals-k`, `medium/49-group-anagrams`.
- Sorted array, or the smallest value that still works: binary search on an index, or on the answer. Keep the `left <= right` loop and a midpoint that does not overflow. `easy/704-binary-search`, `medium/33-search-in-rotated-sorted-array`, `medium/875-koko-eating-bananas`.
- A contiguous window, a substring, or "at most K": sliding window. Advance `right`, then move `left` forward while the window breaks the rule. `medium/3-longest-substring-without-repeating-characters`, `medium/424-longest-repeating-character-replacement`, `hard/76-minimum-window-substring`.
- Next greater, previous smaller, daily temperatures, or a histogram: monotonic stack of indexes (you need distances or boundaries, so store indexes). `medium/739-daily-temperatures`, `hard/84-largest-rectangle-in-histogram`, `hard/239-sliding-window-maximum`.
- Nested matching, undo, or the path of a DFS: a stack, or recursion that plays the same role. `easy/20-valid-parentheses`, `medium/155-min-stack`.
- Level order, shortest path in an unweighted graph, or a process that spreads (rotting, infection): a queue and BFS. The first time you reach a node is the shortest hop count. `medium/102-binary-tree-level-order-traversal`, `medium/994-rotting-oranges`, `hard/127-word-ladder`.
- In-place edit of a linked list: pointers. Use a dummy head when the real head might change. Use fast and slow pointers for a cycle or the middle. `easy/206-reverse-linked-list`, `easy/141-linked-list-cycle`, `medium/19-remove-nth-node-from-end-of-list`.
- A tree where each node's answer comes from its children: DFS recursion. Write the return value of one call before you write the body. `easy/104-maximum-depth-of-binary-tree`, `medium/236-lowest-common-ancestor-of-a-binary-tree`, `hard/124-binary-tree-maximum-path-sum`.
- Top K, a streaming median, or merge K sorted inputs: a heap. For top K, keep a size-k heap and read the root. A running median uses one heap for each half. Merge K stores the current head of each list. `medium/215-kth-largest-element-in-an-array`, `hard/295-find-median-from-data-stream`, `hard/23-merge-k-sorted-lists`.
- Intervals: sort by start, then merge overlaps or sweep a line. `medium/56-merge-intervals`.
- A grid of land and water, a dependency list, or "how many components": graph DFS or BFS. Use union-find when the question is the component count. `medium/200-number-of-islands`, `medium/207-course-schedule`, `medium/547-number-of-provinces`.
- Every subset, permutation, or path: backtracking. Choose, recurse, undo. `medium/78-subsets`, `medium/46-permutations`, `medium/79-word-search`.
- Words matched by prefix: a trie. `medium/208-implement-trie-prefix-tree`.
- Count the ways, minimum cost, or a subsequence, and the same smaller problem repeats: DP. Write the state, the transition, the base case, and the fill order before any code. `easy/70-climbing-stairs`, `medium/322-coin-change`, `medium/300-longest-increasing-subsequence`, `medium/1143-longest-common-subsequence`, `hard/72-edit-distance`.
- A design that needs O(1) get and put, with eviction of the least recently used entry: a hash map plus a linked list. `medium/146-lru-cache`.

When two patterns fit, pick the one that removes the cost you named. Unsorted indexes for a pair sum are a hash map (`easy/1-two-sum`). A sorted array where both ends can move inward is two pointers (`medium/11-container-with-most-water`).

## Go choices while coding

Settle these before the first loop.

- A missing map key reads as the zero value. Use comma-ok when absence matters: `j, ok := seen[target-n]`.
- Slices share a backing array. `append` may reuse it, and it may allocate when capacity runs out. Hold the result: `s = append(s, x)`.
- Copy a result slice before you store it. Backtracking mutates the current path; `append([]int(nil), cur...)` keeps an earlier answer stable. See `medium/78-subsets`. `slices.Clone` is the same idea.
- Strings are immutable byte sequences. `s[i]` is a byte. A `range` over a string yields runes. Use `[]rune(s)` when the problem means characters.
- `container/heap` `Push` and `Pop` use pointer receivers. Pass `*IntMinHeap` to `heap.Init`, `heap.Push`, and `heap.Pop`. See `medium/215-kth-largest-element-in-an-array`.
- There is no built-in set. Use `map[T]struct{}` and store `struct{}{}`.
- Recursion depth is limited by the goroutine stack. A deep tree, a long chain, or a graph can overflow. Prefer an explicit stack or BFS when the depth is unbounded.

## After the code

Trace the original example on the code, including the first iteration and the last.

Then run:

- Empty input
- One element
- Duplicates
- Already sorted, or already valid
- No answer (nil, -1, 0, or an empty slice — the one you agreed up front)

For graphs and lists, add a disconnected node and a cycle.

State time and space together. Count the recursion stack, the map entries, and the heap storage, along with the slice you return. Say which term dominates.

## Spoken script

1. Clarify. "The input is ___. The output is ___. I am assuming ___."
2. Example. "On this input the answer is ___. After each step, ___ stays true."
3. Brute force. "A correct way is ___. That is O(___) time and O(___) extra space. The cost I want to remove is ___."
4. Pattern. "This is a ___ problem. I will use ___."
5. Code. Narrate the loop and the invariant. Name the Go choice that matters here (comma-ok, a copied slice, or a pointer receiver).
6. Test. Walk the example, then empty, one element, duplicates, and no answer.
7. Complexity. "Time is O(___). Extra space is O(___), including ___."

## Walkthrough: Two Sum

Return the indexes of two numbers that add up to `target`. The same index may not be used twice. This package returns `nil` when no pair exists. Full code: `easy/1-two-sum/twosum.go`.

**Clarify.** `nums` is not sorted. Duplicates are allowed. Return indexes, and leave `nums` unchanged.

**Example.** `nums = [2, 7, 11, 15]`, `target = 9`. 2 needs 7, which is not in the map yet. 7 needs 2, which was stored at index 0. The answer is `[0, 1]`.

**Invariant.** After index `i` is processed, the map holds `nums[i]` and every value before it, each with its index. Look up `target - nums[i]` before storing `nums[i]`. That keeps one index from matching itself.

**Brute force.** For each `i`, scan every `j > i`. Time is O(n^2). Extra space is O(1). The cost to remove is that inner scan.

**Pattern.** The missing piece is a complement lookup, so one hash map and one pass:

```go
if j, ok := seen[target-n]; ok {
    return []int{j, i}
}
seen[n] = i
```

**Tests.**

- `[2, 7, 11, 15]`, target 9 → `[0, 1]`. The map goes from empty to `{2: 0}`, then 7 hits.
- Empty slice → `nil`. The loop never runs.
- One element → the value is stored, nothing hits, return `nil`.
- Duplicates `[3, 3]`, target 6 → `[0, 1]`. The second 3 finds the first because the lookup happens before the write.
- Already sorted `[1, 2, 3]`, target 5 → `[1, 2]`. Sorted input still wants indexes, so the map pass is enough.
- No pair `[1, 2]`, target 10 → `nil`.

**Complexity.** Time O(n). Extra space O(n) for the map. There is no recursion.

## Walkthrough: which pattern for Daily Temperatures

For each day, return how many days until a strictly warmer temperature. A later colder day does not answer an earlier day. That is next-greater, so the structure is a monotonic stack of indexes: the distance is `i - j`. Full code: `medium/739-daily-temperatures/temps.go`.

**Brute force.** From each day, scan forward until a warmer one. Time is O(n^2). The cost to remove is looking again at days that are already colder than a later day you have seen.

**Invariant.** Stack indexes increase from bottom to top, and their temperatures strictly decrease. A day that has found a warmer day is popped once and never pushed again.

```go
for len(stack) > 0 && temperatures[stack[len(stack)-1]] < t {
    j := stack[len(stack)-1]
    stack = stack[:len(stack)-1]
    ans[j] = i - j
}
stack = append(stack, i)
```

**Example.** `[73, 74, 75, 71, 69, 72, 76, 73]` → `[1, 1, 4, 2, 1, 1, 0, 0]`. 74 resolves 73 at distance 1. 72 resolves 69 and 71. 76 resolves 72 and 75. The last 73 has nothing warmer after it, so it stays 0.

**Tests.** Empty input returns an empty slice. One day returns `[0]`, because the answer slice is allocated as zeros and nothing pops. Equal temperatures do not pop: the comparison is `<`. A strictly decreasing array never pops, so every answer stays 0.

**Complexity.** Each index is pushed once and popped at most once, so time is O(n). Extra space is O(n) for the stack. The answer slice is O(n) output.

The same checklist picks a different tool when the signal changes. "Fewest coins that sum to `amount`" is minimum cost with repeated sub-amounts, so it is DP: `dp[a]` is the fewest coins that make `a`. See `medium/322-coin-change/coinchange.go`.

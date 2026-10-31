# 8-week roadmap

Spend about 8–12 hours a week. Implement each structure yourself, then solve problems out loud. Re-solve anything you needed hints for two days later.

## Week 1 — Go foundations and complexity

Big-O (time and extra space), recursion and base cases, arrays versus slices, strings, maps, and pointers.

Implement a min stack, a queue from two stacks, and a singly linked list. See `medium/155-min-stack`, `easy/232-implement-queue-using-stacks`, and `easy/206-reverse-linked-list`.

Solve 8–12 easy array and hash-map problems (two pointers, frequency maps, prefix sums). `easy/1-two-sum` is the template. Also `easy/121-best-time-to-buy-and-sell-stock`, `easy/125-valid-palindrome`, `easy/136-single-number`, `easy/217-contains-duplicate`, `easy/242-valid-anagram`, `easy/283-move-zeroes`, `medium/49-group-anagrams`, `medium/238-product-of-array-except-self`, and `medium/560-subarray-sum-equals-k`.

## Week 2 — Searching and sorting

Binary search loop patterns (`left <= right`, midpoint without overflow). Merge sort and the quicksort partition idea. Sorting with `sort.Slice`.

Practice sorted-array problems, interval problems, and binary search on the answer. See `easy/704-binary-search`, `medium/33-search-in-rotated-sorted-array`, `medium/875-koko-eating-bananas`, `medium/56-merge-intervals`, `medium/912-sort-an-array`, and `hard/4-median-of-two-sorted-arrays`.

## Week 3 — Linked lists, stacks, and queues

Reverse a list, detect a cycle, merge two sorted lists. Monotonic stack and a deque.

Problems: next greater element, valid parentheses, sliding-window maximum, minimum window substring. See `easy/21-merge-two-sorted-lists`, `easy/141-linked-list-cycle`, `easy/206-reverse-linked-list`, `medium/2-add-two-numbers`, `medium/19-remove-nth-node-from-end-of-list`, `hard/25-reverse-nodes-in-k-group`, `easy/20-valid-parentheses`, `medium/22-generate-parentheses`, `hard/32-longest-valid-parentheses`, `medium/739-daily-temperatures`, `hard/84-largest-rectangle-in-histogram`, `medium/3-longest-substring-without-repeating-characters`, `medium/11-container-with-most-water`, `medium/424-longest-repeating-character-replacement`, `hard/239-sliding-window-maximum`, `hard/76-minimum-window-substring`, and `hard/42-trapping-rain-water`.

## Week 4 — Trees and heaps

DFS and BFS, binary search trees, tree recursion, lowest common ancestor, and heaps.

Problems: inorder and level-order traversal, kth largest, top-K, merge k sorted lists, maximum path sum, running median. See `easy/94-binary-tree-inorder-traversal`, `easy/104-maximum-depth-of-binary-tree`, `easy/226-invert-binary-tree`, `easy/543-diameter-of-binary-tree`, `medium/98-validate-binary-search-tree`, `medium/102-binary-tree-level-order-traversal`, `medium/105-construct-binary-tree-from-preorder-and-inorder-traversal`, `medium/236-lowest-common-ancestor-of-a-binary-tree`, `hard/297-serialize-and-deserialize-binary-tree`, `medium/215-kth-largest-element-in-an-array`, `medium/347-top-k-frequent-elements`, `hard/23-merge-k-sorted-lists`, `hard/124-binary-tree-maximum-path-sum`, and `hard/295-find-median-from-data-stream`.

## Week 5 — Graphs

Adjacency lists, BFS and DFS, connected components, topological sort, Union-Find, and Dijkstra (weighted).

Problems: number of islands, course schedule, shortest path, dependency ordering. See `medium/133-clone-graph`, `medium/200-number-of-islands`, `medium/207-course-schedule`, `medium/547-number-of-provinces`, `medium/994-rotting-oranges`, `medium/128-longest-consecutive-sequence`, and `hard/127-word-ladder`.

## Week 6 — Dynamic programming

Memoization versus tabulation. 1D and 2D tables. Knapsack and subsequence patterns.

Problems: climbing stairs, coin change, longest increasing subsequence, edit distance, grid path counts. See `easy/70-climbing-stairs`, `medium/53-maximum-subarray`, `medium/62-unique-paths`, `medium/198-house-robber`, `medium/300-longest-increasing-subsequence`, `medium/322-coin-change`, `medium/1143-longest-common-subsequence`, `medium/5-longest-palindromic-substring`, `medium/139-word-break`, `hard/10-regular-expression-matching`, and `hard/72-edit-distance`.

## Week 7 — Advanced patterns

Backtracking, tries, intervals, greedy choice, and bit manipulation.

Problems: permutations, subsets, word search, meeting rooms, trie queries. See `medium/46-permutations`, `medium/78-subsets`, `medium/79-word-search`, `medium/208-implement-trie-prefix-tree`, `medium/15-3sum`, `medium/56-merge-intervals`, `medium/146-lru-cache`, `easy/136-single-number`, and `hard/41-first-missing-positive`.

## Week 8 — Interview simulation

Run 4–6 timed mocks (one easy, then mediums). Re-solve weak topics from the error log. Practice stating the invariant, complexity, and edge cases before you code.

## Problems by difficulty

### Easy

- `easy/1-two-sum`
- `easy/20-valid-parentheses`
- `easy/21-merge-two-sorted-lists`
- `easy/70-climbing-stairs`
- `easy/94-binary-tree-inorder-traversal`
- `easy/104-maximum-depth-of-binary-tree`
- `easy/121-best-time-to-buy-and-sell-stock`
- `easy/125-valid-palindrome`
- `easy/136-single-number`
- `easy/141-linked-list-cycle`
- `easy/206-reverse-linked-list`
- `easy/217-contains-duplicate`
- `easy/226-invert-binary-tree`
- `easy/232-implement-queue-using-stacks`
- `easy/242-valid-anagram`
- `easy/283-move-zeroes`
- `easy/543-diameter-of-binary-tree`
- `easy/704-binary-search`

### Medium

- `medium/2-add-two-numbers`
- `medium/3-longest-substring-without-repeating-characters`
- `medium/5-longest-palindromic-substring`
- `medium/11-container-with-most-water`
- `medium/15-3sum`
- `medium/19-remove-nth-node-from-end-of-list`
- `medium/22-generate-parentheses`
- `medium/33-search-in-rotated-sorted-array`
- `medium/46-permutations`
- `medium/49-group-anagrams`
- `medium/53-maximum-subarray`
- `medium/56-merge-intervals`
- `medium/62-unique-paths`
- `medium/78-subsets`
- `medium/79-word-search`
- `medium/98-validate-binary-search-tree`
- `medium/102-binary-tree-level-order-traversal`
- `medium/105-construct-binary-tree-from-preorder-and-inorder-traversal`
- `medium/128-longest-consecutive-sequence`
- `medium/133-clone-graph`
- `medium/139-word-break`
- `medium/146-lru-cache`
- `medium/155-min-stack`
- `medium/198-house-robber`
- `medium/200-number-of-islands`
- `medium/207-course-schedule`
- `medium/208-implement-trie-prefix-tree`
- `medium/215-kth-largest-element-in-an-array`
- `medium/236-lowest-common-ancestor-of-a-binary-tree`
- `medium/238-product-of-array-except-self`
- `medium/300-longest-increasing-subsequence`
- `medium/322-coin-change`
- `medium/347-top-k-frequent-elements`
- `medium/424-longest-repeating-character-replacement`
- `medium/547-number-of-provinces`
- `medium/560-subarray-sum-equals-k`
- `medium/739-daily-temperatures`
- `medium/875-koko-eating-bananas`
- `medium/912-sort-an-array`
- `medium/994-rotting-oranges`
- `medium/1143-longest-common-subsequence`

### Hard

- `hard/4-median-of-two-sorted-arrays`
- `hard/10-regular-expression-matching`
- `hard/23-merge-k-sorted-lists`
- `hard/25-reverse-nodes-in-k-group`
- `hard/32-longest-valid-parentheses`
- `hard/41-first-missing-positive`
- `hard/42-trapping-rain-water`
- `hard/72-edit-distance`
- `hard/76-minimum-window-substring`
- `hard/84-largest-rectangle-in-histogram`
- `hard/124-binary-tree-maximum-path-sum`
- `hard/127-word-ladder`
- `hard/239-sliding-window-maximum`
- `hard/295-find-median-from-data-stream`
- `hard/297-serialize-and-deserialize-binary-tree`

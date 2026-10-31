# Checklist

## Must know

- Arrays and strings: two pointers, prefix sums, sliding window
- Hash maps and sets
- Linked lists
- Stacks and queues
- Trees (DFS, BFS, BST)
- Heaps
- Graphs (BFS, DFS, topological sort, Union-Find)
- Binary search
- Dynamic programming
- Backtracking

## Go interview points

- A missing map key reads as the zero value. Use the comma-ok form (`v, ok := m[k]`) when absence matters.
- Slices share a backing array. Copy with `append([]int(nil), a...)` or `slices.Clone` before you store or mutate independently.
- `append` may allocate a new array when capacity is exceeded. Hold the result: `s = append(s, x)`.
- Strings are immutable byte sequences. Indexing yields a byte. Range over a string yields runes. Use `[]rune` when you mean characters.
- `container/heap` `Push` and `Pop` use pointer receivers. Pass `*IntMinHeap` to `heap.Init`, `heap.Push`, and `heap.Pop`.
- There is no built-in set. Use `map[T]struct{}`.
- Recursion depth is limited by the goroutine stack. Deep trees and graphs can overflow; prefer an explicit stack or BFS when depth is unbounded.
- State time and space together. Count the recursion stack, map entries, and heap storage, not only the output slice.

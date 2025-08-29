# LEETCODE-Arrays-3446
---
### Code Recap

* `sortdiagonal(row, col, grid, asc)`:

  1. Collects all diagonal elements into `vec`.
  2. Sorts them ascending (`asc=true`) or descending (`asc=false`).
  3. Places them back in the diagonal.

---

### Example Dry Run

Suppose:

```
grid = [
 [3, 3, 1, 1],
 [2, 2, 1, 2],
 [1, 1, 1, 2],
 [1, 2, 3, 3]
]
n = 4
```

---

#### Step 1: Process diagonals starting from first column (`col=0`) → **descending sort**

* **row = 0, col = 0** → diagonal: `[3,2,1,3]` → sort desc → `[3,3,2,1]`
  grid becomes:

  ```
  [3, 3, 1, 1]
  [2, 3, 1, 2]
  [1, 2, 1, 2]
  [1, 2, 3, 1]
  ```

* **row = 1, col = 0** → diagonal: `[2,2,2]` → already `[2,2,2]`.

* **row = 2, col = 0** → diagonal: `[1,2]` → sort desc → `[2,1]`.

* **row = 3, col = 0** → diagonal: `[1]` → stays same.

---

#### Step 2: Process diagonals starting from first row (`row=0`) → **ascending sort**

* **row = 0, col = 1** → diagonal: `[3,2,1]` → sort asc → `[1,2,3]`.

* **row = 0, col = 2** → diagonal: `[1,1,3]` → sort asc → `[1,1,3]`.

* **row = 0, col = 3** → diagonal: `[1,2,1,1]` → sort asc → `[1,1,1,2]`.

---

### Final Matrix after all diagonals sorted:

```
[
 [3, 1, 1, 1],
 [3, 2, 1, 1],
 [2, 2, 1, 2],
 [1, 3, 3, 2]
]
```

---

✅ So the algorithm works like this:

* Left-side diagonals (starting from col=0) → sorted descending.
* Top-side diagonals (starting from row=0) → sorted ascending.

---

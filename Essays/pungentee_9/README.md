# Task 1: Optimal Page Replacement Algorithm

**Given:**

- 5 pages in memory with commands until next use: A=1000, B=33000, C=15000, D=50000, E=750
- Need to load 3 new pages: F=900, G=24000, H=12000

**Solution:**

## Initial State

| Page | Commands until next use |
|------|-------------------------|
| A    | 1000                   |
| B    | 33000                  |
| C    | 15000                  |
| D    | 50000                  |
| E    | 750                    |

## Step 1: Loading page F (900 commands until use)

- **Selection criteria:** Remove page with highest "commands until next use"
- Page D has the highest value (50000), so it will be replaced
- **Action:** Remove D, insert F

| Page | Commands until next use |
|------|-------------------------|
| A    | 1000                   |
| B    | 33000                  |
| C    | 15000                  |
| **F**| **900**                |
| E    | 750                    |

## Step 2: Loading page G (24000 commands until use)

- **Selection criteria:** Remove page with highest "commands until next use"
- Page B has the highest value (33000), so it will be replaced
- **Action:** Remove B, insert G

| Page | Commands until next use |
|------|-------------------------|
| A    | 1000                   |
| **G**| **24000**              |
| C    | 15000                  |
| F    | 900                    |
| E    | 750                    |

## Step 3: Loading page H (12000 commands until use)

- **Selection criteria:** Remove page with highest "commands until next use"
- Page G has the highest value (24000), so it will be replaced
- **Action:** Remove G, insert H

| Page | Commands until next use |
|------|-------------------------|
| A    | 1000                   |
| **H**| **12000**              |
| C    | 15000                  |
| F    | 900                    |
| E    | 750                    |

# Task 2: NRU (Not Recently Used) Algorithm

**Given:**

- 5 pages in memory: A, B, C, D, E
- Need to load 3 pages: F, G, H
- Access pattern: A and C were accessed; B and D were accessed and modified

**Solution:**

## Initial Classification

Based on R (Referenced) and M (Modified) bits:

| Page | R bit | M bit | Class |
|------|-------|-------|-------|
| A    | 1     | 0     | 2     |
| B    | 1     | 1     | 3     |
| C    | 1     | 0     | 2     |
| D    | 1     | 1     | 3     |
| E    | 0     | 0     | 0     |

**Classes:**

- Class 0: E (not referenced, not modified)
- Class 1: (none)
- Class 2: A, C (referenced, not modified)
- Class 3: B, D (referenced and modified)

## Step 1: Loading page F

- **Selection:** Choose from lowest class (Class 0)
- **Action:** Remove E, insert F

| Page | R bit | M bit | Class |
|------|-------|-------|-------|
| A    | 1     | 0     | 2     |
| B    | 1     | 1     | 3     |
| C    | 1     | 0     | 2     |
| D    | 1     | 1     | 3     |
| **F**| **0** | **0** | **0** |

## Step 2: Loading page G

- **Selection:** Choose from lowest class (Class 0) - page F
- **Action:** Remove F, insert G

| Page | R bit | M bit | Class |
|------|-------|-------|-------|
| A    | 1     | 0     | 2     |
| B    | 1     | 1     | 3     |
| C    | 1     | 0     | 2     |
| D    | 1     | 1     | 3     |
| **G**| **0** | **0** | **0** |

## Step 3: Loading page H

- **Selection:** Choose from lowest class (Class 0) - page G
- **Action:** Remove G, insert H

| Page | R bit | M bit | Class |
|------|-------|-------|-------|
| A    | 1     | 0     | 2     |
| B    | 1     | 1     | 3     |
| C    | 1     | 0     | 2     |
| D    | 1     | 1     | 3     |
| **H**| **0** | **0** | **0** |

# Task 3: Second Chance Algorithm

**Given:**

- 5 pages in memory: A, B, C, D, E (in FIFO order)
- Need to load 3 pages: F, G, H
- Access pattern: A, D, and E were accessed (R=1)

**Solution:**

## Initial State

| Position | Page | R bit | Status |
|----------|------|-------|--------|
| Head     | A    | 1     | Oldest |
| 2        | B    | 0     |        |
| 3        | C    | 0     |        |
| 4        | D    | 1     |        |
| Tail     | E    | 1     | Newest |

## Step 1: Loading page F

- **Check head (A):** R=1, so give second chance
- **Action:** Set A's R=0, move A to tail, check next
- **Check B:** R=0, so remove B
- **Result:** Remove B, insert F

| Position | Page | R bit | Status |
|----------|------|-------|--------|
| Head     | C    | 0     | Oldest |
| 2        | D    | 1     |        |
| 3        | E    | 1     |        |
| 4        | A    | 0     | (got second chance) |
| Tail     | **F**| **0** | **Newest** |

## Step 2: Loading page G

- **Check head (C):** R=0, so remove C
- **Result:** Remove C, insert G

| Position | Page | R bit | Status |
|----------|------|-------|--------|
| Head     | D    | 1     | Oldest |
| 2        | E    | 1     |        |
| 3        | A    | 0     |        |
| 4        | F    | 0     |        |
| Tail     | **G**| **0** | **Newest** |

## Step 3: Loading page H

- **Check head (D):** R=1, so give second chance
- **Action:** Set D's R=0, move D to tail, check next
- **Check E:** R=1, so give second chance
- **Action:** Set E's R=0, move E to tail, check next
- **Check A:** R=0, so remove A
- **Result:** Remove A, insert H

| Position | Page | R bit | Status |
|----------|------|-------|--------|
| Head     | F    | 0     | Oldest |
| 2        | G    | 0     |        |
| 3        | D    | 0     | (got second chance) |
| 4        | E    | 0     | (got second chance) |
| Tail     | **H**| **0** | **Newest** |

# Task 4: Clock Algorithm

**Given:**

- 5 pages in memory: A, B, C, D, E (arranged in clock)
- Need to load 3 pages: F, G, H
- Access pattern: A, C, and E were accessed (R=1)

**Solution:**

## Initial State (Clock Hand at A)

```
     A(R=1)
   E(R=1) B(R=0)
    D(R=0) C(R=1)
```

## Step 1: Loading page F

- **Check A:** R=1, set R=0, advance hand to B
- **Check B:** R=0, replace with F

```
     A(R=0)
   E(R=1) F(R=0) ← hand
    D(R=0) C(R=1)
```

## Step 2: Loading page G

- **Check F:** R=0, replace with G

```
     A(R=0)
   E(R=1) G(R=0) ← hand
    D(R=0) C(R=1)
```

## Step 3: Loading page H

- **Check G:** R=0, replace with H

```
     A(R=0)
   E(R=1) H(R=0) ← hand
    D(R=0) C(R=1)
```

# Task 5: LRU (Least Recently Used) Algorithm

**Given:**

- 5 pages in memory: A, B, C, D, E
- Need to load 3 pages: F, G, H
- Access sequence: A, B, D, A

**Solution:**

## Initial LRU Matrix (4x4 for tracking)

After access sequence A, B, D, A:

|   | A | B | C | D | E |
|---|---|---|---|---|---|
| A | 0 | 1 | 1 | 1 | 1 |
| B | 0 | 0 | 1 | 0 | 1 |
| C | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 1 | 1 | 0 | 1 |
| E | 0 | 0 | 0 | 0 | 0 |

**LRU Order (least to most recently used):**

1. C (binary: 00000 = 0)
2. E (binary: 00000 = 0)
3. B (binary: 00101 = 5)
4. D (binary: 01101 = 13)
5. A (binary: 01111 = 15)

## Step 1: Loading page F

- **Remove:** C (least recently used)
- **Result:** Replace C with F

**Current pages:** A, B, F, D, E

## Step 2: Loading page G

- **Remove:** E (next least recently used)
- **Result:** Replace E with G

**Current pages:** A, B, F, D, G

## Step 3: Loading page H

- **Remove:** B (next least recently used after C and E)
- **Result:** Replace B with H

**Final pages:** A, H, F, D, G

# Summary Table

| Algorithm | Final Pages After Loading F, G, H |
|-----------|-----------------------------------|
| Optimal   | A, H, C, F, E                    |
| NRU       | A, B, C, D, H                    |
| Second Chance | D, E, F, G, H               |
| Clock     | A, E, H, D, C                    |
| LRU       | A, H, F, D, G                    |


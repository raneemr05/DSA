
## 3. What is time complexity?

**Time complexity describes how the amount of work an algorithm performs changes as the input size increases.**

Let's use a simple example:

```python
def greet_students(students):
    for student in students:
        print(f"Hello, {student}!")
```

The function greets every student in the list.

- 3 students → 3 loop iterations.
- 10 students → 10 loop iterations.
- 100 students → 100 loop iterations.

The more students we have, the more times the loop runs.

This is called **linear time complexity**, written as **O(n)**.

Here, `n` represents the input size — in this example, the number of students.

### An important distinction

Time complexity does **not** directly tell us how many seconds the code takes to execute. It describes how the amount of work grows as the input gets larger.

---

## 4. How can we assess time complexity?

For beginners, a useful starting point is to count how many times an important operation runs, then consider how that count changes as the input grows.

Let's start with three common patterns.

### Pattern A: One loop — O(n)

```python
def example_a(n):
    for i in range(n):
        print(i)
```

- If `n = 5`, the loop runs 5 times.
- If `n = 100`, the loop runs 100 times.

The number of iterations grows in proportion to `n`.

**O(n) — Linear time**

If the input doubles, the number of loop iterations roughly doubles too.

### Pattern B: Nested loops — O(n²)

```python
def example_b(n):
    for i in range(n):
        for j in range(n):
            print(i, j)
```

Suppose `n = 3`:

- The outer loop runs 3 times.
- For each outer iteration, the inner loop runs 3 times.
- Total inner-loop executions: `3 × 3 = 9`.

If `n = 5`, the `print` statement runs 25 times. If `n = 100`, it runs 10,000 times.

**O(n²) — Quadratic time**

The work grows much faster because each outer-loop iteration triggers another complete run of the inner loop.

### Pattern C: Halving the value — O(log n)

```python
def example_c(n):
    while n > 0:
        print(n)
        n //= 2
```

If `n = 16`, the values printed are:

```text
16
8
4
2
1
```

The loop runs 5 times because the value is halved on each iteration until it reaches zero.

This is **logarithmic time complexity**, written as **O(log n)**. More specifically, the repeated halving relates to a logarithm with base 2, although Big O notation usually leaves the base unwritten.

**O(log n) — Logarithmic time**

The number of iterations grows slowly as the input increases, because the value is repeatedly halved.

---

## 5. Compare how the work grows

The following table shows representative operation counts for each pattern. For the logarithmic column, it shows `log₂(n)` as a guide; the exact number of iterations in a loop can differ slightly depending on its stopping condition.

| Input size (`n`) | O(n) | O(n²) | log₂(n), approximately |
|---:|---:|---:|---:|
| 4 | 4 | 16 | 2 |
| 8 | 8 | 64 | 3 |
| 16 | 16 | 256 | 4 |
| 32 | 32 | 1,024 | 5 |

These are **operation counts, not execution times**.

The key observation is that different algorithms can respond very differently to the same increase in input size.

---

## 6. A simple checklist for analysing time complexity

When you look at a piece of code, ask:

1. **What is the input size?** It is often represented by `n`.
2. **What operation or statement are we counting?**
3. **How many times does it run?** Look at loops and how they interact.
4. **How does the count grow as `n` increases?** Does it stay constant, grow proportionally, grow quadratically, or shrink the remaining work by a factor each time?

This checklist is a starting point. More complex code may require considering conditions, function calls, and different execution paths.

---

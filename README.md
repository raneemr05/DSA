# Introduction to Complexity and Time Complexity

Beginner-friendly notes for understanding how algorithms behave as the size of the input grows.

## Learning goals

By the end of this lesson, you should be able to:

- Explain what complexity means in programming.
- Describe why complexity matters.
- Explain time complexity in simple terms.
- Recognise common time-complexity patterns in code.
- Use a simple checklist to begin analysing time complexity.

---

## 1. What is complexity?

**Complexity describes how the resources a solution needs change as the problem gets bigger.**

Imagine you're preparing lunch.

### Scenario A: Make one sandwich

You need a few ingredients and a little time.

### Scenario B: Make 50 sandwiches

You need more ingredients and more time to prepare them.

As the number of sandwiches increases, the resources needed increase too.

In programming, we ask similar questions:

- How much time or work does the solution need?
- How much extra memory does the solution need?

These are the two main types of complexity we'll explore:

- **Time complexity:** How does the amount of work grow as the input gets bigger?
- **Space complexity:** How does the amount of memory used grow as the input gets bigger?

For now, focus on **how the requirements grow**, rather than the exact number of seconds or bytes used.

---

## 2. Why does complexity matter?

Imagine two developers create solutions to find a student's name in a list.

Both solutions work correctly with 10 students. But what happens when the school has 100,000 students?

A solution that works well with a small input might become too slow or use too much memory with a large input.

### Same task, different efficiency

- **Solution A:** Continues to work efficiently as the list grows.
- **Solution B:** May become very slow when the list is large.

We analyse complexity to help us choose solutions that remain efficient as the amount of data increases.

Complexity matters because it helps us:

- Handle larger amounts of data.
- Reduce unnecessary processing.
- Use memory efficiently.
- Build applications that scale as more users and data are added.

> **Remember:** A solution that works is good. A solution that works efficiently at scale is even better.

---

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

## Key takeaways

- Complexity describes how resource requirements change as a problem grows.
- Time complexity focuses on how the amount of work grows with input size.
- `O(n)` is a common pattern for one loop over the input.
- `O(n²)` is a common pattern when two loops each run `n` times.
- `O(log n)` is a common pattern when the remaining value or search space is repeatedly divided by a constant factor.
- Big O describes growth, not the actual number of seconds a program takes.

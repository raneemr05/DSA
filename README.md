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

## Key takeaways

- Complexity describes how resource requirements change as a problem grows.
- Time complexity focuses on how the amount of work grows with input size.
- `O(n)` is a common pattern for one loop over the input.
- `O(n²)` is a common pattern when two loops each run `n` times.
- `O(log n)` is a common pattern when the remaining value or search space is repeatedly divided by a constant factor.
- Big O describes growth, not the actual number of seconds a program takes.

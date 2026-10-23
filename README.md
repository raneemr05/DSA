# Introduction to Complexity

Beginner-friendly notes for understanding how algorithms behave as the size of the input grows and how to find its complexity.

## Learning goals

By the end of this lesson, you should be able to:

- Explain what complexity means in programming.
- Describe why complexity matters.
- Explain time complexity in simple terms.
- Recognise common time-complexity patterns in code.
- Use a simple checklist to begin analysing time complexity.


## 1. What is complexity? 😨

**Complexity describes how an algorithm’s resource requirements grow as the input size increases.**

Imagine you're preparing lunch.

### Scenario A: Make one sandwich

You need a few ingredients and a little time.

### Scenario B: Make 50 sandwiches

You need more ingredients and more time to prepare them.

As the number of sandwiches increases, the resources needed increase too.

In programming, we ask similar questions:

- How much time or work does the solution need?
- How much extra memory does the solution need?

### These are the two main types of complexity we'll explore:

- **Time complexity:** How does the amount of work grow as the input gets bigger?
- **Space complexity:** How does the amount of memory used grow as the input gets bigger?

For now, focus on **how the requirements grow**, rather than the exact number of seconds or bytes used.



## 2. Why does complexity matter? 🤔

Imagine two developers create solutions to find a student's name in a list.

Both solutions work correctly with 10 students. But what happens when the school has 100,000 students?

A solution that works well with a small input might become too slow or use too much memory with a large input.

### Same task, different efficiency 🙄

- **Solution A:** Continues to work efficiently as the list grows.
- **Solution B:** May become very slow when the list is large.

We analyse complexity to help us choose solutions that remain efficient as the amount of data increases.

Complexity matters because it helps us:

- Handle larger amounts of data.
- Reduce unnecessary processing.
- Use memory efficiently.
- Build applications that scale as more users and data are added.

> **Remember:** A solution that works is good. A solution that works efficiently at scale is even better. 😎


# How Do We Analyse Complexity? 🧐

An algorithm's performance can depend on the input it receives, even when the input contains the same number of items. We commonly analyse three cases:

- **Best case:** The most favourable scenario for the algorithm.
- **Average case:** The expected behaviour across a defined set or distribution of inputs.
- **Worst case:** The least favourable scenario for the algorithm.

## Example: Searching for a Name

Imagine searching for a name in a list of `n` names, checking one name at a time.

- **Best case:** The name is first, so we check one item — **O(1)**.
- **Worst case:** The name is last or isn't present, so we may check all `n` items — **O(n)**.
- **Average case:** If the name is equally likely to appear at any position, a successful search checks roughly half the list on average. Its growth is still **O(n)**.

These cases describe different scenarios for the same algorithm.

You might be wondering what we are using here O() --> Its BigO

## Where Does Big O Fit In? 🤨

**Big O notation** describes an upper bound on how an algorithm's resource usage grows as the input size increases. In introductory DSA, we commonly use Big O to discuss worst-case complexity.

For example, linear search has a worst-case time complexity of **O(n)** because the number of checks can grow in proportion to the number of items.

**Remember:** Worst case and Big O are not the same thing:

- **Worst case** describes the scenario being analysed.
- **Big O** describes an upper bound on the growth rate.

Big O can also describe bounds for best-case or average-case analysis.

## Explore Big O with Practical Examples

Want to understand what **O(1)**, **O(log n)**, **O(n)** and **O(n²)** look like in code?

Continue to the [Big O Examples Repository](../Time_Space_Complexity/BigO-examples/ReadME.md), where we explore common growth patterns through practical examples.

## Continue Learning

- [Time Complexity](../time_complexity/README.md)
- [Space Complexity](../space_complexity/README.md)
- [BigO](../Time_Space_Complexity/BigO-examples/ReadME.md)



## Key takeaways 😃

- Complexity describes how resource requirements change as a problem grows.
- Time complexity focuses on how the amount of work grows with input size.
- `O(n)` is a common pattern for one loop over the input.
- `O(n²)` is a common pattern when two loops each run `n` times.
- `O(log n)` is a common pattern when the remaining value or search space is repeatedly divided by a constant factor.
- Big O describes growth, not the actual number of seconds a program takes.

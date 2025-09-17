# Problem Set 2: Data Analysis and Testing with MovieLens

## Overview
For this assignment, you will analyze the MovieLens dataset using pandas in Jupyter notebooks. You will practice writing modular analysis functions, testing your code with controlled datasets and assertions, and documenting your reasoning. This assignment is designed to help you develop good practices for reproducible, testable data analysis and effective use of AI tools like Copilot.

--- 

## Requirements

### 1. Process & Documentation
- **Work Log:** Keep a clear, timestamped log of each work session in your `work-log.md` file.
- **Copilot Usage and Self-reflections:** Document wins and fails, share your prompting snippets, and offer self-reflections in your `reflections.md` file.
- Make regular, meaningful git commits as you complete self-contained units of work.

### 2. High-level Analysis Task

Create a jupyter notebook (`.ipynb` file) for these analysis tasks. You may choose to make a separate notebook for each high-level task, but it's not required.

#### Task 2A. Complete the task from the lab

Which movies have the highest average rating, considering only movies with at least 50 ratings?

#### Task 2B. Which users had the broadest taste in movies (rated movies from the most different genres)? 
- Consider only users who rated 20 or fewer movies because people who rate a lot of movies tended to hit all the available genres, giving an uninteresting answer.
- I found a couple users who rated movies from 16 different genres.
- Note that a single movie can count towards more than one genre. That makes this analysis task a little tricky!

#### Optional Challenge Task 2C (up to 10 bonus points available). Which pairs of users had the highest overlap in movies they rated? 

As will often be the case in real-world data analysis tasks, the second high-level task as stated is ambiguous. What does "highest overlap" mean? How should we measure it?

We could measure overlap in several ways, including:
- The number of movies both users rated (e.g., if User A rated movies {1, 2, 3} and User B rated movies {2, 3, 4}, their overlap is 2 because they both rated movies 2 and 3).
- The proportion of movies rated by one user that were also rated by the other (e.g., in the example above, User A rated 2 out of their 3 movies also rated by User B, and User B rated 2 out of their 3 movies also rated by User A).
- The Jaccard similarity, which is the size of the intersection divided by the size of the union of the two sets of rated movies (in the example above, the intersection is {2, 3} and the union is {1, 2, 3, 4}, so the Jaccard similarity is 2/4 = 0.5).

The first seems simplest, but it's not very satisfactory because it will be biased towards users who rate a lot of movies. The second and third options are better in that regard, but they can be biased towards users who rate very few movies. The second option can also be asymmetric (the overlap from A to B can differ from the overlap from B to A).

You may choose any of these measures, or propose your own, but you must clearly define it in your notebook and justify your choice. If you choose a measure that is biased toward very active or very inactive users, yielding uninteresting results such as only pairs with 100% overlap, you may want to consider filtering out users who rated too few and/or too many movies.

This is a challenging data analysis task. You will definitiely need to break it down into smaller tasks. And you will probably want to get advice from your copilot on how to break it into steps. My copilot gave me a clever idea for computing all the overlap counts using matrix multiplication, an idea you might want to ask it about, even if you don't know how matrix multiplication works.

### 3. Workflow
For each high-level analysis task, you will first need to break it down into a sequence of smaller, testable tasks. 

For each smaller task, apply the following 4-step workflow. You'll know a task is "small enough" if you are able to specify tests for the function that implements the task.
1. Write a markdown cell describing the analysis and expected result.
2. Write a code cell defining a function to perform the analysis (taking one or more DataFrames as input).
3. Write a test cell using a controlled test dataset and assert statements to verify correctness of the function.
- use `assert` statements.
- Test your function on edge cases (e.g., empty DataFrames, missing values, duplicate entries).
4. Write a cell applying your function to the real MovieLens data and displaying the result.

At the conclusion of the final smaller task for that high-level task, include a cell explaining your overall findings and interpretations for the high-level task.

---

## Submission Features Checklist
- [ ] A division of each of the higher-level tasks into two or more smaller tasks
- [ ] For each smaller task, the 4-step workflow applied.


## Submission Documentation Checklist
- [ ] `work-log.md` file
- [ ] `reflections.md` file (copilot notes and self-reflections)
- [ ] `analysis.ipynb` file
- [ ] Regular commit history
- [ ] Push your repo back to GitHub
- [ ] submit on Canvas with a note saying that it's ready for grading

---

## Grading Rubric

### 1. Division of High-Level Tasks into Smaller Tasks (15%)
- Clear breakdown of high-level task into smaller, manageable tasks.

### 2. Analysis Functions and Testing (45%)
- Correctness and clarity of analysis functions (20%)
- Quality and coverage of tests (25%)

### 3. Conclusion and Interpretations (15%)

### 4. Process & Documentation (25%)
- Work Log (5%)
- Copilot wins, losses, and prompts (10%)
- Self-reflections (5%)
- Commit log (5%)


---

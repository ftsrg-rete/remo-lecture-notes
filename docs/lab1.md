---
title: Laboratory Exercise 1
subtitle: System Modeling (VIMIAD03)
header: System Modeling (VIMIAD03)
---

# Tool Demo & First Steps

In this lab you will practice version control operations and collaborative model editing.  
The goal is to understand branching, merging, conflict resolution, and teamwork using a shared repository.

---

## Prerequisites

Make sure you:

- can open the provided project
- know how to switch branches
- know how to commit changes
- know how to inspect diffs

> 💡 Tip  
> Always check which branch you are on before editing files.

---

## 1. Practicing Version Control

First, explore the repository and the available views:

- Local changes
- History
- Compare / Diff view

### Tasks

1. Open the `model.qeax` model, inspect it, then close it.
2. Create a `README.txt` file on the `master` branch.
3. Rebase the `feature` branch onto `master`.
4. Modify the README on the `feature` branch.
5. Inspect the differences between the two branches:
   - first for `README.txt`
   - then for `model.qeax`
6. On the `master` branch create a new `feature-2` branch.
7. Merge the old feature branch into `master` (simulate that another developer merged changes meanwhile).
8. Checkout the new feature branch, resolve the conflicts, and merge to `master`.

---

### Expected result

You should be able to:

- see the history of both branches
- understand which commit belongs to which branch
- inspect file differences

---

## 2. Modifying the Model

Create a class diagram based on the provided example. Use a fresh feature branch (e.g., `class-diagram`).

Requirements:

- Modify/Extend the existing model
- The model should contain approximately 15–20 elements
- Choose any topic (preferably something interesting to you)

Examples:

- game objects
- university system
- transport network
- smart home

When you finish, merge your feature branch into `master`.

---

### Expected result

A valid model that loads without errors and contains multiple connected elements.

---

## 3. Merge and Conflict Resolution

Now integrate your changes into the main development line.

### Tasks

1. Create two new branches, and on each, change the same model element, but to different versions. E.g., rename a class, change a multiplicity, etc. 
2. Merge one branch into `master`
3. Try to merge the second branch into `master` -- this should prompt for conflict resolution.
4. Resolve all conflicts using LemonTree
5. Verify the model opens correctly after the merge

> 💡 Tip  
> Save and close the project in Enterprise Architect before committing. 

---

### Expected result

- No merge conflicts remain
- All intended changes are preserved

---

## 4. Pair Exercise – Collaboration (optional exercise)

Work in pairs.

### Tasks

1. Create a shared repository
2. Upload the model to two different branches
3. Each of you modifies the model independently
4. Both of you merge the other's changes into your own branch

---

### Final state requirements

At the end of the exercise:

- both versions must contain the same model
- (parts of) both modifications must be present
- no differences remain between branches

> Compare the branches — the diff must be empty.

---

## Goal of the Lab

By the end of the exercise you should understand:

- why branches exist
- how merges work
- why conflicts happen
- how collaborative modeling differs from editing text files

# pr-diff-demo
A demo of how diffs behave in a GitHub PR.


When the `topic` branch is checked out, the contents of the `demo.md` file were (at commit `6bd4912`):

```
# Demo File

Line 1

Line 2

Line 3

Line 4

Line 5
```

The `topic` branch contains a new commit (`abc051f`) that modified the first line to:

```
Line 1 updated in topic branch.
```


A new commit (`bcb60f4`) was also made to the `main` branch that added the following line at the end of the file:

```
New line added directly in main branch
```


In the [pull request](https://github.com/ravimashru/pr-diff-demo/pull/2/files) from the `topic` branch to the `main` branch, we see the following diff:

<img width="531" alt="image" src="https://user-images.githubusercontent.com/8961232/110755496-0910aa80-826f-11eb-9742-8810b39b7a3e.png">


This is the diff between the latest commit in the `topic` branch (i.e. `abc051f`) and the last common commit between the two branches (i.e. `6bd4912`). It does not contain changes from the new commits on the `main` branch.

To see changes between the two latest commits on both branches, we can use the following endpoint: https://github.com/ravimashru/pr-diff-demo/compare/bcb60f4..abc051f

<img width="413" alt="image" src="https://user-images.githubusercontent.com/8961232/110756272-fcd91d00-826f-11eb-9c3d-da1fa5e2d2c2.png">


Note that this diff shows how to go from commit `bcb60f4` (the current state of the `main` branch) to `abc051f` (the current state of the `topic` branch). That's why we see the changes added in the `main` branch as a deletion, and the changes in the `topic` branch as an addition.

# Day 001 — Environment and Git

## Objective

By the end of today I can:

- [x] Use the basic Git workflow to create and save a project history.
- [x] Push local commits to a GitHub repository.
- [x] Explain what a Git tag is used for.

## Learn

- Primary resource: [GitHub Skills](https://skills.github.com/)
- Supporting resources:
  - [Git basics](https://docs.github.com/en/get-started/git-basics)
  - [Pushing commits to a remote repository](https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository)
  - [Git log documentation](https://git-scm.com/docs/git-log)
- Timebox: 45 minutes

## Recall

The basic Git flow is:

```text
make a change → git status → git add → git commit → git push
```

`git log` shows the commit history. The short version, `git log --oneline`, makes the history easier to scan.

## What stood out

Git tags were the most useful new idea today. A tag is a human-readable name attached to a specific commit. Tags are commonly used to mark important points such as releases:

```bash
git tag v0.1.0
git show v0.1.0
```

A tag does not replace a commit message and does not sit in front of every commit. It points to one commit so that commit can be referred to consistently later.

## Build

- Deliverable: Repository setup, mission, first lesson, first commit, and push to GitHub.
- Acceptance check: `git status`, `git log --oneline`, and the GitHub repository all show the work.

## Practice drill

- Run `git log --oneline` and identify the first commit.
- If desired, create a local test tag with `git tag day-001` and inspect it with `git show day-001`.
- No formal DSA or SQL today.

## Documentation and debugging

- Record the difference between a local repository and a remote GitHub repository.
- Record any Git command that failed and how it was fixed.

## Reflection

- What became clearer? The basic Git flow and the purpose of tags.
- What did I get stuck on? Nothing significant today.
- What will I change tomorrow? Move on to semantic HTML and build the profile page.

## Commit

```text
day-001: document environment and git basics
```

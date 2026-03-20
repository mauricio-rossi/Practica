# Git Cheat Sheet

This reference provides common commands used to follow the repository's branching and promotion workflow.

## Start a Feature Branch

```bash
git checkout develop
git checkout -b feature/us-00002-login
```

## Commit Work in Progress

```bash
git add .
git commit -m "feat(auth): add login form [US-00002]"
```

## Squash a Completed Story into `develop`

```bash
git checkout develop
git merge --squash feature/us-00002-login
git commit -m "US-00002: Add login form"
```

## Squash Completed Sprint Work into `main`

```bash
git checkout main
git merge --squash develop
git commit -m "Sprint 01 complete"
```

## Promote Stable Work to `releases`

```bash
git checkout releases
git merge --squash main
git commit -m "Release v0.1.0"
```

## Tag a Sprint Milestone

```bash
git tag -a sprint-01-complete -m "End of Sprint 01"
git push origin sprint-01-complete
```

## Tag a Public Release

```bash
git tag -a v0.1.0 -m "First alpha release"
git push origin v0.1.0
```
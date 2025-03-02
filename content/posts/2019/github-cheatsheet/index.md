---
title: "GitHub Cheatsheet"
date: "2019-02-17"
author: "mattselkey"
categories: [ "DevOps","Github" ]
---

# 1. General Tasks

## 1.1 Creating a new repository

First initialise the repository

```shell
git init
```

Write code, then commit.

```shell
git commit
```

## 1.2 Clone a repository

```shell
git clone https://github_url/project-name.git
```

## 1.3 Changing a repositories' remote URL

```shell
git remote set-url origin https://github_url/project-name.git
```

# 2. Branches

## 2.1 List Branches

To list all branches in the current repository.

```shell
git branch -a
```

## 2.2 New Branch

To create a new branch named newBranchName, where BaseBranchName is the base branch.

```shell
git checkout -b newBranchName BaseBranchName
```

**Note:** *BaseBranchName* is optional

## 2.3 Change Working Branch

Change working branch to BranchName.

```shell
git checkout BranchName
```

## 2.4 Delete a Branch

```shell
git branch -d BranchName
```

## 2.5 Delete a Remote Branch

```shell
git push RemoteRepositoryURL -d BranchName
```

# 3. Tags

## 3.1 List All Tags

```shell
git tag
```

## 3.2 Delete a Tag

```shell
git tag -d TagName
```

## 3.3 Sync Local/Remote Tags

```shell
git fetch --prune --tags
```

# 4. Subtrees

## 4.1 Add a new Subtree from a remote repository

```shell
git subtree add --prefix LocalFolder RemoteRepoURL.git BranchName --squash
```

## 4.2 Update a Subtree from a remote repository

```shell
git subtree pull --prefix LocalFolder RemoteRepoURL.git BranchName --squash
```

## 4.3 Remove a Subtree

```shell
git remote rm LocalFolder
```
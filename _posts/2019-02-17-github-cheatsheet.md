---
id: 152
title: GitHub Cheatsheet
date: 2019-02-17T15:13:44+01:00
author: mattselkey
layout: post
guid: https://mattselkey.com/?p=152
permalink: /github-cheatsheet/
categories:
  - DevOps
  - Github
---
<!-- wp:heading {"level":1} -->
<h1>1. General Tasks</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>1.1 Creating a new repository</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>First initialise&nbsp;the repository</p>
<!-- /wp:paragraph -->

<!-- wp:shortcode -->
[cc lang="bash"]git init[/cc]
<!-- /wp:shortcode -->

<!-- wp:paragraph -->
<p>Write code, then commit.</p>
<!-- /wp:paragraph -->

<!-- wp:shortcode -->
[cc lang="bash"]git commit[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>1.2 Clone a repository</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
[cc lang="bash"]git clone https://github_url/project-name.git[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>1.3 Changing a repositories' remote URL</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
[cc lang="bash"]git remote set-url origin https://github_url/project-name.git[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading {"level":1} -->
<h1>2. Branches</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>2.1 List Branches</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>To list all branches in the current repository.</p>
<!-- /wp:paragraph -->

<!-- wp:shortcode -->
[cc lang="bash"]git branch -a[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>2.2 New Branch</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>To create a new branch named newBranchName, where BaseBranchName is the base branch.</p>
<!-- /wp:paragraph -->

<!-- wp:shortcode -->
[cc lang="bash"]git checkout -b newBranchName BaseBranchName[/cc]
<!-- /wp:shortcode -->

<!-- wp:paragraph -->
<p><strong>Note:</strong> <em>BaseBranchName</em> is optional</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>2.3 Change Working Branch</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Change working branch to BranchName.</p>
<!-- /wp:paragraph -->

<!-- wp:shortcode -->
[cc lang="bash"]git checkout BranchName[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>2.4 Delete a Branch</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
[cc lang="bash"]git branch -d BranchName[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>2.5 Delete a Remote Branch</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
[cc lang="bash"]git push RemoteRepositoryURL -d BranchName[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading {"level":1} -->
<h1>3. Tags</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>3.1 List All Tags</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
[cc lang="bash"]git tag[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>3.2 Delete a Tag</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
[cc lang="bash"]git tag -d TagName[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>3.2 Sync Local/Remote Tags</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
[cc lang="bash"]git fetch --prune --tags[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading {"level":1} -->
<h1>4. Subtress</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>4.1 Add a new Subtree from a remote repository</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
[cc lang="bash"]git subtree add --prefix LocalFolder RemoteRepoURL.git BranchName --squash[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>4.2 Update a Subtree from a remote repository</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
[cc lang="bash"]git subtree pull --prefix LocalFolder RemoteRepoURL.git BranchName --squash[/cc]
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>4.2 Remove a Subtree</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
[cc lang="bash"]git remote rm LocalFolder[/cc]
<!-- /wp:shortcode -->
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
<p>First initialise the repository</p>
<!-- /wp:paragraph -->

<!-- wp:shortcode -->
{% highlight ruby %}
git init
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:paragraph -->
<p>Write code, then commit.</p>
<!-- /wp:paragraph -->

<!-- wp:shortcode -->
{% highlight ruby %}
git commit
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>1.2 Clone a repository</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
{% highlight ruby %} 
git clone https://github_url/project-name.git
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>1.3 Changing a repositories' remote URL</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
{% highlight ruby %}
git remote set-url origin https://github_url/project-name.git
{% endhighlight %}
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
{% highlight ruby %}
git branch -a
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>2.2 New Branch</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>To create a new branch named newBranchName, where BaseBranchName is the base branch.</p>
<!-- /wp:paragraph -->

<!-- wp:shortcode -->
{% highlight ruby %}
git checkout -b newBranchName BaseBranchName
{% endhighlight %}
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
{% highlight ruby %}
git checkout BranchName
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>2.4 Delete a Branch</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
{% highlight ruby %}
git branch -d BranchName
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>2.5 Delete a Remote Branch</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
{% highlight ruby %}
git push RemoteRepositoryURL -d BranchName
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:heading {"level":1} -->
<h1>3. Tags</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>3.1 List All Tags</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
{% highlight ruby %}
git tag
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>3.2 Delete a Tag</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
{% highlight ruby %}
git tag -d TagName
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>3.2 Sync Local/Remote Tags</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
{% highlight ruby %}
git fetch --prune --tags
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:heading {"level":1} -->
<h1>4. Subtress</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>4.1 Add a new Subtree from a remote repository</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
{% highlight ruby %}
git subtree add --prefix LocalFolder RemoteRepoURL.git BranchName --squash
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>4.2 Update a Subtree from a remote repository</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
{% highlight ruby %}
git subtree pull --prefix LocalFolder RemoteRepoURL.git BranchName --squash
{% endhighlight %}
<!-- /wp:shortcode -->

<!-- wp:heading -->
<h2>4.2 Remove a Subtree</h2>
<!-- /wp:heading -->

<!-- wp:shortcode -->
{% highlight ruby %}git remote rm LocalFolder{% endhighlight %}
<!-- /wp:shortcode -->
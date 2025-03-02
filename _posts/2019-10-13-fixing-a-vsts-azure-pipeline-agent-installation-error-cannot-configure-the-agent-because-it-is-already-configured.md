+++
id: 249
title: 'Fixing a VSTS Azure Pipeline Agent installation Error: Cannot configure the agent because it is already configured.'
date: 2019-10-13T20:11:46+01:00
github_comments_issueid: "4"
author: mattselkey
layout: post
guid: https://mattselkey.com/?p=249
permalink: /fixing-a-vsts-azure-pipeline-agent-installation-error-cannot-configure-the-agent-because-it-is-already-configured/
categories:
  - DevOps
tags:
  - Azure
  - DevOps
  - TFS
+++
<!-- wp:paragraph -->
<p>Recently while setting up an On-premises Azure DevOps server I came across a few issues installing and configuring a  VSTS  Azure Pipelines  Agent. During the configuration phase an error reported that the agent was already configured.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"left","id":250,"width":858,"height":93,"sizeSlug":"full","className":"is-style-default"} -->
<div class="wp-block-image is-style-default"><figure class="alignleft size-full is-resized"><img src="https://mattselkey.com/wp-content/uploads/2019/10/image.png" alt="" class="wp-image-250" width="858" height="93"/></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>I'd been troubleshooting the previous agent install which was reporting as offline even though it was installed and eventually decided to manually uninstall the agent (that issue was certificate based, but that's another story!). </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>After a little investigation it turned out the error message was due to  hidden configuration files which where not removed during the previous manual uninstall. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>To view these files, browse to the folder the agent was installed in, in Explorer choose <strong>View</strong> and ensure "<strong>Hidden items</strong>" is ticked, as shown below.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":252,"width":872,"height":317,"sizeSlug":"full"} -->
<figure class="wp-block-image size-full is-resized"><img src="https://mattselkey.com/wp-content/uploads/2019/10/image-2.png" alt="" class="wp-image-252" width="872" height="317"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Remove all of the . files</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":251,"width":803,"height":286,"sizeSlug":"full"} -->
<figure class="wp-block-image size-full is-resized"><img src="https://mattselkey.com/wp-content/uploads/2019/10/image-1.png" alt="" class="wp-image-251" width="803" height="286"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The simply rerun config.cmd and complete the configuration as normal.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":253,"width":500,"height":107,"sizeSlug":"full"} -->
<figure class="wp-block-image size-full is-resized"><img src="https://mattselkey.com/wp-content/uploads/2019/10/image-3.png" alt="" class="wp-image-253" width="500" height="107"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>One complete the service should be up and running</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":257,"width":535,"height":78,"sizeSlug":"full"} -->
<figure class="wp-block-image size-full is-resized"><img src="https://mattselkey.com/wp-content/uploads/2019/10/image-6.png" alt="" class="wp-image-257" width="535" height="78"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>And the agent online and enabled.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":255,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://mattselkey.com/wp-content/uploads/2019/10/image-5.png" alt="" class="wp-image-255"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

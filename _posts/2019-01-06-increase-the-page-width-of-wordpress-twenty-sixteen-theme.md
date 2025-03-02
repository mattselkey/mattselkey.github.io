+++
id: 112
title: Increase the page width of the WordPress Twenty Sixteen theme.
date: 2019-01-06T22:33:02+01:00
github_comments_issueid: "2"
author: mattselkey
layout: post
guid: https://mattselkey.com/?p=112
permalink: /increase-the-page-width-of-wordpress-twenty-sixteen-theme/
categories:
  - CSS
  - webdevelopment
  - Wordpress
+++
<p style="text-align: justify;">One issue I've found with the built-in WordPress themes (especially the Twenty Sixteen theme) is that when using images in a post they are not aligned correctly on the page.</p>
<p style="text-align: justify;">After firing up Chrome development tools and checking out the elements on the page it is clear that the main culprit for this is the post comment/date stamp element taking up a big part for the left hand of the page, as shown below:</p>
<img class="aligncenter size-full wp-image-114" src="https://mattselkey.com/wp-content/uploads/2019/01/2019-01-06-15_55_31-Matthew-S-Key-–-IT-_-Scripting-_-Automation-_-Coding-_-Endurance-Sport.png" alt="2019-01-06 15_55_31-Matthew S Key – IT _ Scripting _ Automation _ Coding _ Endurance Sport" width="937" height="286" />

This can easily be fixed by overriding one CSS element.

To do this, logon to your site's WordPress, click on '<strong>Appearance</strong>', then '<strong>Edit CSS</strong>'.

<img class=" size-full wp-image-115 aligncenter" src="https://mattselkey.com/wp-content/uploads/2019/01/2019-01-06-15_41_21-Dashboard-‹-Matthew-S-Key-—-WordPress.png" alt="2019-01-06 15_41_21-Dashboard ‹ Matthew S Key — WordPress.png" width="335" height="284" />

Next, click on '<strong>Additional CSS</strong>'

<img class=" size-full wp-image-116 aligncenter" src="https://mattselkey.com/wp-content/uploads/2019/01/2019-01-06-15_42_40-Customize_-Matthew-S-Key-–-IT-_-Scripting-_-Automation-_-Coding-_-Endurance-Spor.png" alt="2019-01-06 15_42_40-Customize_ Matthew S Key – IT _ Scripting _ Automation _ Coding _ Endurance Spor" width="339" height="209" />

Add the following snippet of CSS into the text box

[cc lang="css" escaped="true"  line_numbers="true" nowrap="false"]
body:not(.search-results) article:not(.type-page) .entry-content {
float: none;
width: 100%;}
[/cc]

It should appear as shown below:

<img class=" size-full wp-image-117 aligncenter" src="https://mattselkey.com/wp-content/uploads/2019/01/2019-01-06-15_43_12-Customize_-Matthew-S-Key-–-IT-_-Scripting-_-Automation-_-Coding-_-Endurance-Spor.png" alt="2019-01-06 15_43_12-Customize_ Matthew S Key – IT _ Scripting _ Automation _ Coding _ Endurance Spor" width="343" height="221" />

Finally click on '<strong>Publish</strong>'

<img class=" size-full wp-image-118 aligncenter" src="https://mattselkey.com/wp-content/uploads/2019/01/2019-01-06-15_43_33-Customize_-Matthew-S-Key-–-IT-_-Scripting-_-Automation-_-Coding-_-Endurance-Spor.png" alt="2019-01-06 15_43_33-Customize_ Matthew S Key – IT _ Scripting _ Automation _ Coding _ Endurance Spor" width="352" height="159" />
<p style="text-align: justify;">Any future posts should appear with the comment/time stamp elements at the bottom of the page and the width of the post should now increase.</p>
<img class=" size-full wp-image-119 aligncenter" src="https://mattselkey.com/wp-content/uploads/2019/01/2019-01-06-15_54_48-Matthew-S-Key-–-IT-_-Scripting-_-Automation-_-Coding-_-Endurance-Sport.png" alt="2019-01-06 15_54_48-Matthew S Key – IT _ Scripting _ Automation _ Coding _ Endurance Sport" width="624" height="349" />

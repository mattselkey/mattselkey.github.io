---
title: "Fixing a VSTS Azure Pipeline Agent installation Error: Cannot configure the agent because it is already configured."
date: "2019-10-13"
author: "mattselkey"
categories: ["DevOps"]
tags: ["Azure","DevOps","TFS"]
---

Recently while setting up an On-premises Azure DevOps server I came across a few issues installing and configuring a VSTS Azure Pipelines Agent. During the configuration phase an error reported that the agent was already configured.

<div style="float: left">
![Azure Pipelines Agent configuration error](https://mattselkey.com/wp-content/uploads/2019/10/image.png)
</div>

I'd been troubleshooting the previous agent install which was reporting as offline even though it was installed and eventually decided to manually uninstall the agent (that issue was certificate based, but that's another story!).

After a little investigation it turned out the error message was due to hidden configuration files which where not removed during the previous manual uninstall.

To view these files, browse to the folder the agent was installed in, in Explorer choose **View** and ensure "**Hidden items**" is ticked, as shown below.

![Showing hidden files in Explorer](image-2.png)

Remove all of the . files

![Hidden agent configuration files](image-1.png)

The simply rerun config.cmd and complete the configuration as normal.

![Successful agent configuration](image-3.png)

One complete the service should be up and running

![Agent service running](image-6.png)

And the agent online and enabled.

![Online agent status](image-5.png)

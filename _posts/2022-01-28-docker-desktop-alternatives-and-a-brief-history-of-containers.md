---
id: 1000
title: 'Docker Desktop Alternatives and of Brief History of Containers.'
date: 2022-01-28T21:34:00+00:00
github_comments_issueid: "5"
author: mattselkey
layout: post
guid: https://mattselkey.com/?p=1000
published: true
categories:
  - Containers
tags:
  - Containers
  - DevOps
  - Docker
---

# Introduction

If you are a user of Docker Desktop (DD), then it's likely you would have received an email in the past month reminding you that the grace period for those needing to transition from the
[free to paid subscription](https://www.docker.com/blog/the-grace-period-for-the-docker-subscription-service-agreement-ends-soon-heres-what-you-need-to-know) is coming to an end. 

This announcement has created panic for some, under the impression that they would be soon be without a tool seen as vital for daily work, unless their employers (for teams larger than 5) paid out a very modest 7 or 21 dollars per month (depending on team size).

The question on everyone's lips, are there any alternatives? 

**The TLDR is: Yes.** However, before we get to that, I wanted to briefly cover the history of containers and how DD fits into the ecosystem.

# Container History

Before docker, containers already had a very long history, a non-exhaustive list of this is shown below[^1]:

* 1999 - Jails was added to FreeBSD by [Poul-Henning Jamp](https://en.wikipedia.org/wiki/FreeBSD_jail) in 1999 and released in version 4.0 of FreeBSD in [2000](https://www.freebsd.org/releases/4.0R/announce/).
* 2001 - [Linux-VServer](https://en.wikipedia.org/wiki/Linux-VServer) was added to Linux by Jacques Gélinas.
* 2004 - Solaris Zones was added to Sun Microsystems Solaris OS.
* 2006 -  Paul Menage's [proposal](https://www.kernel.org/doc/ols/2007/ols2007v2-pages-45-58.pdf) lead to lead to the introduction of generic process containers being added to the [Linux kernel](https://lkml.org/lkml/2006/10/20/251). cgroups allowed processes to be grouped together, with a share of cpu, memory and disk I/O
* 2008 - User namespaces were implemented into the kernel, allowing a process to have it’s own set of users - a process could have root privileges inside a container (but not outside)
* 2009 - IBM’s LXC (LinuX Containers) project added userspace tooling on top of the cgroups and namepsaces  - that is - tools such as an interactive shell, creating containers, listing, starting, pausing, resuming and destroying containers - see [LXC: Linux container tools](https://developer.ibm.com/tutorials/l-lxc-containers/#tools-liblxc) 
* 2013 - Docker was announced. Originally Docker used LXC and added additional tooling for developers
* 2014 - Kubernetes (k8s) was announced by [Google](https://cloudplatform.googleblog.com/2014/06/an-update-on-container-support-on-google-cloud-platform.html), version 1.0 finally being released in 2015 
* 2015 - runC spun out from the main code - runC was a lightweight, portable container runtime.
  - There was no dependency on the rest of the Docker platform: just the container runtime and nothing else.
  - The goal of runC was make standard containers available everywhere.
  - The code for runC was donated the code to the Open Container Project (OCP foundation). OCP was renamed to the Open Container Initiative (OCI)
* 2020 - k8s deprecated the docker runtime - instead pushes support for the Container Runtime Interface (CRI) [1]
> "If you are using Docker for building your application containers, you can still run these containers on any container runtime. This use of Docker does not count as a dependency on Docker as a container runtime."[^2]
* 2021 - Docker announces a new subscription for professionals and businesses [model](https://www.docker.com/blog/updating-product-subscriptions/)

# Why You Don't Need Docker Desktop

As you can see above, containerization has a long history, of which Docker plays only a small, but significant part.
As a docker user, more often than not, the end goal is to push the final image to k8s. 

> "The image that Docker produces isn’t really a Docker-specific image—it’s an OCI (Open Container Initiative) image. Any OCI-compliant image, regardless of the tool you use to build it, will look the same to k8s."[Kubernetes.io](https://kubernetes.io/blog/2020/12/02/dont-panic-kubernetes-and-docker/)

The main point to note here is that as long as the image being build implements the OCI specification it will be supported by any component of the cloud native landscape, including k8s.
Docker Desktop (DD) is not the only software on which OCI images can be built. 
Additionally, although DD provides a k8s environment on which you can deploy and test containers, there are also alternatives to this feature which can be run stand-alone or side-by-side with DD.

# Features and Alternatives

Let's dig into DD's feature set.
In addition to the nice GUI, DD provides the following base features:

|  Feature | Purpose  | Stand-alone install  |  Alternatives? | Notes  |
|---|---|---|---|---|
| Docker Engine  |  The Docker daemon (dockerd) can build and containerize application |  Yes | Yes   |   |
| Docker CLI client  | The CLi allows users to control and interact with dockerd  | Yes  |  Yes |   |
| Docker Compose  | Define and run multi containers in a single dockerfile (docker-compose.yml).  |  Yes |  Yes |   |
| Content trust in Docker  | > "Content trust gives you the ability to verify both the integrity and the publisher of all the data received from a registry over any channel"  |  Yes |   |   |
| Kubernetes  | Built in k8s cluster  | No  | Yes - minikube, k3s,  |   |
| Credential Helper |  docker-credential-helpers is a suite of programs to use native stores to keep Docker credentials safe. |  Yes | Yes  |   |

From this list, the big attraction is the built in k8s support. 
There are lots of alternatives which can be used to install a micro k8s cluster, however only one provides a DD like experience and that is Rancher Desktop (RD).

Just like DD, RD includes a nice GUI, the option to choose a version of k8s which fits your dev environment, support for Docker compose and Cli support via [nerdctl](https://github.com/containerd/nerdctl)
[RD](https://rancherdesktop.io) just hit v1.0 (as of 26.01.2022) and if you want an excellent review of it, check out DevOps Toolkit's [YouTube channel](https://www.youtube.com/watch?v=evWPib0iNgY)

# Footnotes
[^1]: This list was compiled using the excellent post by Tim Hildred over at [Redhat](https://www.redhat.com/en/blog/history-containers) as a starting point.
[^2]: Check whether Dockershim deprecation affects you, [kubernetes.io](https://kubernetes.io/docs/tasks/administer-cluster/migrating-from-dockershim/check-if-dockershim-deprecation-affects-you/)


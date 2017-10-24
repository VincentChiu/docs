---
author:
  name: Bob Strecansky
  email: bob.strecansky@gmail.com 
description: 'This guide describes how to effectively use Docker in production.  Included are best practices in Docker versioning, environments, setup, image management, TODO 	'
keywords: 'docker,production,compose,deployment'
license: '[CC BY-ND 4.0](https://creativecommons.org/licenses/by-nd/4.0)'
published: Monday, October 23rd, 2017
modified: Monday, October 23rd, 2017
modified_by:
  name Bob Strecansky
title: 'How to Use Docker Effectively in Production'
contributor:
  name: Bob Strecansky
  link: https://twitter.com/bobstrecansky
  external_resources:
- '[Docker](https://www.docker.com/)'

---

{: .note}
> The steps in this guide require root privileges. Be sure to run the steps below as `root` or with the `sudo` prefix. For more information on privileges, see our [Users and Groups](/docs/tools-reference/linux-users-and-groups) guide.

## Disclaimer

This guide uses well-tested packages for Production (Ubuntu 16.04 LTS for the Docker Host, Docker Community Edition as the Docker package, and Ubuntu 16.04 LTS for the base container, 

##Initial Steps

1.  Install Docker using the [Linode Docker Installation Guide](https://www.linode.com/docs/applications/containers/how-to-install-docker-and-pull-images-for-container-deployment) on the hosts that you're planning on running Docker on.  It is extremely prudent that you use a consistent docker version across the nodes that are going to run your Docker containers (the guide listed above uses Docker CE (Community Edition) which is a good choice from a stability perspective).

2.  Determine a base Docker image strategy that you'd like to use for your web application or site.  If you determine that you'd like to use the latest Ubuntu LTS version, then follow along below with Using the Latest Ubuntu LTS Image.  If you want to make sure that you have a deployment that maintains the same OS underneath, you can use the Creating a Private Docker Registry section below.  This decision is a tradeoff - If the website or web application you are developing is unlikely to stop functioning with an OS upgrade, then it's extremely advantageous to utilize an image that is maintained by Ubuntu, both from a performance and a security perspective.  If you decide that you'd like to maintain your own underlying operating system, make sure you often update the base image that you choose so that you get the latest (security patched) versions of OS level packages.


3.  Validate that you're running the current LTS kernel on your platform, this will ensure that you have as few driver issues as possible.  At the time of writing, Ubuntu 16.04 is using ai4.10.0-37-generic #41~16.04.1-Ubuntu SMP kernel.  You can find this with
`uname -a`

## Using the Latest Ubuntu LTS Image:
docker pull ubuntu:latest

Dockerfile:
`from ubuntu:latest`

## Creating a Priate Docker Registry:
1.  Create a [Private Docker Registry](https://docs.docker.com/registry/deploying/) in order to maintain your own private docker container images.  You'll want to configure a registry such as the one []

2.  Come up with a process to clean old Docker images, as the old containers tend to take up lots of disk space with no utilization.
    `docker images -q -a | xargs --no-run-if-empty docker rmi`



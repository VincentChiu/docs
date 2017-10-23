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

Docker is becoming increasingly popular among software developers, operators and enterprises as a software container platform. Containers package software in a format that can run isolated on a shared operating system. Bundled with only essential libraries and settings, Docker renders lightweight, efficient self-contained systems that run identically wherever deployed.

{: .note}
> The steps in this guide require root privileges. Be sure to run the steps below as `root` or with the `sudo` prefix. For more information on privileges, see our [Users and Groups](/docs/tools-reference/linux-users-and-groups) guide.



##Installation

1.  Install Docker:



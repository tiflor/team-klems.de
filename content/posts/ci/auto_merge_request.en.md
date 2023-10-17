---
title: "Automatically create a merge request with GitLab-CI"
date: 2023-10-06T18:40:01+02:00
tags: [""]
categories: ["" ]
author: "Jörg Klems"
showToc: false
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Never forget to create a merge request, let's create it with GitLab-CI"
#canonicalURL: "https://canonical.url/to/page"
disableHLJS: false # to disable highlightjs
disableShare: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
#cover:
#    image: "<image path/url>" # image path/url
#    alt: "<alt text>" # alt text
#    caption: "<text>" # display caption under cover
#    relative: false # when using page bundles set this to true
#    hidden: true # only hide on current single page
---

Have you ever forget to create a merge request for your new branch?

Ever search for the work off somebody else in a branch where you unsure if it is ready or worked on?

Are you run GitOps and need to promote your environment through different branches?

Let's create the merge request with GitLab-CI.

## Preparation

To start we need to prepare the repository, we need to have a GitLab access token with api access and the role necessary, mostly developer, to create the merge request.
This token then needs to be available in GitLab CI variable which can be easiest done with glab.
The name of the variable is `MR_TOKEN`, the token itself has to be pasted into the command.

```bash
glab variable set MR_TOKEN <Put your token here>  -m
```

## The CI job

code is [here.](https://gitlab.com/tiflor/auto_mr_creation_demo/-/blob/main/gitlab-ci/create_mr.yml?ref_type=heads)

{{< gitlab src="tiflor/auto_mr_creation_demo/-/raw/22e36f3d88ccb8c61e77d6dc1b59859c48b6b94b/gitlab-ci/create_mr.yml" language="yml" >}}

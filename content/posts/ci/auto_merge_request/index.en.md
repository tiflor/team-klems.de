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

Merge requests like gitlab is naming them or pull requests like github is naming them are a great feature in my opinion.
They summarize the changes done, to reach a dedicated goal and enable us to discuss and share the changes done.
But what if you or somebody else forgot to create a merge request for your development branch?
Or you run GitOps and need to promote your environment through different branches, do you want to create and merge manually?

There is a solution for this challenge, the merge request can be created via you CI in this case via Gitlab-CI.

## Preparation

To start we need to prepare the repository.
A GitLab access token with api access permission and the role necessary, mostly developer, to create the merge request, is needed.
This token then needs to be available in GitLab CI variable which can be easiest done with glab.
The name of the variable is `MR_TOKEN`, the token itself has to be pasted into the command.

```bash
glab variable set MR_TOKEN <Put your token here>  -m
```

Alternative the ci variable can be set via the UI.
Both option shall end with a picture similar to the this one.

![CI Variable in Gitlab CI](images/auto_merge_request-CI_variables.png)
If done in an environment with dedicated access permissions, adapt the environment parameter of the CI variable.

## The CI job



code is [here.](https://gitlab.com/tiflor/auto_mr_creation_demo/-/blob/main/gitlab-ci/create_mr.yml?ref_type=heads)

{{< gitlab src="tiflor/auto_mr_creation_demo/-/raw/main/gitlab-ci/create_mr.yml" language="yml" >}}

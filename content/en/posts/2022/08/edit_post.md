---
title: "Edit posts"
date: "17.08.2022"
tags: ["hugo", "config"]
author: "Jörg Klems"
showToc: false
TocOpen: false
draft: true
hidemeta: false
comments: false
description: "Fix edit posts feature of hugo and PaperMod"
#canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
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
editPost:
    URL: "https://github.com/tiflor/team-klems.de/tree/edit_post/content/en/"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---


The hugo theme PaperMod which I use for this site, has a nice function to [editPost](https://github.com/adityatelange/hugo-PaperMod/wiki/Features#edit-link-for-posts) which adds a kind of edit button on each page which leads to the source of the page to quickly fix and change the page content.
If really like this feature but I was kind of unable to use it in the right way from the beginning.
This post is now used to figure out a working solution.

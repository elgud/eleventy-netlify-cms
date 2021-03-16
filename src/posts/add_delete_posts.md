---
title: How to Add and Delete Posts 
description: How to add and delete posts in the eleventy base blog.
date: 2021-02-06
tags:
  - add-post
  - delete-post
  - eleventy-base-blog
layout: layouts/post.njk
---

This is a post to simply see how to 
1. add a post
2. delete a post

**It is probably best to not make major content changes with the server running. Doing so can mess up _site in strange ways.**

## To add a post: 
1. simply create a new file in posts with an appropriate name, 
2. cut and paste the header from a previous post and edit,
3. add your content in markdown

Avoid copying a post and renaming it when the server is running. Doing this messes up _site. 

## To delete a post:
1. stop the server
2. delete the .md file containing the post
3. start the server


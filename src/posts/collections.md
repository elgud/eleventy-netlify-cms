---
title: Collections in Eleventy 
description: How the collections in Eleventy work and how to create a new set of pages that act like the blog posts but are separate from them.
date: 2021-02-16
tags:
  - eleventy-base-blog
  - collections
layout: layouts/post.njk
---
The eleventy base blog creates a collections of posts that can be accessed using collections[posts]. This is created automatically. You create a new post you just add a new .md file (or html) to the posts folder, calling it anything you like. Everything in that directory gets added to collections[posts].

The question is how and how can you create new collections. So for example as well as a collection of posts you might want a collection of services, or products, or perhaps basic information about animals, or houses. There are all kinds of things you might want to create a collection of depending on the purpose of your website.

## How do collections work?

Basically, all pages are added to 'collections' automatically. You can access all of them using collections.all (see sitemap.xml.njk). Pages include

1. All files with .njk, .md, or .html
2. All tag pages. These are pages that are automatically generated. There is page for each tag. 

If there are pages that you do not want to include these should be added to .eleventyignore.

There is a function in .eleventy.js that creates a list of tags: tagList.

The key tags 'out of the box' are 

- posts for the blog posts 
- nav for navigation. This is set up via eleventyNavigation
- tagList

The collections are used 'out of the box':

- collections.posts (archive.njk, post.njk, index.njk)
- collections.all (page-list.njk, sitemap.xml.njk)
- collections.tagList (tags-list.njk)
- collections[ tag ] tags.njk 

At present only posts have tags (other than nav). If you want to separate tags into groups depending on page types, you will have to change some of the code. So you would have to first get the collection of "posts" tags or the collection of "animal" tags, for example, and then collect the tags for those. 

The simplest way could be to modify eleventy.js and create functions that gather various 'tagList's perhaps as well as the full one.

Where there are tags, you can access a sub-collection of tags via collections.tag-name as illustrated above. So to create a group of pages you give them all the same tag (example in your case).

The posts.json file simply adds the tag of 'post' to all the .md files in the directory. Looking at the posts in posts directory none have an explicit tag of post because this is added by posts.json.  Therefore they can be accessed via collections.posts.

The file postlists.njk in _includes is generic code to display a list of pages associated with a tag. So archive.njk sets a variable called postslist and passes this too postlist.njk by including the code from postlist.njk. So you can write an alternative archive.njk that sets variable postslist to collections.tag-name as is done in tags.njk.



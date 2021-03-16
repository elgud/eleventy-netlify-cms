---
title: Structure of Eleventy Base Blog
description: An exploration of the file structure of the Eleventy Base Blog
date: 2021-02-07
tags:
  - file-structure
  - eleventy-base-blog
layout: layouts/post.njk
---

## Eleventy
Eleventy transforms a directory of templates (of varying types) into HTML It deploys to Netlify.

The templates it supports are: Liquid, Nunjucks, Handlebars, HTML, Markdown, EJS,Haml, Pug, Javascript

The Eleventy [website](https://www.11ty.dev) is https://11th.dev
[Documentation](https://www.11ty.dev/docs) is at https://www.11ty.dev/docs though these are of limited help if you do not know the template technology in the above list.

There is some information in README.md

The templates used in the base blog are Markdown (.md) and nunjucks (.njk).

eleventy.js has config information. This says
- The template formats used are md, njk, html, and liquid
- The markdown template engine is liquid
- The html template engine is nunjucks (njk)
- The data template engine is nunjucks (njk)

nunjucks is a templating language for javascript, written my [mozzilla](https://www.mozilla.github.io/nunjucks)

liquid is a template language created by shopify. It is written in Ruby adn is used by many other web apps including jekyll (which is used by GitHub).

Eleventy base blog also makes use of json.

## The folder _site
_site is not included in the git changes. It gives a good starting point for working out what the code actually does. _site contains the following directories:

<div class="table-responsive">
    <table class="table table-hover table-bordered border-primary align-middle">
        <thead>
            <tr>
                <th>folder</th><th>files</th><th>comment</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>about</td><td>index.html</td><td>the about page</td>
            </tr>
            <tr>
                <td rowspan="2">css</td>
                <td>index.css</td><td>css for blog pages</td>
            </tr>
            <tr>
                <td>prism-base16-monokai.dark.css</td>
                <td>css for how code (```) should look</td></tr>            
            </tr>
            <tr>
                <td rowspan="3">feed</td>
                <td>.htaccess</td><td>.htaccess file</td>
            </tr>
            <tr>
                <td>feed.json</td><td>json file of contents of whole site</td>
            </tr>
            <tr>
                <td>feed.xml</td><td>xml file of contents of whole site</td>
            </tr>
            <tr><td>img</td><td>.gitkeep</td><td>.gitkeep is empty</td></tr>
            <tr><td>page-list</td><td>index.html</td>
                 <td>table of all pages with their links and titles</td>
            </tr>
            <tr><td rowspan="5">posts</td><td>index.html</td>
                <td>Archive page: list of blog posts with links</td>
            </tr>
            <tr>
                <td>firstpost/index.html</td>
                <td rowspan="4">pages each containing a blog post</td>
            </tr>
            <tr><td>secondpost/index.html</td></tr>
            <tr><td>thirdpost/index.html</td></tr>
            <tr><td>fourthpost/index.html</td></tr>
            <tr><td rowspan="4">tags</td><td>index.html</td>
                <td>A page showing a list of tags in button format to click. Clicking takes you to the appropriate page below.</td>
            </tr>
            <tr><td>another-tag/index.html</td>
                <td rowspan="3">A list of blog posts with the tag in question.</td>
            </tr>
            <tr><td>number-2/index.html</td></tr>
            <tr><td>second-tag/index.html</td></tr>
        </tbody>
    </table>
</div>

Then there are three single files in _site:
<div class="table-responsive">
    <table class="table table-hover table-bordered border-primary align-middle">
        <thead>
            <tr>
                <th>file</th><th>comment</th>
            </tr>
        </thead>
        <tbody>
        <tr><td>404.html</td><td>Page/Content not found error page</td></tr>
        <tr><td>index.html</td><td>home page</td></tr>
        <tr><td>sitemap.xml</td><td>list of urls of all pages in site with their last modified date in xml format.</td></tr>
        </tbody>
    </table>
</div>

## The files that construct the final html site files
The above html files are constructed by combining templates and content. The content of some of the files is generated automatically.

As above, we first look at the folders and then the individual files
<div class="table-responsive">
    <table class="table table-hover table-bordered border-primary align-middle">
        <thead>
            <tr>
                <th>folder</th><th>file</th><th>comment</th>
            </tr>
        </thead>
        <tbody>
        <tr><td>_data</td><td>metadata.json</td>
            <td>Top level information about the site such as title and description.</td>
        </tr>
        <tr><td>_includes</td><td>postslists.njk</td><td>Code for creating a chronologial list of posts and lists of posts by tag</td>
        </tr>
        <tr><td rowspan="3">_includes/layouts</td><td>base.njk</td>
            <td>HTML that goes in all pages: head, header, almost empty main, and (empty) footer. Uses metadata.json</td>
        </tr>
        <tr><td>home.njk</td><td>Template for home page. Uses base.njk, template-class: tmpl-home.</td>
        </tr>
        <tr><td>post.njk</td><td>Template for blog post pages. Uses base.njk, template-class: tmpl-post. Code for automatically providing links to next and previous posts.</td>
        </tr>
        <tr><td>about</td><td>index.md</td><td>content for about page (about/index.html) in markdown format</td>
        </tr>
        <tr><td rowspan="2">css</td><td>index.css</td><td rowspan="2">css files are copied to css directory in _site as is</td>
        </tr>
        <tr><td>prism-base16-monokai.dark.css</td></tr>
        <tr>
                <td rowspan="3">feed</td>
                <td>htaccess.njk</td><td>code to create an .htaccess file</td>
            </tr>
            <tr>
                <td>json.njk</td><td>code to create a json file of contents of whole site (feed.json)</td>
            </tr>
            <tr>
                <td>feed.njk</td><td>code to create an xml file of contents of whole site (feed.xml)</td>
            </tr>
            <tr><td>img</td><td>.gitkeep</td>Copied to _site as is</td></tr>
            <tr><td>node_modules</td><td>loads of directories</td><td>have not explored</td></tr>
            <tr><td rowspan="5">posts</td><td>firstpost.md</td>
                <td rowspan="4">Content for blog posts in markdown. One file for each post</td>
            </tr>
            <tr><td>secondpost.md</td></tr>
            <tr><td>thirdpost.md</td></tr>
            <tr><td>fourthpost.md</td></tr>
            <tr><td>posts.json</td><td>Add the tag 'posts' to all content files in the directory.</td>
            </tr>
        </tbody>
    </table>
</div>

<div class="table-responsive">
    <table class="table table-hover table-bordered border-primary align-middle">
        <thead>
            <tr>
                <th>file</th><th>comment</th>
            </tr>
        </thead>
        <tbody>
            <tr><td>404.md</td><td>Content for error page when a page is not found. Uses home.njk. Becomes 404.html</td>
            </tr>
            <tr><td>archive.njk</td><td>Uses home.njk and postlists.njk. Creates a list of posts. The page shown under Archive. Becomes posts/index.html</td>
            </tr>
            <tr><td>index.njk</td><td>Home page content. Uses home.njk. Generates a list of recent blog posts.</td>
            </tr>
            <tr><td>page-list.njk</td><td>Creates a table of links and titles that includes every page in the site.</td>
            </tr>
            <tr><td>sitemap.xml.njk</td><td>Generates sitemap.xml</td></tr>
            <tr><td>tags-list.njk</td><td>Creates tags/index.html in _site. Creates a list of tags that link to pages that list the posts where those tags are included. Uses home.njk</td>
            </tr>
            <tr><td>tags.njk</td><td>Uses home.njk and postslist.njk. Generates a page which lists the posts for a given tag.</td></tr>
        </tbody>
    </table>
</div>

### Other files
<div class="table-responsive">
    <table class="table table-hover table-bordered border-primary align-middle">
        <thead>
            <tr>
                <th>file</th><th>comment</th>
            </tr>
        </thead>
        <tbody>
            <tr><td>.editorconfig</td><td>Some editor settigs to do with indenting, white space and EOL.</td>
            </tr><td>.eleventy.js</td><td>Configuration file for eleventy</td>
            </tr>
            <tr><td>.eleventyignore</td><td>Just contains README.md. We don't want README to be part of the site.</td>
            </tr>
            <tr><td>package.json</td><td>json file to do with the package. Seems to alias npm commands.</td>
            </tr>
            <tr><td>README.md</td><td>Information about how to set up eleventy and the base blog</td>
            </tr>
        </tbody>
    </table>
</div>


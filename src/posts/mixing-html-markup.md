---
title: Mixing HTML and Markup
description: To what extent can you mix up html and markup in a post?
date: 2021-02-06
tags:
  - html
  - markup
layout: layouts/post.njk
---

This blog is about seeing to what extent it is possible to mix html and markup in a post.

According to the internet, anything surrounded by html markup tags is treated as is and not converted to HTML.

Lets test that. Writing
```
<section>
** bold text in a section with markup **
</section>
```
produces
<section>
** bold text in a section with markup **
</section>

So the internet is correct. Apparently there is a markup engine that will cope with this and interpret it as you would want, but this is not the default markup engine for eleventy. The default markup engine for eleventy is Liquid.

**This means that you cannot add semantic markup tags in markdown.**

Therefore to create a table, you are best sticking to pure html:
```
<table class="table">
  <tr>
    <th></th><th>col1</th> <th>col2</th>
  </tr>
    <th>row1</th><td>item1,1</td><td>item1,2</td>
  </tr>
  <tr>
    <th>row2</th><td>item1,1</td><td>item1,2</td>
  </tr>
</table>
  ```
This table has some bootstrap styling:
<table class=".table">
  <tr>
    <th></th><th>col1</th> <th>col2</th>
  </tr>
    <th>row1</th><td>item1,1</td><td>item1,2</td>
  </tr>
  <tr>
    <th>row2</th><td>item1,1</td><td>item1,2</td>
  </tr>
</table>



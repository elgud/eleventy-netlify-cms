---
title: Change the 404 page
description: The 404 page is not changed dynamically like the rest of the pages. This post explains why.
date: 2021-02-23
tags:
  - 404 page
  - eleventy-base-blog
layout: layouts/post.njk
---

The 404 page cannot be changed dynamically like other pages, although 404.html is changed dynamically in _site. In order for changes to take effect, ```npm start``` must be run.

The reason for this is the following code in .eleventy.js:

``` js/2/4
eleventyConfig.setBrowserSyncConfig({
    callbacks: {
      ready: function(err, browserSync) {
        const content_404 = fs.readFileSync('_site/404.html');
        browserSync.addMiddleware("*", (req, res) => {
          // Provides the 404 content without redirect.
          res.write(content_404);
          res.end();
        });
      },
    },
    ui: false,
    ghostMode: false
  });
```

This code ensures that _site/404.html is read when npm is started and stored in the browser. So the browser does not re-read 404.html when it is updated.



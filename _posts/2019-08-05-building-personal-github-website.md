---
layout: post
title: "Building Personal GitHub Website"
date: 2019-08-05
description: Brief documentation of the steps I took to get my website up and running.
tags: academic personal aug2019 github ruby html jekyll googleanalytics 
---

# 1. Opening a separate github account
I opened the username *`ryansunwork`* to host this page to keep it separate from my main *`ryanrsun`* github so that nobody would come read these blog posts. Thus the url is <https://ryansunwork.github.io>.

# 2. Install Ruby and Jekyll
I installed Ruby and Jekyll with Homebrew according to the guide at <https://jekyllrb.com/docs/installation/macos/>.

# 3. Pick a different theme
The themes supported by GitHub Pages are [here](https://pages.github.com/themes/). I picked the [Cayman](https://pages-themes.github.io/cayman/) theme. Its repository can be found [here](https://github.com/pages-themes/cayman). To change the theme of the site, change the line `theme: jekyll-theme-cayman` to `theme: jekyll-theme-minimal` or whatever other theme you would prefer. 

# 4. Edit the theme
You can make changes within the themes by "replacing" files found in the theme repository folders with identically-named files in your own website repository. For example, I copied the default.html file from the Cayman repository and
1. Commented out the google analytics code
2. Commented out the the skip-to-content link
3. Inserted my personal head.html in the header

The head.html is an *`include`*, which has its own *`_includes`* folder in the root directory. My head.html is itself a container for two more include files, *`analytics.html`* and *`collecttags.html`*. I configured the *`analytics.html`* file according to the directions from [here](https://desiredpersona.com/google-analytics-jekyll/)

The Cayman theme does not come with a *`post.html`*. I have created my own which takes the default layout, adds a date, adds some links, and adds a tagging system. When adding a date, I struggled to understand the html `class=""` system. These classes are apparently defined in the `_sass` folder of the theme repository. The links I added are just to go back to the blog and to the home page. It appears you need to add them within some structure like a `<span><\span>` block. You can break lines between spans with `<br />`. 

The tagging system I took from <http://longqian.me/2017/02/09/github-jekyll-tag/>. Tags go at the top of each post file in between the three dashes, like so: `tags: these are four tags`. Each tag is separated by white space, and it is recommended to use lowercase. In the *`_includes`* folder we have *`collecttags.html`*  to create a list *`site.tags`*. The tags are displayed at the bottom of each post thanks to *`_layouts/post`*. You then need to make a page for each tag (as well as a *`_layout`* page for the tag page formatting). This will be time confusing if you have hundreds or thousands of tags. Instead a tag generator script was provided, just make a *`tag`* folder and then run `python3 tag_generator.py` from the root directory to make a page for each tag.

# 5. Other random notes
* A markdown cheat sheet can be found [here](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf).
* I followed [this guide](http://jmcglone.com/guides/github-pages/) to get things up and running initially.
* I want to build a sitemap using [this](https://help.github.com/en/articles/sitemaps-for-github-pages) guide.
* I want to explore pagination using [this](https://jekyllrb.com/docs/pagination/) guide.
* I want a custom domain name using [this](https://help.github.com/en/articles/using-a-custom-domain-with-github-pages) guide.
* I want to explore commenting on blog posts using [discus](https://github.com/jmcglone/jmcglone.github.io/blob/master/_includes/disqus.html).
* I want to explore how I can make all the blog entries come one after the other, or at least link to the next one, without having to navigate back to the blog page each time.


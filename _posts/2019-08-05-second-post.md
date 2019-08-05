---
layout: post
title: "Building Personal GitHub Website"
date: 2019-08-05
desription: Brief documentation of the steps I took to get my website up and running.
tags: academic personal aug2019
---

# 1. Opening a separate github account
I opened the username `ryansunwork` to host this page to keep it separate from my main `ryanrsun` github so that nobody would come read these blog posts. Thus the url is <https://ryansunwork.github.io>.

# 2. Install Ruby and Jekyll
I installed Ruby and Jekyll with Homebrew according to the guide at <https://jekyllrb.com/docs/installation/macos/>

# 3. Pick a different theme
The themes supported by GitHub Pages are [here](https://pages.github.com/themes/). I picked the [Cayman](https://pages-themes.github.io/cayman/) theme. Its repository can be found [here](https://github.com/pages-themes/cayman). To change the theme of the site, change the line `theme: jekyll-theme-cayman` to `theme: jekyll-theme-minimal` or whatever other theme you would prefer. 

You can make changes within the themes by "replacing" files found in the theme repository folders with identically-named files in your own website repository. For example, if you would like to add a `head.html` file to the Minimal theme, create <pre class="prettyprint pre-scrollable"><code>permalink: /blog/:year/:month/:day/:title</code></pre>
 

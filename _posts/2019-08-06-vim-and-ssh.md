---
layout: post
title: "Vim and ssh"
date: 2019-08-06
description: Some vim shortcuts and using ssh keys for two different github accounts on one computer 
tags: academic personal aug2019 github ssh vim
---

# Some vim shortcuts
* `:set paste` makes it so that you don't get automatic indents when pasting large blocks of code.
* `:syntax on` turns on syntax highlighting. You can set this on your .vimrc also.
* `0` moves to the beginning of the current line.
* `$` moves to the end of the current line.
* `H` moves to the top of the current window.
* `M` moves to the middle of the current window.
* `L` moves to the bottom line of the current window.
* `1G` moves to the first line of the file.
* `20G` moves to the 20th line of the file.
* `G` moves to the last line of the file.
* `20j` moves 20 lines down.
* `e` moves to the end of the word.
* `w` moves to the beginning of the words.
* `3w` moves forward three words.
* `b` moves backward to the beginning of a word.
* `3b` moves backward three words.
* `)` jumps forward one sentence.
* `(` jumps backward one sentence.
* `}` jumps forward one paragraph.
* `{` jumps backward one paragraph.

# Managing Github accounts
I have two different github accounts (one main and one just for this blog) and I modify them from multiple computers (office laptop, personal laptop, office desktop). To work on the same account between different computers, use `git push origin master` as usual to push all your work online before leaving one computer. Then use `git pull origin master` to access this work from another computer that is "behind." Make sure the computer that is behind has not done any work since its last push, otherwise it might be difficult to merge.

To manage two different GitHub ssh accounts on the same computer, see [here](https://code.tutsplus.com/tutorials/quick-tip-how-to-work-with-github-and-multiple-accounts--net-22574) or [here](https://gist.github.com/jexchan/2351996). Basically you need to create a `config` file in `~/.ssh/` that calls your second account SECOND-ACC or something like that. Then do `git remote add origin git@SECOND-ACC:USERNAME/REPO.git` and you will be able to `git push origin master` normally.  

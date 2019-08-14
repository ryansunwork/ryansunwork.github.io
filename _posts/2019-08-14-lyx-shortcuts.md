---
layout: post
title: "LyX Shortcuts"
date: 2019-08-14
description: LyX shortcuts I should use more, and how to define your own shortcuts
tags: academic personal aug2019 lyx shortcuts
---

# PC and Mac differences
A lot of LyX help articles on the internet are written for PC. They say things like "Alt-m b" will write the following text under a bar." On a Mac, the Alt key they are referring to is the `control` key. So press `control` and `m` together, then press `b` to get this effect. When it says something like `Ctrl-m` to enter math mode, this means `command` and `m` together on a Mac.  

# Some shortcuts
* `control-m` will get you into a sort of "menu" mode that opens up a lot of other shortcuts, in particular the delimiters:
  * `control-[` immediately afterwards will get you square brackets that vary with the size of your expression inside.
  * `control-{` immediately afterwards will get you the varying size curly brackets.
  * `control-(` immediately afterwards will get you the varying size parentheses.
* `control-m g <letter>` will get you the corresponding Greek letter.
  * `command <letter`> will sometimes also get you that letter
* `control-m f` will get you a fraction.

# Customizing shortcuts
1. First navigate to *`/Users/rsun3/Library/Application Support/LyX-2.3/bind`* and create a *`user.bind`* file.
  * To figure out where to navigate, click `Lyx -> About Lyx` when you have the application open. It will give you both a Library Directory and a User Directory, pick the User Directory. Note that the other shortcut .bind files are in the Library Directory, but for whatever reason, if I place *`user.bind`* there, it doesn't work.
2. Because you want to keep most of the defaul bindings, start with `\bind_file mac.bind`. This automatically gives you all the original Mac bindings. Bindings that come later overwrite those that come earlier, so you can next overwrite them with your custom keys.
3. A typical binding line goes `\bind "C-g" "textstyle-update color 16"`. 
  * Here we are saying that `command` and `g` pressed at the same time will change the color to red.
  * The `-` means pressed at the same time. A space between two keys means one, then the other.
  * `C` means `command`, `A` means `option`, `M` means `control`, and `S` means `shift` on a Mac.
4. To see what the command you need to give LyX is, go to `View -> Messages Pane` on the top tool bar. Then click the Settings tab on the right, click the Selected radio button that comes up on the left, then double click `action - User commands` until the No changes to a Yes. Then click the Output tab again. Now do the action you want, and it should come up in the window with the command.
5. I bound `control-[number]` to common layouts like Title, Section, Itemize, etc.

# Notes
* I can't seem to bind `command-1` or any other number for whatever reason (maybe a system default shortcut), but you can bind `control-1`
* See [here](https://wiki.lyx.org/Tips/KeyboardShortcuts) for some more tips. 

---
layout: post
title: Setting up my dev environment
description:
summary:
img: /assets/coding_cominc.png
tags: [python, tools]
---

Configuration that I mention here are tailored in such a manner that I seek comfort in.
You can find all my configuration in [dotfiles](https://www.github.com/shiyanshirani/dotfiles){:target="_blank"} repository which I try to keep updated on frequent basis.

![coding-comic](/assets/setting_up_dev_environment_comic.png)


1. [MacBook Pro 2020 (Intel)](https://support.apple.com/kb/SP819?locale=en_US){:target="_blank"} - with this being my daily driver for work as well has personal use, it never failed me to get the work done with ease, if only I could ask for update is for Finder, sometimes it could get a lot more difficult to do the straight-forward chores.

2. [alacritty](https://github.com/alacritty/alacritty){:target="_blank"} - the most light-weighted terminal ever came across, as it is a terminal emulator it doesn't come with tab support so for that I complement it with [tmux](https://github.com/tmux/tmux/wiki/Getting-Started){:target="_blank"} with a cheeky way of using keymapings found on [Josh Medeski's notion](https://www.joshmedeski.com/posts/macos-keyboard-shortcuts-for-tmux/){:target="_blank"}

3. [yabai](https://github.com/koekeishiya/yabai){:target="_blank"} - a tiling management tool that snaps in tiles at lightining-fast speed which puts the native full-screen app tiling for macOS to absolute shame. *it's [i3](https://i3wm.org/){:target="_blank"} for unix.* I twin it with [skhd](https://github.com/koekeishiya/skhd){:target="_blank"} for keymapping with the addition of system-wide maps.

4. [nvim/vim](https://www.google.com) - personalized development environment (*PDE*). small-dive into my most used [plugins](#plugins) and [*story time*](#story time)

5. firefox -

<img src="/assets/firefox.png"  width="auto" height="auto">


```bash
os:         macOS Ventura (13.0.1)
shell:      zsh
terminal:   alacritty
wm:         yabai
```
/div
One of the hobbies I had way back since 2016 was for keyboards,  I spent ridiculous numbers of hours star-gazing [r/mkindia](https://www.reddit.com/r/mkindia/){:taget="_blank"} and [r/MechanicalKeyboards](https://www.reddit.com/r/MechanicalKeyboards/){:target="_blank"}, So I bought [Gamakay TK68](https://www.banggood.in/GAMAKAY-TK68-Mechanical-Keyboard-68-Keys-Triple-Mode-Connection-Wired-Type-C-or-BT5_0-or-2_4G-Wireless-with-Receiver-Gateron-Switch-XDA-Profile-PBT-Keycaps-Hot-Swappable-RGB-Gaming-Keyboard-p-1837263.html?cur_warehouse=CN&ID=515632){:target="_blank"} in 2020 and geared then up with Gateron Browns (*not bad for the beginners*).

<img src="/assets/gamakay.png"  width="auto" height="auto">



# plugins
1. `telescope.nvim` - by far the most used plugin
2. `vim-cool` - removes highlighted texts after buffer search when hit `return`.
3. `mason.nvim` - lets me install lsps, formatters, linters & daps on the go.


<hr>


image credits [xkcd.com](https://xkcd.com)

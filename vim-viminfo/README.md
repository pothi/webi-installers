---
title: vim-viminfo
homepage: https://webinstall.dev/vim-viminfo
tagline: |
  viminfo keeps track of Vim's state when switching between files
---

To update (replacing the current version) run `webi vim-viminfo`.

### Files

These are the files / directories that are created and/or modified with this
install:

```text
~/.local/share/vim/viminfo
~/.config/vim/plugins/viminfo.vim
~/.vimrc
```

## Cheat Sheet

> ~/.local/share/vim/viminfo stores cursor position, copy and paste buffers, command history,
> and a few other goodies. The defaults aren't always good, and should be
> tweaked.

In an age where we have terabytes of storage (rather than kilobytes of storage),
it makes sense to bump the size of Vim's copy buffers to match the full size of
largest code file you're likely to come across, and somewhere between several
hours and a few days worth of history.

This one-line plugin does just that.

### How to install manually

Create the file `~/.config/vim/plugins/viminfo.vim`. Add the same contents as
<https://github.com/webinstall/webi-installers/blob/main/vim-viminfo/viminfo.vim>.

That will look something like this:

```vim
" Tell vim to remember certain things when we exit
"  '100  :  marks will be remembered for up to 100 previously edited files
"  "20000:  will save up to 20,000 lines for each register
"  :200  :  up to 200 lines of command-line history will be remembered
"  %     :  saves and restores the buffer list
"  n...  :  where to save the viminfo files
set viminfo='100,\"20000,:200,%,n~/.local/share/vim/viminfo
```

Then create the directory `~/.local/share/vim/` to keep viminfo file.

Optionally, copy or move your existing viminfo file to `~/.local/share/vim/`.

Then `~/.vimrc` should be updated to include it:

```vim
" viminfo: reasonable defaults from webinstall.dev/vim-viminfo
source ~/.config/vim/plugins/viminfo.vim
```

# fzf.el [![MELPA](https://melpa.org/packages/fzf-badge.svg)](https://melpa.org/#/fzf)

An Emacs front-end for [fzf][1].

![demo](https://cloud.githubusercontent.com/assets/306502/12380684/ca0a6648-bd46-11e5-9091-841b282874e4.gif)

# My fork

This is a fork of bling/fzf.el. It looks like it was abandoned and stopped taking PRs, so I made some updates:

## Opening in splits

* `enter` opens a file in the previous buffer you were focused on
* `ctrl + s` opens a file in a horizontal split
* `ctrl + v` opens a file in a vertical split

## Choosing a files backend

`fzf/files-source` lets you choose between file backends. Defaults to `"find"`.

```elisp
(setq fzf/files-source "find") ;; uses a `find` based backend (slow)
(setq fzf/files-source "ripgrep") ;; uses a `ripgrep` based backend (fast)
(setq fzf/files-source "git")` ;; uses a `git ls-files` based backend (fast)
```

Or, you can use a `"custom"` source and use any UNIX command you want to build a list of files:

```elisp
(setq fzf/files-source "custom")
(setq fzf/files-source-custom-command "rg --files --ignore | sort")
```

## proximity-sort

If [proximity-sort](https://github.com/jonhoo/proximity-sort) is available, it will use that to sort file search results in proximity to the currrently open buffer.

If you install it to `~/.cargo/bin/proximity-sort` it should just work out of the box.

If you have a custom binary install, you can set it with:

```elisp
(setq fzf/proximity-sort-executable "/path/to/proximity-sort")
```

# installation

fzf.el can be installed through [MELPA][2].

# usage

`M-x fzf`

# license

GPL3

[1]: https://github.com/junegunn/fzf
[2]: https://melpa.org

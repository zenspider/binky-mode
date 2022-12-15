# binky-mode

[![License GPL 3](https://img.shields.io/badge/license-GPL_3-green.svg?style=flat)](LICENSE)
[![MELPA](http://melpa.org/packages/binky-mode-badge.svg)](http://melpa.org/#/binky-mode)

Jump between points like a rabbit !

This package provides commands to jump between points in buffers and files.
Marked position, last jump position and recent buffers are all supported in
same mechanism like `point-to-register` but with an enhanced experience.

<!-- markdown-toc start -->

**Table of Contents**

- [binky-mode](#binky-mode)
  - [Screenshot](#screenshot)
  - [Install](#install)
    - [dependencies](#dependencies)
    - [package](#package)
  - [Usage](#usage)
  - [Customization](#customization)
  - [Feature](#feature)
  - [Comparison](#comparison)
  - [Todo](#todo)
  - [License](#license)

<!-- markdown-toc end -->

## Screenshot

- Call `M-x binky-*` related command

![binky with preview](image/binky-preview.png)

`?` or `C-h` for popup preview mannually, `q`, `C-g` or `escape` for quit

- Call `M-x binky-margin-mdoe`

![margin with sign](image/margin-with-sign.png)

- Or use mark as indicator, `(setq binky-margin-string nil)`

![margin with mark](image/margin-with-mark.png)

## Install

### dependencies

- cl-lib

### package

- Manually

Clone and add to `load-path`, require the package.

- Melpa

This package is available on [MELPA][melpa].
Install with `M-x package-install` <kbd>RET</kbd> `binky-mode` from within Emacs.

## Usage

```elisp
;; Directly
(require 'binky-mode)
(binky-mode)

;; Or with `use-package`, etc
(use-package binky-mode
  :hook (after-init-hook . binky-mode))
```

- `binky-add` : add current positon to records
- `binky-delete` : delete existed position from records
- `binky-jump` : jump to position in records
- `binky-binky` : one command to rule all. With `C-u` prefix, keep editing untill quit
- `binky-margin-mode` : toggle to enable or disable margin indicator feature
- `binky-auto-toggle` : toggle to enable or disable auto-mark feature

## Customization

A lot of options are provided. See docstrings in file.

## Feature

- Better UI experience than `register-to-point`, such as preview customization and jump highlight
- Integration with buffers switch, and more sorting strategies are provided now and in future

## Comparison

- [Dogears](https://github.com/alphapapa/dogears.el)

  - Bookmark style record
  - More infomations: relevance, within, directory, etc

- [Binky-mode](https://github.com/liuyinz/binky-mode)

  - Register style record
  - Vim-like mark and jump
  - Flexible and customizable

I have used dogears for several months, and it's great in most features except so many information
I don't need. A better and avy-like jumping system is the top priority for me.

During time of using vim, what I missed most is [Vim-marks](https://vim.fandom.com/wiki/Using_marks). However,
evil is too heavy, so I write `binky-mode` to imitate part of features.

Enjoy it.

## Todo

- [x] Avoid duplicated records added
- [x] Buffer margin indicator support
- [ ] Support completing-read interface
- [ ] More sorting strategy: frecency, duration

## License

See [LICENSE](LICENSE).

[melpa]: http://melpa.org/#/binky-mode

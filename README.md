# Cloak-mode

[![MELPA](https://melpa.org/packages/cloak-mode-badge.svg)](https://melpa.org/#/cloak-mode)

Minor mode to cloak sensitive data

## Motivation

I used to use `hidepw` package but it only supports a plain list of regexs and also use font locking which have some conflicts with other packages, `cloak-mode` allows to setup a regex by major mode, which fits betters for my use case.

## Demo

![demo](./demo.gif)

## Installation

### Cloning the repo

Clone this repo somewhere, and add this to your config:

```elisp
(add-to-list 'load-path "path where the repo was cloned")

;; for example we load it for envrc files
(require 'cloak-mode)
(setq cloak-mode-patterns '((envrc-file-mode . "[a-zA-Z0-9_]+[ \t]*=[ \t]*\\(.*+\\)$")))
(global-cloak-mode)
```

### Using use-package

```emacs-lisp
(use-package cloak-mode
  :ensure t
  :config
  (global-cloak-mode))
```

### Using straight.el

```emacs-lisp
(use-package cloak-mode
  :straight (cloak-mode
             :type git
             :host github
             :repo "erickgnavar/cloak-mode")
  :config
  (global-cloak-mode))
```

## Examples

### Single pattern per mode

In case we need just one pattern we can define directly as a string

```elisp
(setq cloak-mode-patterns '((envrc-file-mode . "[a-zA-Z0-9_]+[ \t]*=[ \t]*\\(.*+\\)$")))
```

### Many patterns per mode

In case we need many patterns we can define a list of strings

```elisp
(setq cloak-mode-patterns '((envrc-file-mode . ("first-pattern" "second pattern"))))
```

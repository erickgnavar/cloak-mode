# cloak-mode

Minor mode to cloak sensitive data

## Installation

### Cloning the repo

Clone this repo somewhere, and add this to your config:

```elisp
(add-to-list 'load-path "path where the repo was cloned")

;; for example we load it for envrc files
(require 'cloak-mode)
(setq cloak-mode-patterns '((envrc-file-mode . "[a-zA-Z0-9_]+[ \t]*=[ \t]*\\(.*+\\)$")))
(add-hook 'envrc-mode-hook 'cloak-mode)
```

### Using straight.el

```emacs-lisp
(use-package cloak-mode
  :straight (cloak-mode
             :type git
             :host github
             :repo "erickgnavar/cloak-mode"))
```

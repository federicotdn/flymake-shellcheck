# flymake-shellcheck
[![Melpa Status](http://melpa.milkbox.net/packages/flymake-shellcheck-badge.svg)](http://melpa.milkbox.net/#/flymake-shellcheck)
![Melpa Status](https://img.shields.io/github/license/federicotdn/flymake-shellcheck.svg)

An Emacs (26+) Flymake handler for bash/sh scripts, using [ShellCheck](https://github.com/koalaman/shellcheck). Installing Flymake is not necessary as it is included in Emacs itself.

## Installation
First, make sure ShellCheck is installed by following [the installation guide](https://github.com/koalaman/shellcheck#installing). After that, you can install `flymake-shellcheck` by using the `package-install` command (make sure [MELPA](https://melpa.org/) is included in your package sources):

<kbd>M-x</kbd> `package-install` <kbd>[RET]</kbd> `flymake-shellcheck` <kbd>[RET]</kbd>

Alternatively, you can just add `flymake-shellcheck.el` to your `load-path`.

## Usage
To enable the Flymake backend whenever a bash or sh script is visited, add the following to your `init.el` file:

```el
(add-hook 'sh-mode-hook 'flymake-shellcheck-load)
```

If you're using [`use-package`](https://github.com/jwiegley/use-package), try this instead:

```el
(use-package flymake-shellcheck
  :commands flymake-shellcheck-load
  :init
  (add-hook 'sh-mode-hook 'flymake-shellcheck-load))
```

After opening a shell/sh file, remember to enable Flymake:

<kbd>M-x</kbd> `flymake-mode` <kbd>[RET]</kbd>

## License
Copyright © 2018 Federico Tedin.

Distributed under the GNU General Public License, version 3.

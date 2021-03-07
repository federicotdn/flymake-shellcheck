# flymake-shellcheck
[![MELPA](https://melpa.org/packages/flymake-shellcheck-badge.svg)](https://melpa.org/#/flymake-shellcheck)
![License](https://img.shields.io/github/license/federicotdn/flymake-shellcheck.svg)

An Emacs (26+) Flymake handler for bash/sh scripts, using [ShellCheck](https://github.com/koalaman/shellcheck). Installing Flymake is not necessary as it is included with Emacs itself.

## Installation
First, make sure ShellCheck is installed by following [the installation guide](https://github.com/koalaman/shellcheck#installing). After that, you can install `flymake-shellcheck` by using the `package-install` command (make sure [MELPA](https://melpa.org/) is included in your package sources):

<kbd>M-x</kbd> `package-install` <kbd>RET</kbd> `flymake-shellcheck` <kbd>RET</kbd>

Alternatively, you can just add `flymake-shellcheck.el` to your `load-path`.

## Usage
To enable the Flymake backend whenever a bash or sh script is visited, add the following to your `init.el` file:

```elisp
(add-hook 'sh-mode-hook 'flymake-shellcheck-load)
```

If you're using [`use-package`](https://github.com/jwiegley/use-package), try this instead:

```elisp
(use-package flymake-shellcheck
  :commands flymake-shellcheck-load
  :init
  (add-hook 'sh-mode-hook 'flymake-shellcheck-load))
```

After opening a shell/sh file, remember to enable Flymake:

<kbd>M-x</kbd> `flymake-mode` <kbd>RET</kbd>

## Customization

- You can set the `flymake-shellcheck-path` variable to the path of the ShellCheck executable in your system, in case `executable-find` wasn't able to find it automatically.
- You can set the `flymake-shellcheck-use-file` variable to `nil` if you wish to run the syntax checker on the contents of the buffer, rather than the contents of the file on disk (default: `t`).
- You can set the `flymake-shellcheck-allow-external-files` variable to `t` if you want to allow shellcheck to read external sources (it adds `-x` as argument, described in [the SC1091 docs](https://github.com/koalaman/shellcheck/wiki/SC1091), default: `nil`).

## License

Distributed under the GNU General Public License, version 3.

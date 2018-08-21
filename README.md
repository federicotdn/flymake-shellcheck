# flymake-shellcheck
An Emacs Flymake handler for bash/sh scripts, using [ShellCheck](https://github.com/koalaman/shellcheck).

## Installation
First, make sure ShellCheck is installed by following [the installation guide](https://github.com/koalaman/shellcheck#installing). After that, add `flymake-shellcheck.el` to your `load-path`.

## Usage
To enable the Flymake backend whenever a bash or sh script is visited, add the following to your `init.el` file:

```el
(require 'flymake-shellcheck)
(add-hook 'sh-mode-hook 'flymake-shellcheck-load)
```

## License
Copyright © 2018 Federico Tedin.

Distributed under the GNU General Public License, version 3

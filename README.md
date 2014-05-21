# gotest.el

Run [Go](http://golang.org) tests and programs from Emacs.

## Installation

The recommended way to install ``gotest.el`` is via [MELPA](http://melpa.milkbox.net/):

    M-x package-install gotest.el

Or [el-get](http://tapoueh.org/emacs/el-get.html):

    M-x el-get-install go-test

or [Cask](https://github.com/cask/cask):

	(depends-on "gotest.el")


## Usage

The following interactive commands can be run via <kbd>M-x</kbd> or
bound to a key of your choice.

All `go-test-*` functions can optionally configure the buffer-local
`go-test-args` variable to pass additional arguments.  Or, by using
a prefix command, you will be prompted for arguments.  For example:
<kbd>C-u M-x go-test-current-test</kbd>.

When using the `'_` prefix arg with any of the `go-test-*` or `go-run`
functions, the most recent arguments from history will be used without
prompting.  For example: <kbd>M-- M-x go-run</kbd>.

### go-test-current-test

Launch unit tests for the current test.

### go-test-current-file

Launch unit tests for the current file.

### go-test-current-project

Launch unit tests for the current project.

### go-run

Launch program via `go run`.  Optionally configure the buffer-local
`go-test-args` variable to pass additional arguments.  Or, by using
a prefix command, you will be prompted for arguments.  For example:
<kbd>C-u M-x go-run</kbd>.

Be sure to make use of minibuffer history (<kbd>C-r</kbd>) to recall
recent arguments to `go run`.  And remember that the <kbd>M--</kbd>
prefix can be used in combination with your `go run` key binding to
use the most recent arguments without prompting.  The go file is
included in history, so you can `go-run` from history regardless of
which buffer you are currently visiting.

### Example key bindings

You can create some key bindings with these commands:

```lisp
(define-key go-mode-map (kbd "C-x f") 'go-test-current-file)
(define-key go-mode-map (kbd "C-x t") 'go-test-current-test)
(define-key go-mode-map (kbd "C-x p") 'go-test-current-project)
(define-key go-mode-map (kbd "C-x x") 'go-run)
```

## Development

### Cask

``gotest.el`` use [Cask](https://github.com/cask/cask) for dependencies
management. Install it and retrieve dependencies :

    $ curl -fsSkL https://raw.github.com/cask/cask/master/go | python
    $ export PATH="$HOME/.cask/bin:$PATH"
    $ cask


### Tests

Launch unit tests :

    $ make clean test


## Support / Contribute

See [here](CONTRIBUTING.md)



## Changelog

A changelog is available [here](ChangeLog.md).


## License

See [LICENSE](LICENSE).


## Contact

Nicolas Lamirault <nicolas.lamirault@gmail.com>

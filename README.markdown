coda-cli -- Shell integration for Coda
======================================

http://justinhileman.info/coda-cli


`coda` makes Panic's Coda a first-class *nix citizen
----------------------------------------------------

This tool provides shell integration for [Coda](http://panic.com/coda). You can
now open files and directories from a terminal:

    coda foo.html
    coda foo.html bar.css
    coda ./

If `foo.html` or `bar.css` doesn't exist, `coda` will create it automatically
for you.

You can also edit a file and wait for it to close (`-w` or `--wait`). This is
really important if you plan on making `coda` your default `$EDITOR`. Now you
can use Coda for writing Git or SVN commit messages. Simply add this line to
your `.bash_profile` or `.bashrc` or `.zshrc`:

    export EDITOR='coda -w'

In addition to knowing how to wait, `coda` plays nice with pipes. You can use
it just like any other POSIX utility... Invoke it from the command line and pass
the output from any command to Coda, or from Coda to another command. Try a
couple of these:

    echo 'foo' | coda
    echo 'bar' | coda >> out.txt
    coda >> somefile.html
    find . -name "*.css" | xargs coda
    coda < config.yaml > config_new.yaml

Note that piping output from coda implies `--wait`.


Installation
------------

Make sure `coda` is executable and somewhere in your `$PATH`. The easiest way to
do that is with [Homebrew](http://mxcl.github.com/homebrew/) ...

    brew update
    brew install coda-cli

Or you can strike out on your own:

    mkdir -p /usr/local/bin
    curl https://raw.github.com/bobthecow/coda-cli/master/coda > /usr/local/bin/coda
    chmod 777 /usr/local/bin/coda


Usage
-----

    coda --help


License
-------

 * Copyright 2011 [Justin Hileman](http://justinhileman.com)
 * Distributed under the [MIT License](http://creativecommons.org/licenses/MIT/)

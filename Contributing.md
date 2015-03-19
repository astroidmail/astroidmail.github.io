# Contributing

Patches and pull-requests against the [master](https://github.com/gauteh/astroid) branch may be submitted either as a [pull-request](https://github.com/gauteh/astroid/pulls) here on github or as a patch (or series of) to:

* notmuch@notmuchmail.org
* astroidmail@googlegroups.com

Useful resources on how to contribute to a project using git can be found in the git-book [Contributing to a Project](http://git-scm.com/book/en/v2/Distributed-Git-Contributing-to-a-Project), specifically the part about [format-patch](http://git-scm.com/book/en/v2/Distributed-Git-Contributing-to-a-Project#Public-Project-over-E-Mail) and the [workflow for using different branches](http://git-scm.com/book/en/v2/Distributed-Git-Contributing-to-a-Project#Public-Project-over-E-Mail) (these will form a pull-request if you choose that path).

Contributions in the form of testing and documentation is also very welcome.

> All contributions must be made under the GNU GPL v3 licence or later.

## Coding style

* Two spaces for tabs
* Otherwise, refer to the existing code-base

## Tests

We use the [Boost Test](http://www.boost.org/doc/libs/1_57_0/libs/test/doc/html/index.html) suite, refer to the [test/](https://github.com/gauteh/astroid/tree/master/test) directory for how to set up a test. The [test_generic](https://github.com/gauteh/astroid/blob/master/test/test_generic.cc) may serve as a starting point. Remember to add the test to [test/.gitignore](https://github.com/gauteh/astroid/blob/master/test/.gitignore) and [test/SConscript](https://github.com/gauteh/astroid/blob/master/test/SConscript).

## Code completion in Vim using [YouCompleteMe](https://github.com/Valloric/YouCompleteMe)

[@ff2000](https://github.com/ff2000) set up YouCompletMe completion for astroid in vim as in issue [#14](https://github.com/gauteh/astroid/issues/14). We now include a default [.ycm_extra_conf.py](https://github.com/gauteh/astroid/blob/master/.ycm_extra_conf.py) created as described in issue [#14](https://github.com/gauteh/astroid/issues/14) and with the standard compile flags for on Arch Linux. To set up a `compile_commands.json` file one option is to use [bear](https://github.com/rizsotto/Bear) and to specify the current directory as the path to this file.

1. Install [YouCompleteMe](https://github.com/Valloric/YouCompleteMe)
1. Install [bear](https://github.com/rizsotto/Bear)
1. Make a `compile_commands.json` file by running: `devel/make_compile_commands.sh` in the source root.


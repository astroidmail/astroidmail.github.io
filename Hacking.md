# Hacking

> Also see [[Contributing]]  

Contributions to Astroid in the form of patches, documentation and testing are very welcome. The discussion will take place on github or on the mailinglists:

* notmuch@notmuchmail.org
* astroidmail@googlegroups.com

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
1. Edit `compilation_database_folder = ''` in [.ycm_extra_conf.py](https://github.com/gauteh/astroid/blob/master/.ycm_extra_conf.py) to read: `compilation_database_folder = DirectoryOfThisScript ()`
1. To ignore this change to `.ycm_extra_conf.py` [run](http://blog.pagebakers.nl/2009/01/29/git-ignoring-changes-in-tracked-files/): `git update-index --assume-unchanged .ycm_extra_conf.py`

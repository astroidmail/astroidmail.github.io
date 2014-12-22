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

## Code completion in Vim using YouCompleteMe

> Refer to issue [#14](https://github.com/gauteh/astroid/issues/14).
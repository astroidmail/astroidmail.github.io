C/C++ coding style
==================

Based on [notmuches STYLE](http://git.notmuchmail.org/git/notmuch/blob/HEAD:/devel/STYLE):

#### Indentation, Whitespace, and Layout


The following nonsense code demonstrates many aspects of the style:

```
static some_type function (param_type param, param_type param)
{
   int i;

   for (i = 0; i < 10; i++) {
       int j;

       j = i + 10;

       some_other_func (j, i);
   }
}
```

* Indent is 2 spaces.

* Pragmatism over perfection!

* Be careful not to pollute the namespace, do not pull in the full `std::` namespace, but rather
  just use the necessary bits, unless too cumbersome.

* Use copious whitespace.  In particular
   - there is a space between the function name and the open paren in a call.
   - likewise, there is a space following keywords such as if and while
   - every binary operator should have space on either side.

* No trailing whitespace. Please enable the standard pre-commit hook in git
  (or an equivalent hook). The standard pre-commit hook is enabled by simply
  renaming file '.git/hooks/pre-commit.sample' to '.git/hooks/pre-commit' .

* Opening braces "cuddle" (they are on the same line as the
  if/for/while test) and are preceded by a space. The opening brace of
  functions is the exception, and starts on a new line.

* Comments are always C-style /* */ block comments.  They should start
  with a capital letter and generally be written in complete
  sentences.  Internal functions are
  typically documented immediately before their definition.

* Code lines should be less than 80 columns and comments should be
  wrapped at 70 columns.

#### Naming

* Use lowercase_with_underscores for function, variable, and type
  names.

* All structs should be typedef'd to a name ending with _t.  If the
  struct has a tag, it should be the same as the typedef name, minus
  the trailing _t.

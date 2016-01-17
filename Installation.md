_astroid_ uses [scons](http://www.scons.org/) for building, also you might need [git](http://git-scm.com) for the build
process to work properly. Both should be available in most distributions.

A fairly recent version of [GTK+](http://www.gtk.org/) and [glib](https://developer.gnome.org/glib/) with their
[C++ bindings](http://www.gtkmm.org/en/) are also required, along with
[boost](http://www.boost.org/), [gmime](http://spruce.sourceforge.net/gmime/) and a compiler that supports [C++11](http://en.wikipedia.org/wiki/C%2B%2B11). And lastly, but importantly, the
[notmuch](http://notmuchmail.org/) libraries are also required.

### compiling

` $ scons `

to run the tests do:

` $ scons test `

### installing

Configure with a prefix and install:
```
$ scons --prefix=/usr build
$ scons --prefix=/usr install
```

this will install the `astroid` binary into `/usr/bin/` and data files into `/usr/share/astroid/`.


### Distribution specific information

* [[Arch Linux]]
* [[Ubuntu]]
* [[Debian]]

### Particular dependencies (incomplete list)
- GTK+ >= 3.10
The default configured editor is `gvim` embedded using [XEmbed](https://specifications.freedesktop.org/xembed-spec/xembed-spec-latest.html), but any editor or setup that support `XEmbed` can in principle be used.

The `editor.cmd` string is passed to `ustring::compose`, and the following arguments must be set:
> _filename_: `%1`  
> _servername_: `%2` (optional)  
> _socketid_: `%3`  

## Editor suggestions

### gvim (default)
```sh
gvim -geom 10x10 --servername %2 --socketid %3 -f -c 'set ft=mail' '+set fileencoding=utf-8' '+set ff=unix' '+set enc=utf-8' %1
```

fancy `gvim` with [Goyo](https://github.com/junegunn/goyo.vim) and [Limelight](https://github.com/junegunn/limelight.vim):
```sh
gvim -geom 10x10 --servername %2 --socketid %3 -f -c 'set ft=mail' '+set fileencoding=utf-8' '+set enc=utf-8' '+set ff=unix' -c Goyo -c Limelight! %1
```

### emacs
```sh
emacs --parent-id %3 %1
```

### neovim (through `st`)
```sh
st -f "Monospace" -w %3 -e nvim %1
``` 

the [st](http://st.suckless.org/) terminal is used since it supports `XEmbed`.

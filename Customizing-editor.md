The default configured editor is `gvim` embedded using [XEmbed](https://specifications.freedesktop.org/xembed-spec/xembed-spec-latest.html), but any editor or setup that support XEmbed can in principle be used.

The `editor.cmd` string is passed to `ustring::compose`, and the following arguments must be set:
> _filename_: `%1`  
> _servername_: `%2` (optional)  
> _socketid_: `%3`  

## Editor suggestions

### gvim (default)
> gvim -geom 10x10 --servername %2 --socketid %3 -f -c 'set ft=mail' '+set fileencoding=utf-8' '+set ff=unix' '+set enc=utf-8' %1

### emacs
> emacs --parent-id %3 %1

### neovim (through `st`)
> st -f "Monospace" -w %3 -e nvim %1

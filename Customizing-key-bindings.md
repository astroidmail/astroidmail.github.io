You can customise keybindings in the `~/.config/astroid/keybindings` file.

You can observe the name of bindings by looking at astroid's debug output when you press a key. For instance by default, by pressing the `L` key, you'll notice it's bound to `main_window.search_tag`. Redefining this binding to a new key (e.g. `/`) is possible with adding this in the keybindings file:

```
main_window.search_tag=/ 
```

See [here](https://github.com/aliceriot/dotfiles/blob/master/astroid/keybindings) for an example keybindings file that tries to emulate Sup and Vimium (c for compose, J/K for tab switching, etc).

> Empty lines and lines starting with `#` will be ignored.

### Unbound targets

There are also unbound targets (actions that do not have keybinding by default) that you can bind to keys, these are for instance:

```
# thread view
thread_view.forward_inline=f
thread_view.forward_attached=M-f

# thread index
thread_index.forward_inline=f
thread_index.forward_attached=M-f
```

this example will overwrite the default keybinding `f` which forwards a message `inlined` or `attached` depending on the configuration option `mail.forward.disposition`. In this particular example the configuration option no longer has any effect, and you choose whether to inline or attach a message depending on the keybinding.
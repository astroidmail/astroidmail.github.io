You can customise keybindings in the `~/.config/astroid/keybindings` file.

You can observe the name of bindings by looking at astroid's debug output when you press a key. For instance by default, by pressing the `L` key, you'll notice it's bound to `main_window.search_tag`. Redefining this binding to a new key (e.g. `/`) is possible with adding this in the keybindings file:

```
main_window.search_tag=/ 
```

See [here](https://github.com/aliceriot/dotfiles/blob/master/astroid/keybindings) for an example keybindings file that tries to emulate Sup and Vimium (c for compose, J/K for tab switching, etc).
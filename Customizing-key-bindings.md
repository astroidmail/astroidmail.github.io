Keybindings can be customised by the user in the `~/.config/astroid/keybindings` file.

You can observe the name of bindings by looking at astroid's debug output when you press a key. For instance by default the `L` key is bound to `main_window.search_tag`. Redefining this binding to a new key (e.g. `/`) is made by inserting this in the keybindings file:

```
main_window.search_tag=/ 
```
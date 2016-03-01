You can configure your own shell-scripts to be run on key-presses

> [Reference of available hooks available below](#reference-of-run-hooks-and-arguments)

The run-hooks are configured through the keybindings file, the most rudimentary example which allows you to safely get the hang of it is to add a line like:

~/.config/astroid/keybindings:
```
thread_index.run(echo %1)=w
```

if you press `w` in the Thread Index the command `echo %1` will be run with `%1` replaced with the `thread`-id from the _currently_ selected thread. 

> Tip: You can use `hooks::` as a shortcut for `/home/$USER/.config/astroid/hooks/`.

### Example: Toggle custom tag in Thread Index 

A more useful example is to set up keybindings to toggle custom tags, first create a script that can toggle its given tag. In this example the `queue` tag:

~/.config/astroid/hooks/toggle (you can place this anywhere):
```sh
#! /usr/bin/bash
#
# get a tag as first argument and thread id as second argument
#

# check if we have tag
if [[ $(notmuch search thread:$2 and tag:$1) ]]; then
  echo "removing tag: $1 from thread:$2"
  notmuch tag -$1 thread:$2
else
  echo "adding tag: $1 from thread:$2"
  notmuch tag +$1 thread:$2
fi
``` 

then create a keybinding in:
~/.config/astroid/keybindings:
```sh
# toggle queue
thread_index.run(hooks::toggle queue %1)=w

# toggle todo
thread_index.run(hooks::toggle todo %1)=M-t
```

you can add several lines for different tags. A successful exit status (0) will trigger a refresh of the thread in astroid ensuring it is updated in all thread indexes. The command is passed to: [`Glib::spawn_command_line_sync`](https://developer.gnome.org/glibmm/stable/group__Spawn.html#ga75961831b4dd3979bb8ab508ee3b3de7). The argument (`thread`-id) is substituted into the string with [`ustring::compose()`](https://developer.gnome.org/glibmm/stable/classGlib_1_1ustring.html#a18e1242bc0ad8a961a28fb2198392258). 

> Future run-hooks for other context may use more arguments, or substitute a list of `thread`-ids into the placeholder.

## Reference of run-hooks and arguments

#### Thread Index

> **thread_index.run (cmd %1)=keyspec**
>
> Arguments: one
> - **thread-id** - currently selected thread

> Hook return value:
> - **true** - an **emit_thread_updated** signal is emitted, causing the thread to be updated in all thread indexes.
> - **false** - no action



You specify the external application which is used to open attachments with the configuration option: `attachment.external_open_cmd`. Typical applications which detect the mime-type and figure out which application to open it with are `xdg-open` or `exo-open`. 

When the process exits, astroid deletes the attachment, so if you have problems with attachment disappearing before they are opened you can use a wrapper script as below which waits for the file to be closed and also checks for viruses using [`clamav`](http://www.clamav.net/).

Put in e.g.: `~/.bin/my-xdg-open.sh` and put the full path of the script into the config option: `attachment.external_open_cmd`.

```sh
#! /usr/bin/bash
#
# check for viruses and wait for file to be closed and for xdg-open to finish
#
# this script requires: libnotify, exo, clamav, inotify-tools

# test for viruses
if [[ ! clamscan "$1" ]]; then
  notify-send "Virus detected" "Virus found in attachment, not opening!" --icon=dialog-warning

  exit 1
fi

inotifywait -e close "$1" &
ip=$!

# open file (you can replace this with xdg-open)
exo-open "$1"

wait $ip # wait for file to be closed
```


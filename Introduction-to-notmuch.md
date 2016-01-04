Astroid uses [notmuch] to index, search and tag your emails. So if you do not already use notmuch, you need to set it up to use Astroid. For a complete setup of notmuch, please refer to its [website][notmuch].

[notmuch]: https://notmuchmail.org/

Here, we provide a quick introduction to what's needed for Astroid to work with [notmuch]. After you've installed notmuch, you need to configure it. A minimal configuration can be like this:

```
$ notmuch config set database.path /path/to/your/mail/ # The top-level directory where your mail is/will be stored
$ notmuch config set user.name "Jane Doe"
$ notmuch config set user.primary_email jane.doe@example.org
$ notmuch config set user.other_email jdoe@example.com
```

See [the documentation for notmuch-config for more details](https://notmuchmail.org/manpages/notmuch-config-1/).

What will be also very useful for you is to define [notmuch hooks](https://notmuchmail.org/manpages/notmuch-hooks-5/) to be automatically applied when notmuch will index your mail to find new mail and or to find changes in your mail database.

Also see <https://notmuchmail.org/initial_tagging/> for more complete approaches to apply automatic tags to your mail.

Astroid needs some information to start with. You can setup Astroid, provided you already have notmuch working (if not, see [our introduction to notmuch][notmuchintro].

The configuration for Astroid is found in the `~/.config/astroid/` directory. If does not exist yet, run Astroid for the first time and it will create it for you. The configuration file is in the JSON format.

# Where to find your mail database

You should probably look at the following properties specifically to see if they match your setup:

`"astroid.notmuch.db": "~/.mail"` should point out to the directory where your mail is. This is the same as the `database.path` for [notmuch][notmuchintro].

# What is your email account

Some self-explanatory variables that you probably want to configure are:

`"accounts.id.name": "Jane Doe"`
`"accounts.id.email": "jane.doe@example.org"`
`"accounts.id.gpgkey": "0x000000000"`
`"accounts.id.save_sent_to": "/home/jane/Mail/sent/cur/"`
`"accounts.id.save_drafts_to": "/home/jane/Mail/drafts/"`

# How to send email

At last, you need to define which program to call to send your email. For instance, if you use [msmtp](http://msmtp.sourceforge.net/): `"accounts.id.sendmail": "msmtp -t"` 

[notmuchintro]: ./Introduction-to-notmuch

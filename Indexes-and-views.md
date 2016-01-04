# Thread Index

The first view when you run Astroid is the first startup query (see `startup.queries` in your astroid config file). It shows an index of threads that match the notmuch search query (typically, `tag:inbox` will show the list of threads in the inbox).

You can scroll between threads with `j` and `k`, toggle tags on threads (for instance toggle a "spam" tag), mark as read/unread, etc. 

  <a href="https://raw.githubusercontent.com/gauteh/astroid/master/doc/astroid-full-window.png">
    <img src="https://raw.githubusercontent.com/gauteh/astroid/master/doc/astroid-full-window.png">
  </a>

From the thread index, you can also open a thread to view the emails in the thread, by hitting `Return`.

# Thread View

When you open a thread from the thread index, you get a thread view showing emails in the thread (usually getting you directly to the first unread email in the thread).

  <a href="https://raw.githubusercontent.com/gauteh/astroid/master/doc/astroid-thread-view.png">
    <img src="https://raw.githubusercontent.com/gauteh/astroid/master/doc/astroid-thread-view.png">
  </a>

For convenience, not all emails in the thread are entirely shown. You can scroll to preview emails and you can also open an email to view it entirely. (TODO: more explanation is needed here for the concept of focused email I guess).

As usual, press '?' to get a list of key bindings.
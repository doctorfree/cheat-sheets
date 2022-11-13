# NeoMutt

NeoMutt is a versatile and highly configurable command line mail reader based on Mutt. NeoMutt is a small but very powerful text-based MIME mail client. NeoMutt is highly configurable, and is well suited to the mail power user with advanced features like key bindings, keyboard macros, mail threading, regular expression searches and a powerful pattern matching language for selecting groups of messages.

The NeoMutt homepage can be found at [https://neomutt.org](https://neomutt.org).

## NeoMutt cheat sheet

- Mark as read: `Ctrl+R`
- Mark to delete: `d`
- Execute deletion: `$`
- Tag a mail: `t`
- Move a mail: `s` (for save, which is a copy + delete)
- Save a mail: `c` (for copy)
- Operation on tagged mails: `;[OP]` with OP being the key for that operation, like `;d` for deleting tagged emails or `;s` for moving them

### Operations on attachments

- Save to file: `s`
- Pipe to view as html: `|` and then `w3m -T text/html`
- Pipe to view as picture: `|` and then `feh -`

### Delete mails based on date

- use `T` to enter a date range, format `[before]-[after]` with before/after being a `DD/MM/YYYY` format (YYYY is optional)
- `~d 24/04-` to mark mails after 24/04 of this year
- `~d -24/04` to mark mails before 24/04 of this year
- `~d 24/04-25/04` to mark mails between 24/04 and 25/04 (inclusive)
- `;d` to tell neomutt we want to delete marked mails
- `$` to make deletion happen

### Simple config

Here is a simple example NeoMutt configuration:

```ini
set realname = "Jane Doe"
set from = "jane@doe.com"
set smtp_url = "smtps://login@doe.com:465"
alias me Jane Doe <login@doe.com>
set folder = "imaps://login@doe.com:993"
set imap_user = "login"
set header_cache     = /home/solene/.cache/neomutt/jane/headers
set message_cachedir = /home/solene/.cache/neomutt/jane/bodies
set imap_pass = "xx"
set smtp_pass = "xx"

set imap_idle = yes       # IMAP push (supposed to work)
set mbox_type = Maildir
set ssl_starttls = yes
set ssl_force_tls = yes

set spoolfile = "+INBOX"
set record = "+Sent"
set postponed = "+Drafts"
set trash = "+Trash"
set imap_list_subscribed = yes
set imap_check_subscribed

#sidebar
set sidebar_visible
set sidebar_format = "%B%?F? [%F]?%* %?N?%N/?%S"
set mail_check_stats
bind index,pager \Cp sidebar-prev         # Ctrl-Shift-p - Previous Mailbox
bind index,pager \Cn sidebar-next         # Ctrl-Shift-n - Next Mailbox
bind index,pager \Ca sidebar-open         # Ctrl-Shift-a - Open Highlighted Mailbox
bind index "," imap-fetch-mail            # ,            - Get new emails
bind index,pager "N" next-unread-mailbox  # Jump to next unread email

# regroup by threads
set sort=threads

# display only interesting headers
ignore *
unignore from date subject to cc
unignore organization organisation x-mailer: x-newsreader: x-mailing-list:
unignore posted-to:
```

## NeoMutt Key Bindings

Primary differences between the [Asciiville](../projects/Asciiville.md) NeoMutt key bindings and the default:

- Vim keybinds. `k` and `j` to go up and down, and `l` and `h` to move forwards and back pages
- Open the sidebar with `B`. `Ctrl+j` and `Ctrl+k` to navigate, `Ctrl+o` to open selection
- `A` will attempt to create a new contact with khard
- `F2`, `F3`, and `F4` are used to switch between three mailboxes

### Index

<table>
<thead>
<tr class="header">
<th>Function</th>
<th>Keybind</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Go to last entry</td>
<td><code>G</code></td>
</tr>
<tr class="even">
<td>Go to first entry</td>
<td><code>gg</code></td>
</tr>
<tr class="odd">
<td>Page down</td>
<td><code>d</code></td>
</tr>
<tr class="even">
<td>Page up</td>
<td><code>u</code></td>
</tr>
<tr class="odd">
<td>Delete message</td>
<td><code>D</code></td>
</tr>
<tr class="even">
<td>Delete thread</td>
<td><code>Ctrl+d</code></td>
</tr>
<tr class="odd">
<td>Mark thread read</td>
<td><code>Ctrl+r</code></td>
</tr>
<tr class="even">
<td>Undelete message</td>
<td><code>U</code></td>
</tr>
<tr class="odd">
<td>Limit/Filter</td>
<td><code>L</code></td>
</tr>
<tr class="even">
<td>Open message</td>
<td><code>l, Enter</code></td>
</tr>
<tr class="odd">
<td>Group reply</td>
<td><code>R</code></td>
</tr>
<tr class="even">
<td>Reply</td>
<td><code>r</code></td>
</tr>
<tr class="odd">
<td>Forward message</td>
<td><code>f</code></td>
</tr>
<tr class="even">
<td>New message</td>
<td><code>m</code></td>
</tr>
<tr class="odd">
<td>View attachments</td>
<td><code>v</code></td>
</tr>
<tr class="even">
<td>Compose to Sender</td>
<td><code>@</code></td>
</tr>
<tr class="odd">
<td>Resend message</td>
<td><code>Esc+e</code></td>
</tr>
<tr class="even">
<td>Save message (to file)</td>
<td><code>s</code></td>
</tr>
<tr class="odd">
<td>Toggle collapse thread</td>
<td><code>Space, Esc+v</code></td>
</tr>
<tr class="even">
<td>Toggle collapse all threads</td>
<td><code>Esc+V</code></td>
</tr>
<tr class="odd">
<td>Add contact to Khard</td>
<td><code>A</code></td>
</tr>
<tr class="even">
<td>Jump to parent message</td>
<td><code>P</code></td>
</tr>
<tr class="odd">
<td>Email PGP public key</td>
<td><code>Esc+k</code></td>
</tr>
</tbody>
</table>

### Pager

<table>
<thead>
<tr class="header">
<th>Function</th>
<th>Keybind</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Bottom of page</td>
<td><code>G</code></td>
</tr>
<tr class="even">
<td>Top of page</td>
<td><code>gg</code></td>
</tr>
<tr class="odd">
<td>Next line</td>
<td><code>j</code></td>
</tr>
<tr class="even">
<td>Previous line</td>
<td><code>k</code></td>
</tr>
<tr class="odd">
<td>View attachments</td>
<td><code>l</code></td>
</tr>
<tr class="even">
<td>Page down</td>
<td><code>d</code></td>
</tr>
<tr class="odd">
<td>Page up</td>
<td><code>u</code></td>
</tr>
<tr class="even">
<td>Group reply</td>
<td><code>R</code>,<code>g</code></td>
</tr>
<tr class="odd">
<td>Reply</td>
<td><code>r</code></td>
</tr>
<tr class="even">
<td>Compose to Sender</td>
<td><code>@</code></td>
</tr>
<tr class="odd">
<td>Delete thread</td>
<td><code>Ctrl+d</code></td>
</tr>
<tr class="even">
<td>Mark thread read</td>
<td><code>Ctrl+r</code></td>
</tr>
<tr class="odd">
<td>Mark thread new</td>
<td><code>N</code></td>
</tr>
</tbody>
</table>

### Sidebar

<table>
<thead>
<tr class="header">
<th>Function</th>
<th>Keybind</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Show sidebar</td>
<td><code>B</code></td>
</tr>
<tr class="even">
<td>Up</td>
<td><code>Ctrl+k</code></td>
</tr>
<tr class="odd">
<td>Down</td>
<td><code>Ctrl+j</code></td>
</tr>
<tr class="even">
<td>Open</td>
<td><code>Ctrl+o</code></td>
</tr>
<tr class="odd">
<td>Open next new</td>
<td><code>Ctrl+n</code></td>
</tr>
<tr class="even">
<td>Open previous new</td>
<td><code>Ctrl+p</code></td>
</tr>
</tbody>
</table>

## See also

- [Asciiville](../projects/Asciiville.md)
- [Tuir](tuir/tuir.md)
- [Irssi](irssi.md)
- [Mastodon](mastodon.md)
- [Newsboat](newsboat.md)

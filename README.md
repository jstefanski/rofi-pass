# rofi-pass

#### bash script to handle pass storages in a convenient way

![rofi-pass](screenshot.jpg "rofi-pass in action")

## Features:

* Open URLs of entries with hotkey
* Add new Entries to Password Storage
* Edit existing Entries
* Generate new passwords for entries
* Inline view, which can copy/type individual entries
* Move/Delete existing entries
* Support for multiple roots for password-store (e.g. separate work from private passwords)
* Type any field from entry
* Auto Type User and Password. Format of password files are expected to be like:
* Bookmarks mode (default: Alt+x)
```
foobarmysecurepassword
user: MyUser
url: http://my.url.foo
```
* Auto Typing of more than one field. This expects a autotype field in password file.
```
foobarmysecurepassword
---
user: MyUser
SomeField: foobar
AnotherField: barfoo
url: http://my.url.foo
autotype: SomeField :tab UserName :tab AnotherField :tab pass
```
The `:tab` field has a special meaning. this will hit the tab key, obviously.<br>
Same for `:space`, which will hit the space key, can be used to activate checkboxes.
In addition to those `:enter` and `:delay` are available.

* All Hotkeys are configurable in config file
* user, url and autotype field names are also configurable

## Requirements
* pass (http://www.passwordstore.org/)
* sed
* rofi (https://github.com/DaveDavenport/rofi)
* xdotool
* gawk
* bash

### BSD
* gnugrep
* gawk

## Configuration
rofi-pass may read its configuration values from `/etc/rofi-pass` and/or `$HOME/.config/rofi-pass/config`.
For an example configuration please take a look at the included `config.example` file.

## Extras
rofi-pass comes with an import script for keepass2 databases. It's the same script that can be downloaded from the pass homepage, with some minor modifications to match rofi-pass structure.

## FAQ

* rofi pass prints garbage instead of my actual passes
** Make sure to run `setxkbmap <language> <variant>` at the start of your Xorg session.

## Alternative

jreinert has written the roughly compatible tool [autopass](https://github.com/jreinert/autopass). It has less features, but definately saner code.
Also he provided a nice little script called `passed` to change your fieldnames. [link](https://github.com/jreinert/passed)

[![MELPA](http://melpa.org/packages/agtags-badge.svg)](http://melpa.org/#/agtags)

agtags
========

Another Emacs frontend to GNU Global.

Setup
-----

Put this file into load-path'ed directory, and byte compile it if desired. Put the following expression into your ~/.emacs.

``` el
(require 'agtags)
```

A simple setup demo

``` el
(when (executable-find "global")
  (agtags-bind-keys)
  (setq agtags-global-treat-text t)

  (add-hook 'text-mode-hook 'agtags-mode)
  (add-hook 'prog-mode-hook 'agtags-mode))
```

Variables
-------

**agtags-key-prefix** (Default "C-c t")

It is used for the prefix key of agtags's command.

**agtags-global-ignore-case** (Default nil)

Non-nil if Global should ignore case in the search pattern.

**agtags-global-treat-text** (Default nil)

Non-nil if Global should include matches from text files. This affects 'agtags-find-file' and 'agtags-find-grep'.

Functions
-------

**agtags-bind-keys**

Set global key bindings for agtags.

Bind Keys
-------

**("b" . agtags-update-tags)**

Create or Update tag files (e.g. GTAGS) in `Root Directory'.

**("f" . agtags-open-file)**

Input pattern and move to the top of the file.

**("F" . agtags-find-file)**

Input pattern, search file and move to the top of the file.

**("t" . agtags-find-tag)**

Input tag and move to the locations.

**("r" . agtags-find-rtag)**

Input rtags and move to the locations.

**("p" . agtags-find-with-string)**

Input string, search as substring and move to the locations.

**("g" . agtags-find-with-pattern)**

Input pattern, search with grep(1) and move to the locations.

**("q" . agtags-switch-dwim)**

Switch to last agtags-*-mode buffer.

License
-------

This program is free software; you can redistribute it and/or modify it under
the terms of the GNU General Public License as published by the Free Software
Foundation; either version 2 of the License, or (at your option) any later
version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE.  See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with
this program; if not, write to the Free Software Foundation, Inc., 51 Franklin
Street, Fifth Floor, Boston, MA 02110-1301, USA.

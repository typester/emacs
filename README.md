Emacs clone to support real fullscreen on OSX
=============================================

This is my personal emacs clone consists of several patches to improve emacs in OSX system.

Currently there's two patches in this repo:

1. fullscreen patch
2. shift modifier fix patch

I've been working these fixes to git branch -- feature/fullscreen and fix/shift_modifier_with_ime. But emacs official git repository is something weird, so my branches doen't merge into latest emacs mainline..

So I also created plain patch files for that. Please look at [download area](http://github.com/typester/emacs/downloads) to get these patches.


Fullscreen patch
----------------

This patch add `ns-toggle-fullscreen` function to toggle fullscreen mode.

TODO: this fullscreen mode doesn't use official `fullscreen_hook` feature, should fix this.


Shift modifier fix
------------------

Current version of Emacs 23.1 (or 23.2 pretest) throws KeyDown event directly to emacs if it was a function key or had modifiers, this break some Input Methods outside of Emacs (Kotoeri, ATOK, etc)

This patch blocks keydown when it comes with Shift modifier. 

XXX: this fixes are very ad-hoc, should consider clearner implementation.


# gnome-shortcuts



Gnome 3 uses DCONF to store the preferences in a single binary file: ~/.config/dconf/user.
As per the Gnome docs, it is recommended to save only the settings that you need and restore them with either dconf or gsettings. However, gsettings is only able to restore the value(s) for one single key at a time (plus, the value must be quoted) and that makes it a bit awkward for this kind of task. Which leaves us with dconf.
So, in this particular case, save the current settings for gnome-shell keyboard shortcuts:

```
dconf dump /org/gnome/shell/keybindings/ > bkp
```
Here's a bkp sample:

```
[/]
toggle-message-tray=['<Super>m']
open-application-menu=['<Super>F1']
toggle-application-view=['<Control>F1']
focus-active-notification=['<Super>n']
toggle-recording=['<Control><Shift><Alt>r']
Load the settings on another system:
```

```
dconf load /org/gnome/shell/keybindings/ < bkp
```










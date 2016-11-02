![alt tag](https://raw.githubusercontent.com/MatteoWickiBande/mwb-layout/master/keyboard-layout.png)
Preview of the mwb-layout (programmer dvorak variant). It was designed to be used on ISO keyboards (Mod3-key).

#Notable features
* Arrow keys on the left side of the home row
* Numpad on the right side
* Navigation keys like Home, End, PgUp and PgDn are easy to acces

#Installation in your $HOME:
```
mkdir -p ~/.xkb/symbols/
cp mwb ~/.xkb/symbols/
```
To enable it:
```
setxkbmap -I ~/.xkb mwb -print | xkbcomp -I$HOME/.xkb - $DISPLAY
```
#Systemwide install:
```
cp mwb /usr/share/X11/xkb/symbols/
```
To enable it:
```
setxkbmap mwb
```

#Install console keymap
Note, that the location of the console keymaps differ between distributions.
On Gentoo:
```
cp mwb.map.gz /usr/share/keymaps/i386/dvorak/
```
On Arch/Parabola:
```
cp mwb.map.gz /usr/share/kbd/keymaps/i386/dvorak/
```
To load the keymap temporarily in your tty:
```
loadkeys mwb
```
Permanently set using systemd-localed:
```
localectl set-keymap mwb
```
On other init systems it differs aswell.
On OpenRC you can edit the file /etc/conf.d/keymaps and set
```
keymap="mwb"
```
#Change the behaviour of CapsLock
The layout does not change the behaviour of the Capslock key. However, it is advised that the user does that, since this key is, compared to Esc and Ctrl, easy to access but usually not used as often.
One recommendation is to use xcape so CapsLock can be used as Esc and Ctrl simultaneously:
```
setxbmap -option 'caps:ctrl_modifier'
xcape -e '#66=Escape'
```
xcape can be found in many distributions repositories, or on github: https://github.com/alols/xcape

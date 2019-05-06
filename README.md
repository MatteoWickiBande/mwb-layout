![alt tag](https://raw.githubusercontent.com/MatteoWickiBande/mwb-layout/master/keyboard-layout.png)
Preview of the mwb-layout (programmer dvorak variant). It was designed to be used on ISO keyboards (Mod3-key).

## Notable features
* Arrow keys on the left side of the home row
* Numpad on the right side
* Navigation keys like Home, End, PgUp and PgDn are easy to acces

## Installing the X11 keymap
###  Installation in your $HOME:
```
mkdir -p ~/.xkb/symbols/
cp mwb ~/.xkb/symbols/
```
To enable it:
```
setxkbmap -I ~/.xkb mwb -print | xkbcomp -I$HOME/.xkb - $DISPLAY
```
### Systemwide install:
```
cp mwb /usr/share/X11/xkb/symbols/
```
To enable it:
```
setxkbmap mwb
```

## Installing the console keymap

Note, that the location of the console keymaps differs between distributions.

* On Gentoo:
```
cp mwb.map /usr/share/keymaps/i386/dvorak/
```
* On Arch/Parabola:
```
cp mwb.map /usr/share/kbd/keymaps/i386/dvorak/
```
### To load the keymap temporarily in your tty:
```
loadkeys mwb
```
### Permanently set using systemd-localed:
```
localectl set-keymap mwb
```
On other init systems it differs aswell.

On OpenRC you can edit the file /etc/conf.d/keymaps and set
```
keymap="mwb"
```
## Change the behaviour of CapsLock

The layout does not change the behaviour of the Capslock key. However, it is advised that the user does that, since this key is, compared to Esc and Ctrl, easy to access but usually not used as often.

One recommendation is to use xcape so CapsLock can be used as Esc and Ctrl simultaneously:
```
setxkbmap -option 'caps:ctrl_modifier'
xcape -e '#66=Escape'
```
xcape can be found in many distributions repositories, or on github: https://github.com/alols/xcape

## FAQ
### "Should I remap my VIM keybindings when using Dvorak?"
Recommendation: No.\
Vim keybindings are mostly chosen in a way that they are intuitive to remember (e.g. 'cw' for 'change word'), so it's sensible to remember the meaning of the actual letters, not just the keybindings. Muscle memory usually adapts quickly.\
As for the most important part, the hjkl-style navigation: Try it out. It still works perfectly fine on dvorak. j-k are comfortably reachable with the left index, and h-l is no problem either with the right hand. Horizontal and vertical movement are split between the two hands, which is an added bonus.\
Remember that this keyboard layout offers comfortably reachable arrow-keys too, although hjkl is still preferable in vim since a mod key isn't needed.

### "How do I switch from, say QWERTY? How long does it take get to get back to the same speed?"
The best way to switch to a new layout is to be consistent. Choose a date, and from there on, force yourself to exclusively use the new layout, no matter what you're doing. Everytime you go back to the old layout, even if it's just to quickly write an important e-mail, you tend to make a big step backwards. Avoid using the old layout until you're able to type in the new layout without concentrating, and without accidental flashbacks to the old layout. To get to that point takes - from personal experience - at least 1-2 weeks, so maybe don't decide to switch layouts right before you write a master thesis.\
Getting back to the old speed however can take months.\
Note however that the purpose of this layout is _not_ to improve typing speed, but to type more efficiently and put less strain on your fingers.\
Furthermore, make sure you use the right fingers for the according keys right from the start, and learn proper touch typing, which means typing without looking down at the keys. Using a keyboard labelled with QWERTY or any other layout can actually be helpful, because it encourages touch tying. Don't even think about labelling the keys or rearranging the keycaps, it will only make it harder in the long run.

### "Will I still be able to use my old layout after switching?"
Yes. It might take a minute to get used to it again, and you will most likely type at a decreased speed, but it's certainly possible to type in the old layout.\
As noted in the question above though, make sure you're already proficient before you go back to the old layout, in order not to hold back your progress.

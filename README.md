# ficode - Finnish xkb layout for coding

### Problem:
Coding on a Finnish keyboard is terrible. Writing Finnish with US-QWERTY or Colemak is terrible.

### Solution:
The Most important bit:
- Finnish base with 'ä' and 'ö' at their regular places
- [] and {} have their place from the US layout

That's 85% done.

The rest is a bonus, but offers some nice things
- US symbols row (except 2)
- Dash '-' and underscore '_' are on the same key from US layout.
- Shifted comma and dot are logically "Finnish" like god intended: ';' and ':'
- Forward slash '/' from the US layout, and logically Backward slash '\' on the same key when shifted.
- Single and double quotes are on the same key like in US, but moved one key to the right (so on the FIN single quote key).
- '!' and '?' are logically(?) side-by-side on shifted '1' and '2'

### The meh
- The bar '|', at '@', less than '<' and '>' are still quite lame, but at least they're are not worse than before, just what they used to be.
- 'å' & 'Å' are on AltGr layer, so not great for Swedish or Norwegian.

### Default layer
```
,---,---,---,---,---,---,---,---,---,---,---,---,---,-------,
| ` | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 0 | - | = | <-    |
|---'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-----|
| ->| | q | w | e | r | t | y | u | i | o | p | [ | ] |     |
|-----',--',--',--',--',--',--',--',--',--',--',--',--'|    |
| Esc  | a | s | d | f | g | h | j | k | l | ö | ä | ' |    |
|----,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'---'----|
|    | < | z | x | c | v | b | n | m | , | . | / |          |
|----'-,-',--'--,'---'---'---'---'---'---'-,-'---',--,------|
| ctrl |  | alt |                          |altgr |  | ctrl |
'------'  '-----'--------------------------'------'  '------'
```

### Shift layer
```
,---,---,---,---,---,---,---,---,---,---,---,---,---,-------,
| ~ | ! | ? | # | $ | % | ^ | & | * | ( | ) | _ | + | <-    |
|---'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-----|
| ->| | Q | W | E | R | T | Y | U | I | O | P | { | } |     |
|-----',--',--',--',--',--',--',--',--',--',--',--',--'|    |
| Esc  | A | S | D | F | G | H | J | K | L | Ö | Ä | " |    |
|----,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'---'----|
|    | > | Z | X | C | V | B | N | M | ; | : | \ |          |
|----'-,-',--'--,'---'---'---'---'---'---'-,-'---',--,------|
| ctrl |  | alt |                          |altgr |  | ctrl |
'------'  '-----'--------------------------'------'  '------'
```

### AltGr layer
```
,---,---,---,---,---,---,---,---,---,---,---,---,---,-------,
| ~ | " | @ | £ | ¤ | ‰ | ^ |   |   |   | ° | ˇ |   | <-    |
|---'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-----|
| ->| | q | w | € | r | þ | y | u | i | œ | p | [ | ' |     |
|-----',--',--',--',--',--',--',--',--',--',--',--',--'|    |
| Esc  | å | s | d | f | g | h | j | k | l | ö | æ | ` |    |
|----,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'---'----|
|    | | | ʒ | × | c | v | b | ŋ | µ | , | . | – |          |
|----'-,-',--'--,'---'---'---'---'---'---'-,-'---',--,------|
| ctrl |  | alt |                          |altgr |  | ctrl |
'------'  '-----'--------------------------'------'  '------'
```

## :warning:
- This hacky xkb setup has been surpassed by one enabled by [keyd](https://github.com/rvaiya/keyd) keyboard daemon.
- If at any time xkb gets updated, all these changes to the system files will be overwritten.
- keyd offers an easier way to work with multiple layers.
- There are keyd config files and setup instructions in the [dotfiles](https://github.com/krumeluu/dotfiles/tree/main/.config/keyd) repo.

## Quickstart

- Clone repo
```
git clone https://github.com/krumeluu/ficode && cd ficode
```
- Stick the contents of `ficode` file to the end of `/usr/share/X11/xkb/symbols/fi` manually or by running
```
sudo su -c 'cat ficode >> /usr/share/X11/xkb/symbols/fi'
```
- Manually insert the following after the Finnish variants in `/usr/share/X11/xkb/rules/base.extras.xml` and `/usr/share/X11/xkb/rules/evdev.extras.xml`

```
        <variant>
          <configItem popularity="exotic">
            <name>ficode</name>
            <description>Finnish (Code)</description>
          </configItem>
        </variant>
```

- Load keymap
```
setxkbmap -config xkb.conf
```


# ficode

## Why

### The Finnish QWERTY keyboard layout is horrible

It's even horribler for writing code. Many of the most common symbols are on
the AltGr layer behind some carpal tunnel acrobatics. The US QWERTY layout
lacks `Å`, `Ä` and `Ö`.

- On the Finnish layout the brackets are a bane in the ärse. Repeatedly
pressing `AltGr` with our thumb while reaching for `7890` with the same hand to
get `{[]}` is beyond uncomfortable. It's difficult to come up with a worse
configuration.
- `\` is as bad, sitting next to `0` on the `AltGr` layer
- `$` is also on `AltGr`, under `4`. Instead on the Shift layer is this: `¤`.
Well, it's a currency symbol, but when has anyone ever used this? (What do I
know, maybe your job is [writing tables in Microsoft
Word](https://en.wikipedia.org/wiki/Currency_sign_(generic)#Other_uses))??
- Using `Shift` and reaching up to `7` for `/` multiple times per filepath
written is tedious.
- The backtick `\` is a dead key: you have to press `Shift` and `=` (next to
BackSpace) and finally `Space` to produce it. You use backticks all the time
with Markdown and quoting string literals (in Go) etc. Instead its keyboard
real estate is occupied by symbols `§` and `½`. I think I once used `§` in 2019.
- Tilde `~` also dead.
- WHO NEEDS CAPSLOCK!?

## What

### Combine The Finnish and the US layouts into a better version

- `[]{}` use the US layout positions.
- The symbol row is the same as US's excluding `@`. The `?` is moved there
instead. (Next to `!`, resembling `2`?).
- Shifted `,` and `.` are Finnish: `;` and `:`. Next to them forward slash `/`,
which becomes backward slash `\` when shifted. Nice.
- Ääkköset in their regular Finnish position, but `Å` & `å` moved to AltGr
layer under `o`.
- Between `Ä` and `Return` there's the single quote `'`. Becomes `"` when
shifted, naturally.
- `<`, `>`, and `|` are between `z` and `Shift` keys. (On ISO keyboards: [ANSI
vs. ISO](https://deskthority.net/wiki/ANSI_vs_ISO))
- `CapsLock` is now `Esc`. Use it to exit Insert mode in Vim (First step of
exiting Vim).

### Default layer

```ascii-art
,---,---,---,---,---,---,---,---,---,---,---,---,---,-------,
| ` | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 0 | - | = | <-    |
|---'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-----|
| ->| | q | w | e | r | t | y | u | i | o | p | [ | ] |     |
|-----',--',--',--',--',--',--',--',--',--',--',--',--'|    |
| Esc  | a | s | d | f | g | h | j | k | l | ö | ä | ' |    |
|----,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'---'----|
| LS | < | z | x | c | v | b | n | m | , | . | / |  Shift   |
|----'-,-',--'--,'---'---'---'---'---'---',--'---',--,------|
| Ctrl |  | Alt |                         | AltGr |  | Ctrl |
'------'  '-----'-------------------------'-------'  '------'
```

### Shift layer

```ascii-art
,---,---,---,---,---,---,---,---,---,---,---,---,---,-------,
| ~ | ! | ? | # | $ | % | ^ | & | * | ( | ) | _ | + | <-    |
|---'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-----|
| ->| | Q | W | E | R | T | Y | U | I | O | P | { | } |     |
|-----',--',--',--',--',--',--',--',--',--',--',--',--'|    |
| Esc  | A | S | D | F | G | H | J | K | L | Ö | Ä | " |    |
|----,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'---'----|
| LS | > | Z | X | C | V | B | N | M | ; | : | \ |  Shift   |
|----'-,-',--'--,'---'---'---'---'---'---',--'---',--,------|
| Ctrl |  | Alt |                         | AltGr |  | Ctrl |
'------'  '-----'-------------------------'-------'  '------'
```

### AltGr layer

```ascii-art
,---,---,---,---,---,---,---,---,---,---,---,---,---,-------,
| ~ | ¡ | @ | £ | ¤ | ‰ | ^ |   | ∞ |   | ° | ˇ | ≠ | <-    |
|---'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-----|
| ->| | q | w | € | r | þ | y | u | i | å | p | [ | ' |     |
|-----',--',--',--',--',--',--',--',--',--',--',--',--'|    |
| Esc  | α | s | d | f | g | h | j | k | l | œ | æ | ` |    |
|----,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'-,-'---'----|
| LS | | | ʒ | × | c | v | b | ŋ | µ | , | . | – |  Shift   |
|----'-,-',--'--,'---'---'---'---'---'---',--'---',--,------|
| Ctrl |  | Alt |                         | AltGr |  | Ctrl |
'------'  '-----'-------------------------'-------'  '------'
```

### Pinky variant

- `Ä` and `Ö` swapped: `Ä` is much more common than `Ö`

### Symbol variant

- Numbers are demoted to Shift layer

## Quickstart

- Clone repo

```sh
git clone https://github.com/quunnb/ficode && cd ficode
```

- Copy files

```sh
# cp ficode /usr/share/X11/xkb/symbols/
```

- Load keymap

```sh
setxkbmap -config ficode.conf
```

### TODO

- Consider adding more stuff to the AltGr layer

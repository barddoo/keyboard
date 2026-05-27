# Sofle Keyboard Setup

Personal [Sofle v2](https://josefadamcik.github.io/SofleKeyboard/) split keyboard configuration managed via [Vial](https://get.vial.today/). Optimized for Vim/Neovim usage.

## File

- `sofle.vil` — Vial keymap backup. Load via **File → Load Saved Layout** in [vial.rocks](https://vial.rocks) or the Vial GUI app.

## Layout Overview

58-key split ortholinear, 3 active layers + home row mods.

### Layer 0 — Base (QWERTY)

```
ESC  1    2    3    4    5   [↑]        [←]  6    7    8    9    0   BSPC
TAB  Q    W    E    R    T   [↓]        [→]  Y    U    I    O    P    \
CAPS ⌘A   ⌥S   ⌃D   ⇧F   G                  H    ⇧J   ⌃K   ⌥L   ⌘;   '
SFT  Z    X    C    V    B   [-]       [F5]  N    M    ,    .    /   DEL
          CTRL ESC  SPC MO1  ALT        ALT MO2 ENT  BSPC CTRL
```

Home row mods (GACS/SCAG): hold for modifier, tap for letter.

Left encoder: scroll up/down. Right encoder: scroll left/right.

### Layer 1 — Symbols (hold left MO1)

```
`    F1   F2   F3   F4   F5             F6   F7   F8   F9   F10 BSPC
TAB  +    =    -    _    --             {    }    |    [    ]   ENT
CAPS ~    !    @    #    $              %    ^    &    *    (   )
SFT  F11  F12  --   --   --             --   --   ,    .    /   DEL
          CTRL ⌘   SPC MO1  ALT       CTRL RALT SPC  RSF CTRL
```

### Layer 2 — Navigation (hold right MO2)

```
     ...  ...  ...  ...  ...            ...  ...  ...  ...  ...  ...
TAB  --   --   --   --   --            HOME PGDN PGUP END  --
CAPS ⌘Z   ⌘X   ⌘C   ⌘V   --             ←    ↓    ↑    →   --
SFT  --   --   --   --   --            ⌘[   ⌘]   --   --   --  DEL
```

## Notable Features

| Feature | Detail |
|---------|--------|
| Home row mods | LGUI/LALT/LCTL/LSFT on A/S/D/F; mirrored on right |
| Combo | J+K → Escape (vim normal mode) |
| Layer 1 | Symbols, F-keys, parens/brackets via shift combos |
| Layer 2 | Navigation (HJKL-aligned arrows), clipboard shortcuts (⌘Z/X/C/V), browser history (⌘[/⌘]) |
| Encoders | Left: up/down arrows; Right: left/right arrows |

## Settings

Key Vial QMK settings from backup:

| Setting | Value |
|---------|-------|
| Tapping term | 175 ms |
| Permissive hold | off |
| One-shot timeout | 5000 ms |
| Debounce | 5 ms |

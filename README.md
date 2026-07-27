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
CTL⎋ ⌘A   ⌥S   ⌃D   ⇧F   G                  H    ⇧J   ⌃K   ⌥L   ⌘;   '
SFT  Z    X    C    V    B   [-]       [F5]  N    M    ,    .    /   DEL
          CTRL ⌘    HYP MO1  SPC        ENT MO2 MO3  BSPC CTRL
```

Home row mods (GACS/SCAG): hold for modifier, tap for letter.

Left encoder: up/down arrows. Right encoder: left/right arrows. Note: `encoder_layout` in the backup is empty — rotation is driven by spare matrix positions (shown as `[↑]/[↓]/[←]/[→]` above), so encoder behaviour lives in the firmware, not this file.

### Layer 1 — Symbols (hold left MO1)

```
`    F1   F2   F3   F4   F5             F6   F7   F8   F9   F10 BSPC
TAB  +    =    -    _    --             {    }    |    [    ]   ENT
CTL⎋ ~    !    @    #    $              %    ^    &    *    (   )
SFT  F11  F12  --   --   --             --   --   <    >    ?   DEL
          CTRL ⌘   SPC MO1  ALT       CTRL RALT SPC  RSF CTRL
```

### Layer 2 — Navigation (hold right MO2)

```
     ...  ...  ...  ...  ...            ...  ...  ...  ...  ...  ...
TAB  --   --   --   --   --            HOME PGDN PGUP END  --
CTL⎋ ⌘Z   ⌘X   ⌘C   ⌘V   --             ←    ↓    ↑    →   --
SFT  --   --   --   --   --            ⌘[   ⌘]   --   --   --  DEL
```

Nav keys sit one column left of the vim letters: `Y/U/I/O` = Home/PgDn/PgUp/End, arrows on `H/J/K/L`.

### Layer 3 — Mouse & Media (hold right outer thumb MO3)

```
     ...  ...  ...  ...  ...            ...  ...  ...  ...  ...  ...
TAB  ⏮   ⏯    ⏭   BRI- BRI+            WH←  WH↓  WH↑  WH→  --
CTL⎋ MUTE VOL- VOL+ --   --             ←    ↓    ↑    →   --
SFT  --   --   --   --   --             BTN1 BTN2 BTN3 SLOW FAST  DEL
```

Cursor on `H/J/K/L` (same vim alignment as layer 2), wheel on the row above, buttons on the row below. Left hand is media/brightness/volume.

## Notable Features

| Feature | Detail |
|---------|--------|
| Home row mods | LGUI/LALT/LCTL/LSFT on A/S/D/F; mirrored on right |
| Caps Lock | `LCTL_T(KC_ESCAPE)` — tap=Esc, hold=Ctrl |
| Thumb homes | Inner (rotated) thumb keys hold `SPACE` (left) and `ENTER` (right) |
| Hyper | `HYPR(KC_NO)` — Ctrl+Shift+Alt+Cmd, hold-only. Third left slot. Bound to Raycast window management + app launchers (see `guide.md`) |
| Left thumb row | `KC_LGUI` — only dedicated ⌘ on the board |
| Combo | J+K → Escape (vim normal mode) |
| Layer 1 | Symbols, F-keys, parens/brackets via shift combos |
| Layer 2 | Navigation (HJKL-aligned arrows), clipboard shortcuts (⌘Z/X/C/V), browser history (⌘[/⌘]) |
| Layer 3 | Mouse cursor/wheel/buttons (HJKL-aligned), media, brightness, volume |
| Encoders | Left: up/down arrows; Right: left/right arrows |

## Settings

Key Vial QMK settings from backup:

| Setting | Value |
|---------|-------|
| Tapping term | 175 ms |
| Permissive hold | on |
| One-shot timeout | 5000 ms |
| Debounce | 5 ms |

The backup stores these as opaque numeric ids (`"4":175, "7":200, …`), so the table above can't be verified from the file alone — confirm in **Vial → QMK Settings** before trusting it. Chordal Hold (see `guide.md`) is a firmware compile option, not settable here.

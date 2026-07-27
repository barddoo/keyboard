# Keyboard Tricks & Concepts

## Home Row Mods

Keys on the home row double as modifiers when held.

| Key | Tap | Hold |
|-----|-----|------|
| A | a | ⌘ (Cmd) |
| S | s | ⌥ (Alt) |
| D | d | ⌃ (Ctrl) |
| F | f | ⇧ (Shift) |
| J | j | ⇧ (Shift) |
| K | k | ⌃ (Ctrl) |
| L | l | ⌥ (Alt) |
| ; | ; | ⌘ (Cmd) |

Order is GACS on left, SCAG on right — mirrored so same-hand combos feel natural.

**Common usage:**
- Hold `F` + tap `H/J/K/L` → Shift + arrow (select text)
- Hold `D` + tap anything → Ctrl+key (terminal shortcuts)
- Hold `A` + tap `Z/X/C/V` → ⌘Z/X/C/V (undo/cut/copy/paste)

---

## Caps Lock → LCTL_T(KC_ESCAPE)

Caps Lock is now a dual-function key:
- **Tap** → Escape (exit Vim modes, dismiss prompts)
- **Hold** → Ctrl (terminal, tmux, editor shortcuts)

Removes the need to reach for the corner Escape key or use the J+K combo for most Vim escapes.

---

## Hyper Key (third left thumb slot)

`HYPR(KC_NO)` = Ctrl + Shift + Alt + Cmd simultaneously. No app uses all 4 modifiers, so it never conflicts. Hold-only — tapping it emits nothing.

It sits in the third slot rather than the inner thumb — hold keys don't need the best position, `SPACE` does.

### Bound shortcuts (Raycast)

| Chord | Action |
|-------|--------|
| Hyper + H | Window: Left Half |
| Hyper + Y | Window: Right Half |
| Hyper + U | Window: Maximize |
| Hyper + I | Window: Center |
| Hyper + T | Terminal |
| Hyper + B | Browser |
| Hyper + G | Slack |
| Hyper + N | *free* — reserved for Notion |

Raycast itself opens on **⌘Space** (its global hotkey, unchanged). On this board that's hold `A` for ⌘ + tap `SPACE` with the left thumb — same hand, no stretch. Hyper+Space is *not* an option: hyper and space are both left-thumb keys with `MO(1)` between them, so one thumb can't hit both.

Set in Raycast → Settings → Extensions → click the Hotkey field, press the chord. Raycast stores these in an encrypted SQLite store with no CLI, so they can't be scripted or backed up alongside `sofle.vil` — if you reinstall Raycast, re-enter them from this table.

Space switching is **not** Raycast: System Settings → Keyboard → Shortcuts → Mission Control.

### Avoid home row mods in hyper chords

Every bound letter above is a plain keycode. Deliberate: `A S D F J K L ;` are mod-taps, so holding one past the 175 ms tapping term while hyper is down sends Shift/Ctrl/Alt instead of the letter and the shortcut silently doesn't fire.

This is why window management is on `H/Y/U/I` instead of the vim-natural `H/J/K/L` — `H` is plain, but `J/K/L` are all mod-taps. Safe letters: `Q W E R T Y U I O P G H Z X C V B N M`.

---

## Layers

Hold a thumb key to activate a layer. Release to go back to base.

### MO(1) — Symbols (left thumb)

Access symbols without shifting. Row 2 becomes:
```
~ ! @ # $ % ^ & * ( )
```
Row 1 becomes brackets/braces:
```
+ = - _    {  }  |  [  ]
```
F-keys on top row (F1–F10), F11/F12 on bottom row. Bottom-row right gives `< > ?` (the shifted forms, since base already has `, . /`).

### MO(2) — Navigation (right thumb)

Right hand becomes arrow cluster, aligned to HJKL:
```
H → ←    J → ↓    K → ↑    L → →
```
Left hand gets clipboard shortcuts:
```
A → ⌘Z   S → ⌘X   D → ⌘C   F → ⌘V
```
Right hand also gets (one column left of the arrows — starts on `Y`, not `U`):
```
Y → Home   U → PgDn   I → PgUp   O → End
⌘[ / ⌘]   → browser back/forward
```

### MO(3) — Mouse & Media (right outer thumb)

Same hand-shape as MO(2), so muscle memory carries over:
```
H → ←    J → ↓    K → ↑    L → →      (cursor)
Y → wheel←  U → wheel↓  I → wheel↑  O → wheel→
N → left click   M → right click   , → middle click
. → slow cursor  / → fast cursor
```
Left hand:
```
Q → ⏮   W → ⏯   E → ⏭   R → brightness−   T → brightness+
A → mute   S → volume−   D → volume+
```

Cursor movement is deliberate, not a mouse replacement — good for dismissing a dialog or nudging a slider without leaving the keyboard.

---

## Dedicated ⌘ (left thumb row)

Home row mods put ⌘ on `A` and `;`, but same-hand chords like ⌘A or ⌘Q are awkward there. The left inner thumb is now plain `KC_LGUI`, so any ⌘ chord works thumb + finger.

It used to be a third Escape (Caps Lock and the J+K combo already cover that).

---

## Combos

Press two keys simultaneously to produce a different output.

| Combo | Output | Use |
|-------|--------|-----|
| J + K | Escape | Vim normal mode (hands stay on home row) |

---

## Permissive Hold

Controls how mod-tap keys behave when you type fast.

**Off (old behavior):** hold `F` + tap `J` within tapping term = types `fj`
**On (current):** hold `F` + tap `J` = `Shift+J`, regardless of timing

Makes deliberate modifier chords more reliable. Can cause accidental mods if you roll keys fast — if this happens, lower the tapping term or enable Chordal Hold.

---

## Chordal Hold

Enhancement to Permissive Hold for split keyboards.

Detects whether the second key is on the **same hand** or **opposite hand**:
- Same hand → treats as tap (you're probably rolling keys while typing)
- Opposite hand → treats as hold (you're probably doing a modifier chord)

Eliminates most accidental mod triggers while keeping chords snappy. Requires Vial firmware 0.7.4+.

**Not enabled yet.** `CHORDAL_HOLD` is a firmware compile flag (`config.h` / `rules.mk`), not a Vial QMK Setting — enabling it means rebuilding and flashing, not editing `sofle.vil`. Highest-value remaining upgrade for this layout.

---

## Tapping Term

How long you must hold a key before it registers as a hold (175ms).

- Too high → mods feel sluggish, accidental taps
- Too low → accidental mods while typing fast
- 160–200ms is the sweet spot for most people

Adjust in Vial → QMK Settings.

---

## Encoders

Rotary knobs on each half.

| Encoder | Action |
|---------|--------|
| Left (rotate) | Up / Down arrows |
| Right (rotate) | Left / Right arrows |

Useful for scrolling in terminal/browser without leaving home row.

Rotation is wired to spare matrix positions in the firmware, not to `encoder_layout` in the backup (that block is empty) — loading `sofle.vil` onto different firmware won't carry the encoders over.

---

## Tips for Vim/Neovim

- **Escape**: tap Caps Lock (faster than J+K combo, no latency)
- **J+K combo**: still works as backup / muscle memory fallback
- **Normal mode navigation**: use Layer 2 (MO2) arrows aligned to HJKL for non-Vim contexts
- **Ctrl chords**: hold Caps Lock for Ctrl — great for `Ctrl+C`, `Ctrl+D`, `Ctrl+Z` in terminal
- **Window management**: Hyper + `H/Y/U/I` for halves/maximize/center, Hyper + `T/B/G` to jump to terminal/browser/Slack — no mouse

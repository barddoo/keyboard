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

## Caps Lock → LCTL_T(KC_ESC)

Caps Lock is now a dual-function key:
- **Tap** → Escape (exit Vim modes, dismiss prompts)
- **Hold** → Ctrl (terminal, tmux, editor shortcuts)

Removes the need to reach for the corner Escape key or use the J+K combo for most Vim escapes.

---

## Hyper Key (left outer thumb)

`Hyper` = Ctrl + Shift + Alt + Cmd simultaneously. No app uses all 4 modifiers, so it never conflicts.

Use it as a namespace for personal shortcuts via Raycast or Hammerspoon:

```
Hyper + H/J/K/L  → window/pane navigation
Hyper + T        → new terminal
Hyper + B        → browser
Hyper + S        → Slack
Hyper + 1-9      → switch spaces/desktops
```

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
F-keys on top row (F1–F10), F11/F12 on bottom row.

### MO(2) — Navigation (right thumb)

Right hand becomes arrow cluster, aligned to HJKL:
```
H → ←    J → ↓    K → ↑    L → →
```
Left hand gets clipboard shortcuts:
```
A → ⌘Z   S → ⌘X   D → ⌘C   F → ⌘V
```
Right hand also gets:
```
U → Home   I → PgDn   O → PgUp   P → End
⌘[ / ⌘]   → browser back/forward
```

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

---

## Tips for Vim/Neovim

- **Escape**: tap Caps Lock (faster than J+K combo, no latency)
- **J+K combo**: still works as backup / muscle memory fallback
- **Normal mode navigation**: use Layer 2 (MO2) arrows aligned to HJKL for non-Vim contexts
- **Ctrl chords**: hold Caps Lock for Ctrl — great for `Ctrl+C`, `Ctrl+D`, `Ctrl+Z` in terminal
- **Window management**: assign Hyper shortcuts in Raycast/Hammerspoon to switch between terminal, browser, Slack without touching the mouse

# pcw.py – Minimal Panel-based Curses Window Manager

A lightweight, safe, panel-based UI framework using `curses` and `curses.panel`.  
All windows are backed by panels (proper z-order), every widget paints every frame with full clipping, and colors are initialized lazily (safe to import without starting curses).

## Color/Attribute Helper

### `cm(fg: str = "default", bg: str = "default", att: str = "default") -> int`

Returns a curses attribute combining foreground, background, and text attributes.  
Colors and attributes are lazily initialized the first time they are used.

**Supported color names** (case-sensitive):  
`black`, `red`, `green`, `yellow`, `blue`, `magenta`, `cyan`, `white`,  
`bright_black`, `bright_red`, … `bright_white`, `default`, `gray`, `grey`

**Supported attribute names**:  
`bold`, `underline`, `reverse`, `blink`, `dim`, `standout`, `normal`, `default`

Example:
```python
win.addstr(y, x, "Hello", cm("bright_yellow", "red", "bold"))

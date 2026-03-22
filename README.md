# KUI – VT100 Terminal UI Library (C)

KUI (Kanishk UI) is a lightweight C library for building terminal-based user interfaces using VT100 escape sequences.

It provides simple APIs for cursor control, text rendering, and drawing UI elements like lines and boxes.

---

## Features

- Cursor positioning (absolute control)
- Screen clearing
- Text rendering at specific positions
- Single-line and double-line box drawing
- Minimal dependency (pure C)
- VT100 compatible

---

## Project Structure

```
kui/
├── include/
│   └── kui_vt100.h
├── src/
│   └── kui_vt100.c
├── examples/
│   └── demo.c
├── docs/
└── README.md
```

---

## Getting Started

### Clone

```
git clone `https://github.com/your-username/kui.git` [(github.com in Bing)](https://www.bing.com/search?q="https%3A%2F%2Fgithub.com%2Fyour-username%2Fkui.git")
cd kui
```

### Compile

```
gcc examples/demo.c src/kui_vt100.c -Iinclude -o demo
```

### Run

```
./demo
```

---

## Basic Usage

```c
#include "kui_vt100.h"

int main()
{
    kui_clear();

    kui_say(2, 10, "KUI Terminal UI");

    kui_draw_box(4, 5, 10, 40);

    kui_draw_horizontal_line(6, 6, 39);
    kui_draw_vertical_line(20, 5, 9);

    kui_go_to_xy(12, 1);

    return 0;
}
```

---

## API Overview

### Screen Control

* `kui_clear()`  
  Clears the screen and resets cursor position

* `kui_go_to_xy(row, column)`  
  Moves cursor to given position (1-based)

---

### Text Rendering

* `kui_say(row, column, str)`  
  Prints a string at specified position

---

### Drawing Primitives

#### Single Line

* `kui_draw_horizontal_line(row, c1, c2)`
* `kui_draw_vertical_line(column, r1, r2)`
* `kui_draw_box(r1, c1, r2, c2)`

#### Double Line

* `kui_draw_double_horizontal_line(row, c1, c2)`
* `kui_draw_double_vertical_line(column, r1, r2)`
* `kui_draw_double_line_box(r1, c1, r2, c2)`

---

## How It Works

KUI uses VT100 escape sequences:

```
\033[2J       -> Clear screen
\033[row;colH -> Move cursor
```

All APIs are built on top of these sequences.

---

## Terminal Compatibility

* Linux terminals (bash, zsh)
* macOS Terminal / iTerm
* Windows (ANSI enabled)

---

## Limitations

* Uses 1-based indexing
* No bounds checking
* Output-only (no input handling)
* Requires VT100-compatible terminal

---

## Future Improvements

* Color support
* Input handling
* Menu system
* Unicode box drawing
* Window abstraction

---

## Example Output

```
+----------------------------------+
|          KUI Terminal UI         |
|----------------------------------|
|                                  |
|                                  |
+----------------------------------+
```

---

## Documentation

Doxygen comments are included.

Generate docs using:

```
doxygen Doxyfile
```

---

## Author

Kanishk Chouhan

---


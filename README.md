# terminaltools
**⌨ Some personal tools for working with the terminal in Python.**

This package contains some useful functions I created for my personal use in Python terminal projects, including styling and querying the user.

⚠ Please note that this package is almost certainly laced with bugs, so use it at your own risk! If you encounter any issues, please create an issue on GitHub (*https://github.com/ericli3690/terminaltools*) or email me at *ericli3690@gmail.com*.

## 🛠 Installation and Use

`>> pip install terminaltools`

```python
from terminaltools import function_name_here
function_name_here(arguments_here)
```

## 🎨 Color Functions

### Available Colors
`BLACK, RED, GREEN, YELLOW, BLUE, PURPLE, CYAN, WHITE`

### marker(color)
Returns the escape sequence for a given color.

### colored(text, color)
Returns the text parameter as a given color.

### color_print(text, color, is_input, insert_end)
Prints the text parameter as a given color.

insert_end is used for the 'end' parameter in print statements; is_input will allow an input to be created instead.

## 🖨 Other Printing Functions

### delay(interval)
Repeatedly refreshes the line, inputting a new dot every second until the amount of dots equals parameter INTERVAL (in seconds).

### nest(text, top_icon, side_icon, corner_icon, left_right_padding, up_down_padding)
DEFAULTS TO: `None, '=', '', '', 0, 0`

Nests 'text' in a box with 'top_icon' on the top and bottom, 'side_icon' on the left and right, and 'corner_icon' on the corners; can also add interior padding via left_right_padding and up_down_padding.

Returns a string.

Try nesting nests in nests!

## ❓ Querying the User

### ask(prompt, filter, disallow_null, clear_console, colors)
define a filter, then call ask:

```python
def myFilter(reply):
  if (reply == "0"):
    return False, 'This value is not allowed.'
  else:
    return True, 'Value accepted.'
ask("Enter a non-zero character.", myFilter)
```

Warning: this uses eval().

Your filter may be named anything, but its argument MUST be called "reply"

disallow_null is true by default; clear_console on user success and failure are both false by default; success color and failure color are green and red respectively by default.

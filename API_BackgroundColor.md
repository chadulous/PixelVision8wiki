# BackgroundColor

The background color is used to fill the screen when clearing the display. You can use this method to read or update the background color at any point during the `GameChip`'s draw phase. When calling `BackgroundColor()`, without an argument, it returns the current background color as an int. You can pass in an optional int to update the background color by calling `BackgroundColor(0)` where `0` is any valid ID in the `ColorChip`. Passing in a value such as `-1`, or one that is out of range, defaults the background color to magenta (`#ff00ff`) which is the engine's default transparent color.

## Usage

`BackgroundColor ( id )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td>This argument is optional. Supply an int to update the existing background color value.</td>
  </tr>
</table>


## Returns

<table>
  <tr>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>int</td>
    <td>This method returns the current background color ID. If no color exists, it returns -1 which is magenta (#FF00FF).</td>
  </tr>
</table>


## Example

Calling this without an argiment will simply return the current background color:

`local bgID = BackgroundColor()`

`print("bg color", bgID)`

This will output the default background color which is set to 0.

You can change the background color before calling clear to change the background color of the display.

`function Init()`

`BackgroundColor(1)`

`end`

`function Draw()`

`Clear()`

`en`d

This will change the background color to #XXXXXX and calling Clear() will repaint the display with the new background color on each frame.

[PIC]


# Clear

Clearing the display removed all of the existing pixel data, replacing it with the default background color. The `Clear()` method allows you to specify what region of the display to clear. By simply calling` Clear()`, with no arguments, it automatically clears the entire display. You can manually define an area of the screen to clear by supplying option `x`, `y`, `width` and `height` arguments. When clearing a specific area of the display, anything outside of the defined boundaries remains on the next draw phase. This is useful for drawing a HUD but clearing the display below for a scrolling map and sprites. Clear can only be used once during the draw phase.

## Usage

`Clear ( x, y, width, height )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>This is an optional value that defaults to 0 and defines where the clear's X position should begin. When X is 0, clear starts on the far left-hand side of the display. Values less than 0 or greater than the width of the display are ignored.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>This is an optional value that defaults to 0 and defines where the clear's Y position should begin. When Y is 0, clear starts at the top of the display. Values less than 0 or greater than the height of the display are ignored.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int</td>
    <td>This is an optional value that defaults to the width of the display and defines how many horizontal pixels to clear. When the width is 0, clear starts at the x position and ends at the far right-hand side of the display. Values less than 0 or greater than the width are adjusted to stay within the boundaries of the screen's visible pixels.</td>
  </tr>
  <tr>
    <td>height</td>
    <td>int</td>
    <td>This is an optional value that defaults to the height of the display and defines how many vertical pixels to clear. When the height is 0, clear starts at the Y position and ends at the bottom of the display. Values less than 0 or greater than the height are adjusted to stay within the boundaries of the screen's visible pixels.</td>
  </tr>
</table>


## Example


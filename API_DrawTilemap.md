# DrawTilemap

By default, the tilemap renders to the display by simply calling DrawTilemap(). This automatically fills the entire display with the visible portion of the tilemap. To have more granular control over how to render the tilemap, you can supply an optional X and Y position to change where it draws on the screen. You can also modify the width (columns) and height (rows) that are displayed too. This is useful if you want to show a HUD or some other kind of image on the screen that is not overridden by the tilemap. To scroll the tilemap, you need to call the ScrollPosition() and supply a new scroll X and Y value.

## Usage

`DrawTilemap ( x, y, columns, rows, offsetX, offsetY, drawMode )`

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
    <td>An optional int value representing the X position to render the tilemap on the display. If set to 0, it renders on the far left-hand side of the screen.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>An optional int value representing the Y position to render the tilemap on the display. If set to 0, it renders on the top of the screen.</td>
  </tr>
  <tr>
    <td>columns</td>
    <td>int</td>
    <td>An optional int value representing how many horizontal tiles to include when drawing the map. By default, this is 0 which automatically uses the full visible width of the display, while taking into account the X position offset.</td>
  </tr>
  <tr>
    <td>rows</td>
    <td>int</td>
    <td>An optional int value representing how many vertical tiles to include when drawing the map. By default, this is 0 which automatically uses the full visible height of the display, while taking into account the Y position offset.</td>
  </tr>
  <tr>
    <td>offsetX</td>
    <td>int?</td>
    <td>An optional int value to override the scroll X position. This is useful when you need to change the left x position from where to sample the tilemap data from.</td>
  </tr>
  <tr>
    <td>offsetY</td>
    <td>int?</td>
    <td>An optional int value to override the scroll Y position. This is useful when you need to change the top y position from where to sample the tilemap data from.</td>
  </tr>
  <tr>
    <td>drawMode</td>
    <td>DrawMode</td>
    <td></td>
  </tr>
</table>



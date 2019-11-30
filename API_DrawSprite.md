# DrawSprite

Sprites represent individual collections of pixel data at a fixed size. By default, Pixel Vision 8 sprites are 8 x 8 pixels and have a set limit of visible colors. You can use the DrawSprite() method to render any sprite stored in the Sprite Chip. The display also has a limitation on how many sprites can be on the screen at one time. Each time you call DrawSprite(), the sprite counts against the total amount the display can render. If you attempt to draw more sprites than the display can handle, the call is ignored. One thing to keep in mind when drawing sprites is that their x and y position wraps if they reach the right or bottom border of the screen. You need to change the overscan border to hide sprites offscreen.

## Usage

`DrawSprite ( id, x, y, flipH, flipV, drawMode, colorOffset )`

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
    <td>The unique ID of the sprite to use in the SpriteChip.</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>An int value representing the X position to place sprite on the display. If set to 0, it renders on the far left-hand side of the screen.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>An int value representing the Y position to place sprite on the display. If set to 0, it renders on the top of the screen.</td>
  </tr>
  <tr>
    <td>flipH</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool. The default value is set to false but passing in true flips the pixel data horizontally.</td>
  </tr>
  <tr>
    <td>flipV</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool. The default value is set to false but passing in true flips the pixel data vertically.</td>
  </tr>
  <tr>
    <td>drawMode</td>
    <td>DrawMode</td>
    <td></td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int</td>
    <td>This optional argument accepts an int that offsets all the color IDs in the pixel data array. This value is added to each int, in the pixel data array, allowing you to simulate palette shifting.</td>
  </tr>
</table>



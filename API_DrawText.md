# DrawText 

The DrawText() method allows you to render text to the display. By supplying a custom DrawMode, you can render characters as individual sprites (DrawMode.Sprite), tiles (DrawMode.Tile) or drawn directly into the tilemap cache (DrawMode.TilemapCache). When drawing text as sprites, you have more flexibility over position, but each character counts against the displays' maximum sprite count. When rendering text to the tilemap, more characters are shown and also increase performance when rendering large amounts of text. You can also define the color offset, letter spacing which only works for sprite and tilemap cache rendering, and a width in characters if you want the text to wrap.

## Usage

DrawText ( text, x, y, drawMode, font, colorOffset, spacing )

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>text</td>
    <td>string</td>
    <td>A text string to display on the screen.</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>An int value representing the X position to start the text on the display. If set to 0, it renders on the far left-hand side of the screen.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>An int value representing the Y position to place sprite on the display. If set to 0, it renders on the top of the screen.</td>
  </tr>
  <tr>
    <td>drawMode</td>
    <td>DrawMode</td>
    <td>This argument accepts the DrawMode enum. You can use Sprite, SpriteBelow, and TilemapCache to change where the pixel data is drawn to. By default, this value is DrawMode.Sprite.</td>
  </tr>
  <tr>
    <td>font</td>
    <td>string</td>
    <td>The name of the font to use. You do not need to add the font's file extension. If the file is called The name of the font to use. You do not need to add the font's file extension. If the file is called default.font.png, you can simply refer to it as "default" when supplying an argument value.</td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int</td>
    <td>This optional argument accepts an int that offsets all the color IDs in the pixel data array. This value is added to each color ID in the font's pixel data, allowing you to simulate palette shifting.</td>
  </tr>
  <tr>
    <td>spacing</td>
    <td>int</td>
    <td>This optional argument sets the number of pixels between each character when rendering text. This value is ignored when rendering text as tiles. This value can be positive or negative depending on your needs. By default, it is 0.</td>
  </tr>
</table>



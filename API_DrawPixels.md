# DrawPixels

This method allows you to draw raw pixel data directly to the display. Depending on which draw mode you use, the pixel data could be rendered as a sprite or drawn directly onto the tilemap cache. Sprites drawn with this method still count against the total number the display can render but you can draw irregularly shaped sprites by defining a custom width and height. For drawnig into the tilemap cache directly, you can use this to change the way the tilemap looks at run-time without having to modify a sprite's pixel data. It is important to note that when you change a tile's sprite ID or color offset, the tilemap redraws it back to the cache overwriting any pixel data that was previously there.

## Usage

`DrawPixels ( pixelData, x, y, width, height, flipH, flipV, drawMode, colorOffset )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>pixelData</td>
    <td>int[]</td>
    <td>The pixelData argument accepts an int array representing references to color IDs. The pixelData array length needs to be the same size as the supplied width and height, or it will throw an error.</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>The x position where to display the new pixel data. The display's horizontal 0 position is on the far left-hand side. When using DrawMode.TilemapCache, the pixel data is drawn into the tilemap's cache instead of directly on the display when using DrawMode.Sprite.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>The Y position where to display the new pixel data. The display's vertical 0 position is on the top. When using DrawMode.TilemapCache, the pixel data is drawn into the tilemap's cache instead of directly on the display when using DrawMode.Sprite.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int</td>
    <td>The width of the pixel data to use when rendering to the display.</td>
  </tr>
  <tr>
    <td>height</td>
    <td>int</td>
    <td>The height of the pixel data to use when rendering to the display.</td>
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
    <td>This argument accepts the DrawMode enum. You can use Sprite, SpriteBelow, and TilemapCache to change where the pixel data is drawn to. By default, this value is DrawMode.Sprite.</td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int</td>
    <td>This optional argument accepts an int that offsets all the color IDs in the pixel data array. This value is added to each int, in the pixel data array, allowing you to simulate palette shifting.</td>
  </tr>
</table>



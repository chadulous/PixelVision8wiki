# Draw Calls

Pixel Vision 8’s renderer takes draw calls and copies their pixel data to the display. These calls are sorted based on their priority and are stored until the display is ready to draw. While the process of how this works isn’t important, it’s helpful to understand the types of draw calls, how they are sorted, and the arguments you can use to configure them. At the rendering pipeline’s core, there is a single process that accepts raw pixel data and copies it to the display. This is part of the `DisplayChip` and is called `NewDrawCall()`.

Pixel Vision 8 exposes the Display’s `NewDrawCall()` method via several helper APIs which makes copying pixel data to the display easier. When you call `DrawSprite()` or `DrawText()`, these methods leverage the `GameChip`’s main draw API called `DrawPixels()`. The `DrawPixels()` API is the bridge between the `GameChip` and the `DisplayChip`. You can always call `DrawPixels()` directly and pass in an array of color IDs to render on the display, but the helper APIs are there to make this process easier. Also, pushing raw pixel data to the display by hand is expensive. Pixel Vision 8 does pixel data caching under the hood to optimize rendering sprites and tiles.

When you use the Drawing APIs, you will need to supply a `DrawMode` enum. Each `DrawMode `targets a specific layer and helps define the priority of each draw call when rendering. Calls with lower values are drawn first, and higher values are drawn over previous requests. Depending on how you configured the system, you can limit the number of layers a game can display to better match the limitations of different 8-bit systems. Here are the layers which are defined in the `DrawMode` enum.

<table>
  <tr>
    <td>Enum</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>DrawMode.TilemapCache</td>
    <td>-1</td>
    <td>This is technically not a layer and is used to draw pixel data directly into the tilemap’s pixel data cache.</td>
  </tr>
  <tr>
    <td>DrawMode.Background</td>
    <td>0</td>
    <td>This is the clear layer and is usually reserved for filling the screen with a background color.</td>
  </tr>
  <tr>
    <td>DrawMode.SpriteBelow</td>
    <td>1</td>
    <td>This is a layer dedicated to sprites just above the background.</td>
  </tr>
  <tr>
    <td>DrawMode.Tile</td>
    <td>2</td>
    <td>This is the tilemap layer and is drawn above the SpriteBelow layer allowing sprites to appear behind the background.</td>
  </tr>
  <tr>
    <td>DrawMode.Sprite</td>
    <td>3</td>
    <td>This is the default layer for sprites to be rendered at. It is above the background.</td>
  </tr>
  <tr>
    <td>DrawMode.UI</td>
    <td>4</td>
    <td>This is a special layer that can be used to draw raw pixel data above the background and sprites. It's designed for HUDs in your game and other graphics that do not scroll with the tilemap.</td>
  </tr>
  <tr>
    <td>DrawMode.SpriteAbove</td>
    <td>5</td>
    <td>This layer allows sprites to render above the UI layer. It is useful for mouse cursors or other graphics that need to be on top of all other layers.</td>
  </tr>
</table>


Just keep in mind that using `DrawMode`.`Tile` will change the `X` and `Y` position to `columns` and `rows`. The tile layer is the only layer that doesn’t require to be constantly updated from frame to frame. You should only draw sprites to the tile layer when needed since updating it will force the engine to re-cache parts of the tilemap’s pixel data and may actually slow down rendering. Likewise, you can draw raw pixel data into this tilemap cache layer on top of a tile by using the `DrawMode.TilemapCache` enum.


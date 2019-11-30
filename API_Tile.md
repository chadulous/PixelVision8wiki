# Tile

This allows you to get the current sprite id, color offset and flag values associated with a given tile. You can optionally supply your own if you want to change the tile's values. Changing a tile's sprite id or color offset will for the tilemap to redraw it to the cache on the next frame. If you are drawing raw pixel data into the tilemap cache in the same position, it will be overwritten with the new tile's pixel data.

## Usage

`Tile ( column, row, spriteID, colorOffset, flag, flipH, flipV )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>column</td>
    <td>int</td>
    <td>The X position of the tile in the tilemap. The 0 position is on the far left of the tilemap.</td>
  </tr>
  <tr>
    <td>row</td>
    <td>int</td>
    <td>The Y position of the tile in the tilemap. The 0 position is on the top of the tilemap.</td>
  </tr>
  <tr>
    <td>spriteID</td>
    <td>int?</td>
    <td>The sprite id to use for the tile.</td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int?</td>
    <td>Shift the color IDs by this value.</td>
  </tr>
  <tr>
    <td>flag</td>
    <td>int?</td>
    <td>An int value between -1 and 16 used for collision detection.</td>
  </tr>
  <tr>
    <td>flipH</td>
    <td>bool?</td>
    <td></td>
  </tr>
  <tr>
    <td>flipV</td>
    <td>bool?</td>
    <td></td>
  </tr>
</table>


## Returns

<table>
  <tr>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>TileData</td>
    <td>Returns a TileData object containing the spriteID, colorOffset, and flag for an individual tile.</td>
  </tr>
</table>



# UpdateTiles

A helper method which allows you to update several tiles at once. Simply define the start column and row position, the width of the area to update in tiles and supply a new int array of sprite IDs. You can also modify the color offset and flag value of the tiles via the optional parameters. This helper method uses calls the Tile() method to update each tile, so any changes to a tile will be automatically redrawn to the tilemap's cache.

## Usage

`UpdateTiles ( column, row, columns, ids, colorOffset, flag )`

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
    <td>Start column of the first tile to update. The 0 column is on the far left of the tilemap.</td>
  </tr>
  <tr>
    <td>row</td>
    <td>int</td>
    <td>Start row of the first tile to update. The 0 row is on the top of the tilemap.</td>
  </tr>
  <tr>
    <td>columns</td>
    <td>int</td>
    <td>The width of the area in tiles to update.</td>
  </tr>
  <tr>
    <td>ids</td>
    <td>int[]</td>
    <td>An array of sprite IDs to use for each tile being updated.</td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int?</td>
    <td>An optional color offset int value to be applied to each updated tile.</td>
  </tr>
  <tr>
    <td>flag</td>
    <td>int?</td>
    <td>An optional flag int value to be applied to each updated tile.</td>
  </tr>
</table>



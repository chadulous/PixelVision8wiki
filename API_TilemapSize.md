# TilemapSize

This will return a Point representing the size of the tilemap in columns (x) and rows (y). To find the size in pixels, you will need to multiply the returned Point’s x and y values by the sprite size's x and y. This method also allows you to resize the tilemap by passing in an optional new width and height. Resizing the tile map is destructive, so any changes will automatically clear the tilemap's sprite ids, color offsets, and flag values.

## Usage

`TilemapSize ( width, height, clear )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int?</td>
    <td>An optional parameter for the width in tiles of the map.</td>
  </tr>
  <tr>
    <td>height</td>
    <td>int?</td>
    <td>An optional parameter for the height in tiles of the map.</td>
  </tr>
  <tr>
    <td>clear</td>
    <td>bool</td>
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
    <td>Point</td>
    <td>Returns a Point of the tile maps size in tiles where x and y are the columns and rows of the tilemap.</td>
  </tr>
</table>



# Flag

This allows you to quickly access just the flag value of a tile. This is useful when trying to the caluclate collision on the tilemap. By default, you can call this method and return the flag value. If you supply a new value, it will be overridden on the tile. Changing a tile's flag value does not force the tile to be redrawn to the tilemap cache.

## Usage

`Flag ( column, row, value )`

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
    <td>value</td>
    <td>int?</td>
    <td>The new value for the flag. Setting the flag to -1 means no collision.</td>
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
    <td></td>
  </tr>
</table>



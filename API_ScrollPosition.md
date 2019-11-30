# ScrollPosition ( x, y )

You can scroll the tilemap by calling the ScrollPosition() method and supplying a new scroll X and Y position. By default, calling ScrollPosition() with no arguments returns a Point with the current scroll X and Y values. If you supply an X and Y value, it updates the tilemap's scroll position the next time you call the DrawTilemap() method.

## Summary

`ScrollPosition ( x, y )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int?</td>
    <td>An optional int value representing the scroll X position of the tilemap. If set to 0, it starts on the far left-hand side of the tilemap.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int?</td>
    <td>An optional int value representing the scroll Y position of the tilemap. If set to 0, it starts on the top of the tilemap.</td>
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
    <td>By default, this method returns a Point with the current scroll X and Y position.</td>
  </tr>
</table>



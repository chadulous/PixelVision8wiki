# RebuildCache

This method converts the tile map into pixel data that can be rendered by the engine. It's an expensive operation and should only be called when the game or level is loading up. This data can be passed into the ScreenBufferChip to allow cached rendering of the tile map as well as scrolling of the tile map if it is larger then the screen's resolution.

## Usage

`RebuildCache ( ``targetTextureData ``)`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>targetTextureData</td>
    <td>Canvas</td>
    <td></td>
  </tr>
</table>


## Returns


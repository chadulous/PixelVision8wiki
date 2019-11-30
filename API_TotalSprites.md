# TotalSprites

Returns the total number of sprites in the system. You can pass in an optional argument to get a total number of sprites the Sprite Chip can store by passing in false for ignoreEmpty. By default, only sprites with pixel data will be included in the total return.

## Usage

`TotalSprites ( bool ignoreEmpty )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>ignoreEmpty</td>
    <td>bool</td>
    <td>This is an optional value that defaults to true. When set to true, the SpriteChip returns the total number of sprites that are not empty (where all the pixel data is set to -1). Set this value to false if you want to get all of the available color slots in the ColorChip regardless if they are empty or not.</td>
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
    <td>This method returns the total number of sprites in the color chip based on the ignoreEmpty argument's value.</td>
  </tr>
</table>



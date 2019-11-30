# Sprite

This allows you to return the pixel data of a sprite or overwrite it with new data. Sprite pixel data is an array of color reference ids. When calling the method with only an id argument, you will get the sprite's pixel data. If you supply data, it will overwrite the sprite. It is important to make sure that any new pixel data should be the same length of the existing sprite's pixel data. This can be calculated by multiplying the sprite's width and height. You can add the transparent area to a sprite's data by using -1.

## Summary

Sprite ( id, data )

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td>The sprite to access.</td>
  </tr>
  <tr>
    <td>data</td>
    <td>int[]</td>
    <td>Optional data to write over the sprite's current pixel data.</td>
  </tr>
</table>


## Returns

<table>
  <tr>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>int[]</td>
    <td>Returns an array of int data which points to color ids.</td>
  </tr>
</table>



# NewRect

A Rect is a Pixel Vision 8 primitive used for defining the bounds of an object on the display. It contains an x, y, width and height property. The Rect class also has some additional methods to aid with collision detection such as Intersect(rect, rect), IntersectsWidth(rect) and Contains(x,y).

## Usage

`NewRect ( x, y, w, h )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>The x position of the rect as an int.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>The y position of the rect as an int.</td>
  </tr>
  <tr>
    <td>w</td>
    <td>int</td>
    <td>The width value of the rect as an int.</td>
  </tr>
  <tr>
    <td>h</td>
    <td>int</td>
    <td>The height value of the rect as an int.</td>
  </tr>
</table>


## Returns

<table>
  <tr>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Rect</td>
    <td>Returns a new instance of a Rect to be used as a Lua object.</td>
  </tr>
</table>



# Display

The display's size defines the visible area where pixel data exists on the screen. Calculating this is important for knowing how to position sprites on the screen. The Display() method allows you to get the resolution of the display at run time. By default, this will return the visible screen area based on the overscan value set on the display chip. To calculate the exact overscan in pixels, you must subtract the full size from the visible size. Simply supply false as an argument to get the full display dimensions.

## Usage

`Display ( visible )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>visible</td>
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
    <td></td>
  </tr>
</table>



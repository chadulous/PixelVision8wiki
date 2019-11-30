Color

The Color() method allows you to read and update color values in the ColorChip. This method has two modes which require a color ID to work. By calling the method with just an ID, like Color(0), it returns a hex string for the given color at the supplied color ID. By passing in a new hex string, like Color(0, "#FFFF00"), you can change the color with the given ID. While you can use this method to modify color values directly, you should avoid doing this at run time since the DisplayChip must parse and cache the new hex value. If you just want to change a color to an existing value, use the ReplaceColor() method.

## Usage

`Color ( int id, string value )`

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
    <td>The ID of the color you want to access.</td>
  </tr>
  <tr>
    <td>value</td>
    <td>string</td>
    <td>This argument is optional. It accepts a hex as a string and updates the supplied color ID's value.</td>
  </tr>
</table>


## Returns

<table>
  <tr>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>string</td>
    <td>This method returns a hex string for the supplied color ID. If the color has not been set or is out of range, it returns magenta (#FF00FF) which is the default transparent system color.</td>
  </tr>
</table>



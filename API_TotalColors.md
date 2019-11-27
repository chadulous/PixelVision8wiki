# TotalColors

The TotalColors() method simply returns the total number of colors in the ColorChip. By default, it returns only colors that have been set to value other than magenta (#FF00FF) which is the default transparent value used by the engine. By calling TotalColors(false), it returns the total available color slots in the ColorChip.

## Usage

TotalColors ( ignoreEmpty )

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
    <td>This is an optional value that defaults to true. When set to true, the ColorChip returns the total number of colors not set to magenta (#FF00FF). Set this value to false if you want to get all of the available color slots in the ColorChip regardless if they are empty or not.</td>
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
    <td>This method returns the total number of colors in the color chip based on the ignoreEmpty argument's value.</td>
  </tr>
</table>



# ReplaceColor

The ReplaceColor() method allows you to quickly change a color to an existing color without triggering the DisplayChip to parse and cache a new hex value. Consider this an alternative to the Color() method. It is useful for simulating palette swapping animation on sprites pointed to a fixed group of color IDs. Simply cal the ReplaceColor() method and supply a target color ID position, then the new color ID it should point to. Since you are only changing the color's ID pointer, there is little to no performance penalty during the GameChip's draw phase.

## Usage

`ReplaceColor ( index, id )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>index</td>
    <td>int</td>
    <td>The ID of the color you want to change.</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td>The ID of the color you want to replace it with.</td>
  </tr>
</table>



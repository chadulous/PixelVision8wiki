# WordWrap

This allows you to call the TextUtil's WordWrap helper to wrap a string of text to a specified character width. Since the FontChip only knows how to render characters as sprites, this can be used to calculate blocks of text then each line can be rendered with a DrawText() call.

## Usage

`WordWrap ( text, width )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>text</td>
    <td>string</td>
    <td>The string of text to wrap.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int</td>
    <td>The width of characters to wrap each line of text.</td>
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
    <td></td>
  </tr>
</table>



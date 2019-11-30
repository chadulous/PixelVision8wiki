# MouseButton

Pixel Vision 8 supports mouse input. You can get the current state of the mouse's left (0) and right (1) buttons by calling MouseButton(). In addition to supplying a button ID, you also need to provide the InputState enum. The InputState enum contains options for testing the Down and Released states of the supplied button ID. By default, Down is automatically used which returns true when the key was pressed in the current frame. When using Released, the method returns true if the key is currently up but was down in the last frame.

## Summary

`MouseButton ( button, state )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>button</td>
    <td>int</td>
    <td>Accepts an int for the left (0) or right (1) mouse button.</td>
  </tr>
  <tr>
    <td>state</td>
    <td>InputState</td>
    <td>An optional InputState enum. Uses InputState.Down default.</td>
  </tr>
</table>


## Returns

<table>
  <tr>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>bool</td>
    <td>Returns a bool based on the state of the button.</td>
  </tr>
</table>



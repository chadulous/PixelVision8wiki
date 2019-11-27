# Key

While the main form of input in Pixel Vision 8 comes from the controllers, you can test for keyboard input by calling the Key() method. When called, this method returns the current state of a key. The method accepts the Keys enum, or an int, for a specific key. In additon, you need to provide the input state to check for. The InputState enum has two states, Down and Released. By default, Down is automatically used which returns true when the key is being pressed in the current frame. When using Released, the method returns true if the key is currently up but was down in the last frame.

## Usage

`Key ( key, state )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>key</td>
    <td>Keys</td>
    <td>This argument accepts the Keys enum or an int for the key's ID.</td>
  </tr>
  <tr>
    <td>state</td>
    <td>InputState</td>
    <td>Optional InputState enum. Returns down state by default. This argument accepts InputState.Down (0) or InputState.Released (1).</td>
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
    <td>This method returns a bool based on the state of the button.</td>
  </tr>
</table>



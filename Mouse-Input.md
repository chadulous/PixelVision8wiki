# Mouse Input

Pixel Vision 8 offers access to the mouse’s position and button states. Unlike controllers or keys, this is considered a special input and displaying a cursor or pointer will have to be manually drawn to the screen.

To access the mouse’s position, you can call the `MousePosition()` method:

`value = MousePosition()`

This will return a `Point `containing the current `X` and `Y` value for the mouse. The mouse position can not be manually changed. It’s directly tied to the native system’s mouse pointer.

In addition to getting the mouse position, you can also poll the mouse’s button state. This can be done by calling the` MouseButton()` method. It requires a button ID and state value.

<table>
  <tr>
    <td>ID</td>
    <td>Button</td>
  </tr>
  <tr>
    <td>0</td>
    <td>Left</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Right</td>
  </tr>
</table>


In addition to the Button ID, you can supply a different input state similar to how the controller input works. There are two options in the `InputState `enum:

<table>
  <tr>
    <td>Enum</td>
    <td>Int</td>
  </tr>
  <tr>
    <td>InputState.Down</td>
    <td>0</td>
  </tr>
  <tr>
    <td>InputState.Released</td>
    <td>1</td>
  </tr>
</table>


When calling the `MouseButton()` method and supplying `InputState`.`Released`, it returns `true `if the mouse button was down in the previous frame and is up in the current frame. Just like with the Buttons enum, you can use the `InputState `enum or supply an int for either state. 

Finally, if you do not supply a button ID or input state, the `MouseButton()` method will automatically default to the left mouse button and the down input state.


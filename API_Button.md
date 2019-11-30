# Button

The main form of input for Pixel Vision 8 is the controller's buttons. You can get the current state of any button by calling the Button() method and supplying a button ID, an InputState enum, and the controller ID. When called, the Button() method returns a bool for the requested button and its state. The InputState enum contains options for testing the Down and Released states of the supplied button ID. By default, Down is automatically used which returns true when the key was pressed in the current frame. When using Released, the method returns true if the key is currently up but was down in the last frame.

## Usage

`Button ( button, state, controllerID )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>button</td>
    <td>Buttons</td>
    <td>Accepts the Buttons enum or int for the button's ID.</td>
  </tr>
  <tr>
    <td>state</td>
    <td>InputState</td>
    <td>Optional InputState enum. Returns down state by default.</td>
  </tr>
  <tr>
    <td>controllerID</td>
    <td>int</td>
    <td>An optional int representing a controller ID. Player 1 is 0 and player 2 is 1. leaving this empty will deafult to player 1.</td>
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


## Button Options

Each controller has X buttons. Each button has a specific ID or you can reference it by the button’s enum name.

[TABLE]

## Input State Options

There are two input states you can use to test a button’s current state.

[TABLE]

## Example


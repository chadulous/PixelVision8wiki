# AddTextFile

This allows you to add your Lua scripts at runtime to a game from a string. This could be useful for dynamically generating code such as level data or other custom Lua objects in memory. Simply give the script a name and pass in a string with a valid Lua code. If a script with the same name exists, this will override it. Make sure to call `LoadScript()` after to parse it.

## Usage

`AddTextFile ( name, file )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>name</td>
    <td>string</td>
    <td>Name of the script. This should contain the .lua extension.</td>
  </tr>
  <tr>
    <td>file</td>
    <td>string</td>
    <td>The string text representing the Lua script data.</td>
  </tr>
</table>


## Example


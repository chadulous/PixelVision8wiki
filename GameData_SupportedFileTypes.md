# Supported File Types

Here are the supported files that can go inside of a PV8 game:

<table>
  <tr>
    <td>Name</td>
    <td>Ext.</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>code</td>
    <td>.lua</td>
    <td>This Lua file, which contains all the code to run the game.</td>
  </tr>
  <tr>
    <td>color-map</td>
    <td>.png</td>
    <td>The color map represents a file that can be used to match up colors in the sprite.png to the order in the colors.png.</td>
  </tr>
  <tr>
    <td>colors</td>
    <td>.png</td>
    <td>The color image contains all the system colors used for rendering. These colors should be 1x1 pixel for each color.</td>
  </tr>
  <tr>
    <td>data</td>
    <td>.json</td>
    <td>The data file represents the game’s system settings and its limitations.</td>
  </tr>
  <tr>
    <td>font</td>
    <td>.png</td>
    <td>This is a default font to be used at run-time. It works similar to the sprite.png, except the order is based on ASCII code. It starts at 32 (spaces) and supports any number of characters you add.</td>
  </tr>
  <tr>
    <td>info</td>
    <td>.json</td>
    <td>This is a metadata file that defines values such as the game’s name, description and some additional values used by other tools and Pixel Vision OS.</td>
  </tr>
  <tr>
    <td>music</td>
    <td>.json</td>
    <td>This JSON file contains a list of songs and patterns allowing you to store and playback collections of sound effects as music.</td>
  </tr>
  <tr>
    <td>sprites</td>
    <td>.png</td>
    <td>This image file contains all of the sprites that the game uses. It is automatically loaded and cut up into 8x8 sprites based on the order of images in the file. </td>
  </tr>
  <tr>
    <td>sound</td>
    <td>.json</td>
    <td>This JSON file contains all of the Sfxr properties for your game’s sound effects.</td>
  </tr>
  <tr>
    <td>tilemap</td>
    <td>.json</td>
    <td>This JSON file represents a tilemap to be used in the game. It includes objects for each tile, their sprite ID, collision flag value and any color offset.</td>
  </tr>
  <tr>
    <td>tilemap</td>
    <td>.png</td>
    <td>You can also store tilemap data as a PNG file. This image will be loaded by default if a tilemap.json file does not exist. PNG tilemaps to not store collision flag or color offset values. The tiles contained in the PNG will need to match the sprites that are already loaded in memory.</td>
  </tr>
</table>


PV8 will ignore any additional files in a project it doesn’t know how to open or edit. Sprites and tilemaps can be created at runtime via the API. When Pixel Vision OS detects the necessary files in a folder for it to run, it will automatically display a Run icon allowing you to launch it.


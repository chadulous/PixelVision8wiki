When Pixel Vision 8 runs a game, each file is loaded in a specific order. Knowing this order is important to understand how a game’s data is parsed by the engine. Here are the steps that Pixel Vision 8 performs when loading a game’s files:

<table>
  <tr>
    <td>Order</td>
    <td>Type</td>
    <td>File Name</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>1</td>
    <td>System Data</td>
    <td>data.json</td>
    <td>This file overrides any default chip settings before anything else is parsed.</td>
  </tr>
  <tr>
    <td>2</td>
    <td>System Colors</td>
    <td>colors.png</td>
    <td>All of the colors in this file will replace the default system colors.</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Color Map</td>
    <td>color-map.png</td>
    <td>This is stored in a temporary ColorChip and used instead of the system colors for parsing sprites, font, and tilemap PNG files.</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Sprites</td>
    <td>sprites.png</td>
    <td>This PNG file is cut up into 8x8 sprites based on the system colors or color map that was previously loaded.</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Tile Map</td>
    <td>tilemap.png or tilemap.json</td>
    <td>This file can be a PNG or JSON. If both are present, the json file will be the one that is loaded. When parsing a PNG, you can set a flag that will add any tiles that are not found in the SpriteChip’s memory.</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Fonts</td>
    <td>*.font.png</td>
    <td>Each font PNG is cut up into 8x8 sprites and added to the SpriteChip’s memory if there is space. After each font is parsed, references to each character sprite are saved in the FontChip under the font file’s name minus the .font.png extension.</td>
  </tr>
  <tr>
    <td>7</td>
    <td>Sounds</td>
    <td>sound.json</td>
    <td>Each sound effect is parsed and stored in the sound chip.</td>
  </tr>
  <tr>
    <td>8</td>
    <td>Music</td>
    <td>music.json</td>
    <td>The music file contains songs and patterns. Patterns are collections of sound effects the tracker plays in a specific order and frequency while the songs are collections of patterns.</td>
  </tr>
  <tr>
    <td>9</td>
    <td>Metadata</td>
    <td>info.json</td>
    <td>This contains additional information about the game that is not used to configure any of the other parsers.</td>
  </tr>
</table>


Once these files are loaded into memory, changes made to them will not be reflected in the game at run-time. 


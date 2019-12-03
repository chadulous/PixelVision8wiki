# GameChip API Cheatsheet

All Pixel Vision 8 games have access to a set of common set of APIs in C# and Lua. These are exposed via the Game Chip. This bridge allows you to access the native properties and methods of the core framework. Below is a  of the GameChip’s APIs.

## LifeCycle APIs

<table>
  <tr>
    <td>Name</td>
    <td>Arguments</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>Init</td>
    <td></td>
    <td>Init() is called when a game first loads up.</td>
  </tr>
  <tr>
    <td>Draw</td>
    <td></td>
    <td>Draw() is called once per frame after the Update() has completed.</td>
  </tr>
  <tr>
    <td>Reset</td>
    <td></td>
    <td>Reset() is called when a game is restarted.</td>
  </tr>
  <tr>
    <td>Update</td>
    <td>timeDelta</td>
    <td>Update() is called once per frame at the beginning of the game loop.</td>
  </tr>
  <tr>
    <td>Shutdown</td>
    <td></td>
    <td>Shutdown() is called when a game is shutting down.</td>
  </tr>
</table>


## Game APIs

### BackgroundColor ( id )

The background color is used to fill the screen when clearing the display. This method returns the current background color ID.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int?</td>
    <td>This argument is optional. Supply an int to update the existing background color value.</td>
  </tr>
</table>


* * *


### Button ( Buttons button, InputState state, int controllerID )

The main form of input for Pixel Vision 8 is the controller's buttons. Returns a bool based on the state of the button.

#### Arguments

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
    <td>An optional InputState enum. Uses InputState.Down default.</td>
  </tr>
</table>


* * *


### Clear ( x, y, width, height )

Clearing the display removed all of the existing pixel data, replacing it with the default background color. 

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>This is an optional value that defaults to 0 and defines where the clear's X position should begin. </td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>This is an optional value that defaults to 0 and defines where the clear's Y position should begin.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int?</td>
    <td>This is an optional value that defaults to the width of the display and defines how many horizontal pixels to clear.</td>
  </tr>
  <tr>
    <td>height</td>
    <td>int?</td>
    <td>This is an optional value that defaults to the height of the display and defines how many vertical pixels to clear.</td>
  </tr>
</table>


#### * * *


### Color ( id, value )

The Color() method allows you to read and update color values in the ColorChip. This method returns a hex string for the supplied color ID.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td>The ID of the color you want to access.</td>
  </tr>
  <tr>
    <td>value</td>
    <td>string</td>
    <td>This argument is optional. It accepts a hex as a string and updates the supplied color ID's value.</td>
  </tr>
</table>


* * *


### Display ( visible )

The display's size defines the visible area where pixel data exists on the screen. Returns the resolution of the display.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>visible</td>
    <td>bool</td>
    <td></td>
  </tr>
</table>


#### * * *


### DrawPixels ( pixelData, x, y, width, height, flipH, flipV, drawMode, colorOffset )

This method allows you to draw raw pixel data directly to the display. 

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>pixelData</td>
    <td>int[]</td>
    <td>The pixelData argument accepts an int array representing references to color IDs.</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>The x position where to display the new pixel data..</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>The Y position where to display the new pixel data.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int</td>
    <td>The width of the pixel data to use when rendering to the display.</td>
  </tr>
  <tr>
    <td>height</td>
    <td>int</td>
    <td>The height of the pixel data to use when rendering to the display.</td>
  </tr>
  <tr>
    <td>flipH</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool.</td>
  </tr>
  <tr>
    <td>flipV</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool.</td>
  </tr>
  <tr>
    <td>drawMode</td>
    <td>DrawMode</td>
    <td>This argument accepts the DrawMode enum.</td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int</td>
    <td>This optional argument accepts an int that offsets all the color IDs in the pixel data array.</td>
  </tr>
</table>


#### * * *


### DrawRect ( x, y, width, height, color, drawMode )

This method allows you to draw a rectangle with a fill color. 

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td></td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td></td>
  </tr>
  <tr>
    <td>width</td>
    <td>int</td>
    <td></td>
  </tr>
  <tr>
    <td>height</td>
    <td>int</td>
    <td></td>
  </tr>
  <tr>
    <td>color</td>
    <td>int</td>
    <td></td>
  </tr>
  <tr>
    <td>drawMode</td>
    <td>DrawMode</td>
    <td></td>
  </tr>
</table>


#### * * *


### DrawSprite ( id, x, y, flipH, flipV, drawMode, colorOffset )

Sprites represent individual collections of pixel data at a fixed size. 

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td>The unique ID of the sprite to use in the SpriteChip.</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>An int value representing the X position to place sprite on the display. </td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>An int value representing the Y position to place sprite on the display. </td>
  </tr>
  <tr>
    <td>flipH</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool.</td>
  </tr>
  <tr>
    <td>flipV</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool.</td>
  </tr>
  <tr>
    <td>drawMode</td>
    <td>DrawMode</td>
    <td></td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int</td>
    <td>This optional argument accepts an int that offsets all the color IDs in the pixel data array.</td>
  </tr>
</table>


#### * * *


### DrawSpriteBlock ( id, x, y, width, height, flipH, flipV, drawMode, colorOffset, onScreen, useScrollPos, bounds )

DrawSpriteBlock() is similar to DrawSprites except you define the first sprite (upper left corner) and the width x height (in sprites) to sample from sprite ram.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td>The top left sprite to start with.</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>An int value representing the X position to place sprite on the display.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>An int value representing the Y position to place sprite on the display.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int</td>
    <td>The width, in sprites, of the grid.</td>
  </tr>
  <tr>
    <td>height</td>
    <td>int</td>
    <td></td>
  </tr>
  <tr>
    <td>flipH</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool.</td>
  </tr>
  <tr>
    <td>flipV</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool</td>
  </tr>
  <tr>
    <td>drawMode</td>
    <td>DrawMode</td>
    <td></td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int</td>
    <td>This optional argument accepts an int that offsets all the color IDs in the pixel data array.</td>
  </tr>
  <tr>
    <td>onScreen</td>
    <td>bool</td>
    <td>This flag defines if the sprites should not render when they are off the screen.</td>
  </tr>
  <tr>
    <td>useScrollPos</td>
    <td>bool</td>
    <td>This will automatically offset the sprite's x and y position based on the scroll value.</td>
  </tr>
  <tr>
    <td>bounds</td>
    <td>Rectangle?</td>
    <td></td>
  </tr>
</table>


#### * * *


### DrawSprites ( ids, x, y, width, flipH, flipV, drawMode, colorOffset, onScreen, useScrollPos, bounds )

The DrawSprites method makes it easier to combine and draw groups of sprites to the display in a grid. 

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>ids</td>
    <td>int[]</td>
    <td>An array of sprite IDs to display on the screen.</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>An int value representing the X position to place sprite on the display.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>An int value representing the Y position to place sprite on the display.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int</td>
    <td>The width, in sprites, of the grid. A value of 2 renders 2 sprites wide. </td>
  </tr>
  <tr>
    <td>flipH</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool.</td>
  </tr>
  <tr>
    <td>flipV</td>
    <td>bool</td>
    <td>This is an optional argument which accepts a bool.</td>
  </tr>
  <tr>
    <td>drawMode</td>
    <td>DrawMode</td>
    <td></td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int</td>
    <td>This optional argument accepts an int that offsets all the color IDs in the pixel data array.</td>
  </tr>
  <tr>
    <td>onScreen</td>
    <td>bool</td>
    <td>This flag defines if the sprites should not render when they are off the screen.</td>
  </tr>
  <tr>
    <td>useScrollPos</td>
    <td>bool</td>
    <td>This will automatically offset the sprite's x and y position based on the scroll value.</td>
  </tr>
  <tr>
    <td>bounds</td>
    <td>Rectangle?</td>
    <td></td>
  </tr>
</table>


#### * * *


### DrawText ( text, x, y, drawMode, font, colorOffset, spacing )

The DrawText() method allows you to render text to the display.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>text</td>
    <td>string</td>
    <td>A text string to display on the screen.</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>An int value representing the X position to start the text on the display.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>An int value representing the Y position to place sprite on the display.</td>
  </tr>
  <tr>
    <td>drawMode</td>
    <td>DrawMode</td>
    <td>This argument accepts the DrawMode enum.</td>
  </tr>
  <tr>
    <td>font</td>
    <td>string</td>
    <td>The name of the font to use.</td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int</td>
    <td>This optional argument accepts an int that offsets all the color IDs in the pixel data array. </td>
  </tr>
  <tr>
    <td>spacing</td>
    <td>int</td>
    <td>This optional argument sets the number of pixels between each character when rendering text.</td>
  </tr>
</table>


#### * * *


### DrawTilemap ( x, y, columns, rows, offsetX, offsetY, drawMode )

By default, the tilemap renders to the display by simply calling DrawTilemap(). 

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>An optional int value representing the X position to render the tilemap on the display. </td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>An optional int value representing the Y position to render the tilemap on the display.</td>
  </tr>
  <tr>
    <td>columns</td>
    <td>int</td>
    <td>An optional int value representing how many horizontal tiles to include when drawing the map. </td>
  </tr>
  <tr>
    <td>rows</td>
    <td>int</td>
    <td>An optional int value representing how many vertical tiles to include when drawing the map.</td>
  </tr>
  <tr>
    <td>offsetX</td>
    <td>int?</td>
    <td>An optional int value to override the scroll X position.</td>
  </tr>
  <tr>
    <td>offsetY</td>
    <td>int?</td>
    <td>An optional int value to override the scroll Y position.</td>
  </tr>
  <tr>
    <td>drawMode</td>
    <td>DrawMode</td>
    <td></td>
  </tr>
</table>


#### * * *


### Flag ( column, row, value )

This allows you to quickly access just the flag value of a tile.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>column</td>
    <td>int</td>
    <td>The X position of the tile in the tilemap. The 0 position is on the far left of the tilemap.</td>
  </tr>
  <tr>
    <td>row</td>
    <td>int</td>
    <td>The Y position of the tile in the tilemap. The 0 position is on the top of the tilemap.</td>
  </tr>
  <tr>
    <td>value</td>
    <td>int?</td>
    <td>The new value for the flag. Setting the flag to -1 means no collision.</td>
  </tr>
</table>


### * * *


### Key ( key, state )

While the main form of input in Pixel Vision 8 comes from the controllers, you can test for keyboard input by calling the Key() method. This method returns a bool based on the state of the button.

#### Arguments

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


### * * *


### MouseButton ( int button, InputState state )

Pixel Vision 8 supports mouse input. Returns a bool based on the state of the button.

#### Arguments

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


* * *


### MousePosition ( )

The MousePosition() method returns a vector for the current cursor's X and Y position. This value is read-only. The mouse's 0,0 position is in the upper left-hand corner of the display

#### * * *


### PaletteOffset ( int value )

This method will automatically calculate the start color offset for palettes in the color chip.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>value</td>
    <td>int</td>
    <td>The palette number, 1 - 8</td>
  </tr>
</table>


### * * *


### PauseSong ( )

Toggles the current playback state of the sequencer. If the song is playing it will pause, if it is paused it will play.

### * * *


### PlayPattern ( id, loop )

This helper method allows you to automatically load a set of patterns as a complete song and plays them back. 

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td></td>
  </tr>
  <tr>
    <td>loop</td>
    <td>bool</td>
    <td>A bool that determines if the song should loop back to the first ID when it is done playing.</td>
  </tr>
</table>


### * * *


### PlayPatterns ( loopIDs, loop )

This helper method allows you to automatically load a set of patterns as a complete song and plays them back.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>loopIDs</td>
    <td>int[]</td>
    <td>An array of loop IDs to playback as a single song.</td>
  </tr>
  <tr>
    <td>loop</td>
    <td>bool</td>
    <td>A bool that determines if the song should loop back to the first ID when it is done playing.</td>
  </tr>
</table>


### * * *


### PlaySong ( id, loop, startAt )

Plays a song by its ID. You can pass in a start position for it to being at a specific pattern ID in the song.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td></td>
  </tr>
  <tr>
    <td>loop</td>
    <td>bool</td>
    <td></td>
  </tr>
  <tr>
    <td>startAt</td>
    <td>int</td>
    <td></td>
  </tr>
</table>


### * * *


### PlaySound ( id, channel )

This method plays back a sound on a specific channel. 

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td>The ID of the sound in the SoundCollection.</td>
  </tr>
  <tr>
    <td>channel</td>
    <td>int</td>
    <td>The channel the sound should play back on. Channel 0 is set by default.</td>
  </tr>
</table>


### * * *


### ReadSaveData ( key, defaultValue )

Allows you to read saved data by supplying a key. Returns string data associated with the supplied key.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>key</td>
    <td>string</td>
    <td>The string key used to find the data.</td>
  </tr>
  <tr>
    <td>defaultValue</td>
    <td>string</td>
    <td>The optional string to use if data does not exist.</td>
  </tr>
</table>


### * * *


### RebuildTilemap ( )

This forces the map to redraw its cached pixel data. Use this to clear any pixel data added after the map created the pixel data cache.

### * * *


### RedrawDisplay ( )

You can use RedrawDisplay to make clearing and drawing the tilemap easier. This is a helper method automatically calls both Clear() and DrawTilemap() for you.

### * * *


### RewindSong ( position, loopID )

Rewinds the sequencer to the beginning of the currently loaded song.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>position</td>
    <td>int</td>
    <td>Position in the loop to start playing at.</td>
  </tr>
  <tr>
    <td>loopID</td>
    <td>int</td>
    <td>The loop to rewind too.</td>
  </tr>
</table>


### * * *


### ScrollPosition ( x, y )

You can scroll the tilemap by calling the ScrollPosition() method and supplying a new scroll X and Y position. By default, this method returns a vector with the current scroll X and Y position.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int?</td>
    <td>An optional int value representing the scroll X position of the tilemap. If set to 0, it starts on the far left-hand side of the tilemap.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int?</td>
    <td>An optional int value representing the scroll Y position of the tilemap. If set to 0, it starts on the top of the tilemap.</td>
  </tr>
</table>


### * * *


### Sound ( int id, string data )

This method allows your read and write raw sound data on the SoundChip.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td></td>
  </tr>
  <tr>
    <td>data</td>
    <td>string</td>
    <td></td>
  </tr>
</table>


### * * *


### Sprite ( id, data )

This allows you to return the pixel data of a sprite or overwrite it with new data. Returns an array of int data which points to color ids.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>id</td>
    <td>int</td>
    <td>The sprite to access.</td>
  </tr>
  <tr>
    <td>data</td>
    <td>int[]</td>
    <td>Optional data to write over the sprite's current pixel data.</td>
  </tr>
</table>


* * *


### Sprites ( ids, width )

This allows you to get the pixel data of multiple sprites.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>ids</td>
    <td>int[]</td>
    <td></td>
  </tr>
  <tr>
    <td>width</td>
    <td>int</td>
    <td></td>
  </tr>
</table>


### * * *


### StopSong ( )

Stops the sequencer.

### * * *


### StopSound ( channel )

Use StopSound() to stop any sound playing on a specific channel.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>channel</td>
    <td>int</td>
    <td>The channel ID to stop a sound on.</td>
  </tr>
</table>


### * * *


### Tile ( column, row, spriteID, colorOffset, flag, flipH, flipV )

This allows you to get the current sprite id, color offset and flag values associated with a given tile. Returns a dictionary containing the spriteID, colorOffset, and flag for an individual tile.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>column</td>
    <td>int</td>
    <td>The X position of the tile in the tilemap.</td>
  </tr>
  <tr>
    <td>row</td>
    <td>int</td>
    <td>The Y position of the tile in the tilemap.</td>
  </tr>
  <tr>
    <td>spriteID</td>
    <td>int?</td>
    <td>The sprite id to use for the tile.</td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int?</td>
    <td>Shift the color IDs by this value.</td>
  </tr>
  <tr>
    <td>flag</td>
    <td>int?</td>
    <td>An int value between -1 and 16 used for collision detection.</td>
  </tr>
  <tr>
    <td>flipH</td>
    <td>bool?</td>
    <td></td>
  </tr>
  <tr>
    <td>flipV</td>
    <td>bool?</td>
    <td></td>
  </tr>
</table>


### * * *


### TilemapSize ( width, height, clear )

This will return a vector representing the size of the tilemap in columns (x) and rows (y). Returns a vector of the tile maps size in tiles where x and y are the columns and rows of the tilemap.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int?</td>
    <td>An optional parameter for the width in tiles of the map.</td>
  </tr>
  <tr>
    <td>height</td>
    <td>int?</td>
    <td>An option parameter for the height in tiles of the map.</td>
  </tr>
  <tr>
    <td>clear</td>
    <td>bool</td>
    <td></td>
  </tr>
</table>


### * * *


### TotalSprites ( bool ignoreEmpty )

Returns the total number of sprites in the system.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>ignoreEmpty</td>
    <td>bool</td>
    <td>This is an optional value that defaults to true. </td>
  </tr>
</table>


### * * *


### UpdateTiles ( column, row, columns, ids, colorOffset, flag )

A helper method which allows you to update several tiles at once. 

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>column</td>
    <td>int</td>
    <td>Start column of the first tile to update. The 0 column is on the far left of the tilemap.</td>
  </tr>
  <tr>
    <td>row</td>
    <td>int</td>
    <td>Start row of the first tile to update. The 0 row is on the top of the tilemap.</td>
  </tr>
  <tr>
    <td>columns</td>
    <td>int</td>
    <td>The width of the area in tiles to update.</td>
  </tr>
  <tr>
    <td>ids</td>
    <td>int[]</td>
    <td>An array of sprite IDs to use for each tile being updated.</td>
  </tr>
  <tr>
    <td>colorOffset</td>
    <td>int?</td>
    <td>An optional color offset int value to be applied to each updated tile.</td>
  </tr>
  <tr>
    <td>flag</td>
    <td>int?</td>
    <td>An optional flag int value to be applied to each updated tile.</td>
  </tr>
</table>


#### * * *


### WriteSaveData ( key, value )

Allows you to save string data to the game file itself. This data persistent even after restarting a game.

#### Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>key</td>
    <td>string</td>
    <td>A string to use as the key for the data.</td>
  </tr>
  <tr>
    <td>value</td>
    <td>string</td>
    <td>A string representing the data to be saved.</td>
  </tr>
</table>



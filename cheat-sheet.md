# API Cheat Sheet

Pixel Vision 8 exposes a set of APIs through the `GameChip` that allows you to create your own games with. The `GameChip` helps tie together all of the chips to create a single entry point when building a game. These APIs are broken up into several groups revolving around input, rendering, audio, and file parsing. These APIs are available in both the C# and Lua implementations of Pixel Vision 8 allowing for porting between either language to be easier. That means if you prefer to sketch out a game in Lua, you can eventually port it to C# for better performance and access to lower level .net functionality as the scope of your game grows over time.

Below is a cheat sheet of the most common APIs used to make PV8 games.

### Color

These APIs manage system colors and the background color used to clear the display.

#### BackgroundColor()

The background color is used to fill the screen when clearing the display. You can use this method to read or update the background color at runtime. When calling `BackgroundColor()` without an argument, it returns the current background color as an int. You can pass in an optional int to update the background color by calling `BackgroundColor(0),` where `0` is any valid system color ID.

```lua
BackgroundColor ( id )
```

#### Color()

The `Color()` API allows you to read and update color values in the `ColorChip`. This API has two modes that require a color ID to work. By calling the method with just an ID, like `Color(0)`, it returns a HEX string for that color. If you supply an additional HEX string value, like `Color(0, "#FFFF00")`, you can change the color with the given ID.

```lua
Color ( id, value )
```



### Drawing

These APIs are in charge of copying pixel data to the display.

#### DrawRect()

The `DrawRect()` API allows you to display a rectangle with a fill color on the screen. Since this API uses `DrawPixels()`, rectangles can be drawn to the tilemap cache or sprite layers.

```lua
DrawRect ( x, y, width, height, color, drawMode )
```

#### DrawSprites()

The `DrawSprite()` API allows you to draw a single sprite to the display. Sprites represent individual collections of 8 x 8 blocks of pixel data. The display also has a limitation on how many sprites that can be on the screen at the same time. Each time you call `DrawSprite()`, the sprite counts against the total amount the display can render.

```lua
DrawSprite ( id, x, y, flipH, flipV, drawMode, colorOffset )
```

#### DrawSpriteBlock()

`DrawSpriteBlock()` is similar to DrawSprites except you define the first sprite (upper left corner) and the width x height (in sprites) to sample from sprite ram.

```lua
DrawSpriteBlock ( id, x, y, width, height, flipH, flipV, drawMode, colorOffset, onScreen, useScrollPos, bounds )
```

#### DrawSprites()

The `DrawSprites()` API makes it easier to draw a group of sprites to the display. Unlike the DrawSpriteBlock() API, you define the exact sprites you want to be drawn. While there is no limit on the size of the sprite group which can be rendered, it is important to note that each ID in the array still counts as an individual sprite.

```lua
DrawSprites ( ids, x, y, width, flipH, flipV, drawMode, colorOffset, onScreen, useScrollPos, bounds )
```

#### DrawText()

The` DrawText()` API allows you to render text to the display. Files ending with the `.font.png` extension are loaded by the `FontChip `and converted into character sprites. The `FontChip `stores these characters separately from `SpriteChip`’s own sprites.

```lua
DrawText ( text, x, y, drawMode, font, colorOffset, spacing )
```



### File IO

These APIs allow you to read and write save data to handle persistent game data.



#### ReadSaveData()

The `ReadSaveData()` API allows you to read saved data by supplying a key. If no matching key exists, "`undefined`" is returned.

```lua
ReadSaveData ( key, defaultValue )
```



#### WriteSaveData()

The `WriteSaveData()` API allows you to write saved data by supplying a key and value. Once saved, this data persists even after restarting a game.

```lua
WriteSaveData ( key, value )
```



### Input

These APIs handle input from the system’s controllers, keyboard, and mouse.



#### Button()

The main form of input for Pixel Vision 8 is the controller's buttons. You can get the current state of any button by calling the `Button()` method and supplying a button ID. There are optional parameters for specifying an `InputState` and the controller ID.

```lua
Button ( Buttons button, InputState state, int controllerID )
```



#### Key()

While the main forms of input for Pixel Vision 8 are the controllers, you can test for keyboard input by calling the `Key()` API. When this API is called, it returns the current state of that specific key.

```lua
Key ( key, state )
```



#### MouseButton()

Pixel Vision 8 supports mouse input. You can get the current state of the mouse's left (`0`) and right (`1`) buttons by calling `MouseButton()`API. In addition to supplying a button ID, you can also provide an option `InputState`.

```lua
MouseButton ( int button, InputState state )
```



#### MousePosition()

The `MousePosition()` API returns a Point for the mouse cursor's `X` and `Y` position. The mouse's `0`,`0` position is in the upper left-hand corner of the display and when the mouse is off-screen it will return `-1`. This value is read-only.

```lua
MousePosition ( )
```



### Lifecycle

The following functions are automatically called when your game is running.



#### Init()

This is called when a game first loads up.

```lua
Init()
```

#### Draw()

Draw() is called once per frame after the Update() has been completed. This is where all of your game's draw calls should take place such as clearing the display, drawing sprites, and pushing raw pixel data into the display.

```lua
Draw()
```

#### Update()

Update() is called once per frame at the beginning of the game loop. This is where you should put all non-visual game logic such as character position calculations, detecting input and performing updates to your animation system. The `timeDelta` is provided on each frame so you can calculate the difference in milliseconds since the last render took place.

```lua
Update( timeDelta )
```



### Music 

These APIs allow you to manage music in your game.

#### PauseSong()

The `PauseSong()` API toggles the current playback state of the sequencer. If the song is playing, it will pause. If the song is paused, it will play.

```lua
PauseSong ( )
```

#### PlaySong()

The `PlaySong()` API allows you to activate the `MusicChip`’s tracker to playback any of the songs stored in memory. A song is simply a collection of patterns. You can supply an optional parameter called `startAt` to tell the `MusicChip` which pattern to start the song at. 

```lua
PlaySong ( id, loop, startAt )
```

#### RewindSong()

The `RewindSong()` API allows you rewind the currently playing song to a specific position and pattern ID. Calling this API without any arguments will simply rewind the song to the beginning of the first pattern.

```lua
RewindSong ( position, patternID)
```

#### StopSong()

The `StopSong()` API will stop the currently playing song.

```lua
StopSong ( )
```



### Rendering

These APIs are in charge of managing what renders to the display.

#### Display()

The `Display()` method allows you to get the resolution of the display at run time. By default, this will return the visible screen area based on the overscan value set on the `DisplayChip`.

```lua
Display ( visible )
```

#### RedrawDisplay()

The `RedrawAPI()` allows you to execute both the `Clear()` and `DrawTilemap()` APIs in a single call. This is a simple helper function to make redrawing the display easier. If you need to supply additional arguments to either the `Clear()` or `DrawTilemap(`) APIs, then you’ll need to call each one independently without using `RedrawDisplay()`.

```lua
RedrawDisplay ( )
```

#### ScrollPosition()

You can scroll the tilemap by calling the `ScrollPosition()` API and supplying a new scroll `X` and `Y` position. By default, calling `ScrollPosition()` with no arguments returns a `Point` with the current scroll `X` and `Y` values. If you supply an `X` and `Y` value, it updates the tilemap's scroll position the next time you call the `DrawTilemap()` API.

```lua
ScrollPosition ( x, y )
```



### Sounds

These APIs allow you to play sound effects on specific audio channels.

#### PlaySound()

The `PlaySound()` API allows playing a single sound effect on a specific channel. The `SoundChip `has a limited number of active channels, so playing a sound effect on a channel where a sound is already playing will override it.

```lua
PlaySound ( id, channel )
```



#### Sound()

The `Sound()` API allows you to read raw sound data from the `SoundChip`. You need to provide a sound effect ID. If you supply the optional data argument, which is a comma-delimited string of sound effect property values, you’ll be able to update the sound effect.

```lua
Sound ( int id, string data )
```



#### StopSound()

Use `StopSound()` to stop any sound playing on a specific channel.

```lua
StopSound ( channel )
```



### Sprites

These APIs allow you to manage sprite pixel data and get the total amount of sprites in memory.



#### Sprite()

The `Sprite()` API allows you to read and write pixel data directly to the `SpriteChip`’s memory. Sprite pixel data is simply an array of color IDs. When calling the `Sprite()` with only an ID argument, you will get the sprite's pixel data. If you supply data, it will overwrite the sprite.

```lua
Sprite ( id, data )
```



####  TotalSprites()

The `TotalSprites()` API returns the total number of sprites in the `SpriteChip`. By supplying `true `for the `ignoreEmpty `parameter, it will only return sprites that contain pixel data.

```lua
TotalSprites ( bool ignoreEmpty )
```



### Tilemap

These APIs allow you work with tilemap data.

#### Flag()

The `Flag()` API allows you to quickly access just the flag value of a tile. This is useful when trying to calculate collision on the tilemap. By default, you can call this method with just a `column `and `row `position to return the flag value at that tile. If you supply a new value, it will be overridden on the tile.

```lua
Flag ( column, row, value )
```

#### RebuildTilemap()

The `RebuildTilemap()` API forces the tilemap to redraw the tilemap cache layer. Use this to clear any pixel data drawn on top of tiles in the tilemap cache layer.

```lua
RebuildTilemap ( )
```

#### Tile()

The `Tile()` API allows you to get the current sprite, color offset and flag values associated with a given tile ID. You can optionally supply your own values if you want to update the tile. 

```lua
Tile ( column, row, spriteID, colorOffset, flag, flipH, flipV )
```

#### TilemapSize()

The `TilemapSize()` API returns a `Point `representing the size of the tilemap in `columns `(`X`) and `rows` (`Y`). To find the size in pixels, you will need to multiply the returned `Point`’s `X` and `Y` values by the sprite size's `X` and `Y`. This method also allows you to resize the tilemap by passing in an optional new `Width` and `Height`.

```lua
TilemapSize ( width, height, clear )
```

#### UpdateTiles()

The `UpdateTiles()` API allows you to update the color offset and flag values of multiple tiles at once. Simply supply an array of tile IDs and the new tile’s color offset and a flag value. This helper method uses the `Tile()` API under the hood to update each tile, so any changes to a tile’s color offset will automatically force it to be redrawn to the tilemap cache layer.

```lua
UpdateTiles ( ids, column, row, width, colorOffset, flag )
```



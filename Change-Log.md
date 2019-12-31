Pixel Vision 8 and the Pixel Vision OS are constantly being updated based on the new feature backlog, bugs that need fixing and optimizing the underlying codebase. Because of this, the goal is to release new versions as often as possible. If you are new to Pixel Vision 8 or looking to understand what has changed since the last release, you can find the most recent changes below, broken down by the version number.

## Important Changes

There are some major API changes in this version that may impact reinstalling Pixel Vision OS on a previous install and how your games run. Here is a list of major changes and ways to migrate your existing games over to the latest version.

### Upgrading Pixel Vision OS

**Issue**- If you have a previous version of Pixel Vision OS you’ll get an error after booting into the Workspace Tool. This has to do with the fact that the `ReadMetaData()` API has now been changed to `ReadMetadata()`. This will impact the logic that checks if the Explorer Tool should prompt the user to upgrade to the newer OS.

**Fix**- Make sure to back up your entire Workspace, then boot up Pixel Vision 8 v0.9.7 while holding down the Shift key to enter safe mode. This will load up the OS Installer Tool. Check "clean install" then reinstall Pixel Vision OS. You’ll need to also reinstall your copy of the Pro Tools as well.

### Changes to Time Delta

**Issue** - When you run your games in Pixel Vision 8 v0.9.7, you may notice the timing is off. The game’s `Update()` now returns `timeDelta` as an `int` instead of a float which was used in previous versions.

**Fix**- If you are using the `timeDelta `in your game’s `Update()` function, add `timeDelta = timeDelta/1000` to the top of the `Update()` function which will convert the value back to a `float`. This should allow your game to run correctly until you have time to make the required adjustments to any `timeDelta `calculations.

### API Changes

Here is a complete list of the API changes that are new in v0.9.7:

* TotalSprites & TotalColors now default to false. Supplying true will return a total ignoring any empty sprites or colors.

* UpdateTiles API changed from:

    `UpdateTiles(int column, int row, int columns, int[] ids, int? colorOffset = null, int? flag = null)`

	to

    `UpdateTiles(int[] ids, int? colorOffset = null, int? flag = null)`

* `StopSound()` was added to the Lua APIs.
* `SpriteSize()` no longer accepts a width and height parameter since changing sprite sizes wasn’t supported reviously.
* Removed `Sprites()` API.
* Changed `DumpMetaData()` to  `ReadAllMetadata()` API
* Changed `ReadMetaData()` and `WriteMetaData()` to `ReadMetadata()` and `WriteMetadata()` respectively.
* Added `IsChannelPlaying()` to Lua API
* Remove `drawMode` parameter from `DrawTilemap()`. It now automatically selected the correct `drawMode` by default.
* Changed `ConvertCharacterToPixelData()` to `CharacterToPixelData()`
* Removed `PlayPattern()` and `PlayPatterns() `from the API.

## Latest Fixes
This is currently a beta release of Pixel Vision 8. You can now log bugs specific to Pixel Vision OS [here](https://github.com/PixelVision8/PixelVisionOS/issues) or to the core MonoGame Runner [here](https://github.com/PixelVision8/MonoGameRunner/issues). There is also a dedicated [Discord Server](https://discord.gg/pixelvision8) for community, help, and sharing work. Below are the issues that have been addressed in this release:

### SDK (v1.9.7)

* [TotalSprites and TotalColors should default to false](https://github.com/PixelVision8/PixelVisionRunner/issues/94)

* [Changing UpdateTiles to work with tileIDs, color offsets and flags values](https://github.com/PixelVision8/PixelVisionRunner/issues/90)

* [Changing TotalSprites API to default to false](https://github.com/PixelVision8/PixelVisionRunner/issues/89)

* [Add StopSound to the Lua API](https://github.com/PixelVision8/PixelVisionRunner/issues/87)

* [Remove optional width and height from SpriteSize()](https://github.com/PixelVision8/PixelVisionRunner/issues/86)

* [Removed Sprites() API](https://github.com/PixelVision8/PixelVisionRunner/issues/85)

* [Change DumpMetaData() api to ReadAllMetadata()](https://github.com/PixelVision8/PixelVisionRunner/issues/81)

* [Change ReadMetaData() api to ReadMetadata()](https://github.com/PixelVision8/PixelVisionRunner/issues/79)

* [Add IsChannelPlaying to the Lua APIs](https://github.com/PixelVision8/PixelVisionRunner/issues/76)

* [Make sure NewPoint and NewRect are part of the C# API](https://github.com/PixelVision8/PixelVisionRunner/issues/75)

* [Removed draw mode option from DrawTilemap](https://github.com/PixelVision8/PixelVisionRunner/issues/74)

* [Fix template header wrapping](https://github.com/PixelVision8/PixelVisionRunner/issues/73)

* [Changed ConvertCharacterToPixelData to CharacterToPixelData](https://github.com/PixelVision8/PixelVisionRunner/issues/72)

* [Error tool doesn't display text in Game Runner](https://github.com/PixelVision8/PixelVisionRunner/issues/70)

* [Add boot to game runner](https://github.com/PixelVision8/PixelVisionRunner/issues/69)

* [Text draw calls are not capped by sprite draw limit](https://github.com/PixelVision8/PixelVisionRunner/issues/68)

* [Need to escape linux launch path](https://github.com/PixelVision8/PixelVisionRunner/issues/49)

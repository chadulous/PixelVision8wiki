# Change Log

Pixel Vision 8 and the Pixel Vision OS are constantly being updated based on the new feature backlog, bugs that need fixing and optimizing the underlying code base. Because of this, the goal is to release new versions as often as possible. If you are new to Pixel Vision 8 or looking to understand what has changed since the last release, you can find all of the changes below, broken down by the version number.

## V0.9.6 Beta

This marks the alpha release of Pixel Vision 8. You can now log bugs specific to Pixel Vision OS [here](https://github.com/PixelVision8/PixelVisionOS/issues) or to the core MonoGame Runner [here](https://github.com/PixelVision8/MonoGameRunner/issues). There is also a dedicated [Discord Server](https://discord.gg/pixelvision8) for community, help, and sharing work. Below are the issues that have been addressed in this release:

### Pixel Vision OS (v2.6.0)

* [Build size check is not correctly calculating the size](https://github.com/PixelVision8/PixelVisionOS/issues/375)

* [Tilemap should show hand cursor over scroll bars](https://github.com/PixelVision8/PixelVisionOS/issues/417)

* [Need option to turn off system sounds](https://github.com/PixelVision8/PixelVisionOS/issues/435)

* [Sound preview not working](https://github.com/PixelVision8/PixelVisionOS/issues/433)

* [Paste is not working in SFX tool](https://github.com/PixelVision8/PixelVisionOS/issues/432)

* [Default game doesn't work if map is set to 256 tiles wide](https://github.com/PixelVision8/PixelVisionOS/issues/429)

* [Image Preview tool not loading](https://github.com/PixelVision8/PixelVisionOS/issues/430)

* [Music tool doesn't retain state](https://github.com/PixelVision8/PixelVisionOS/issues/372)

* [Debug color mode is not saved correctly](https://github.com/PixelVision8/PixelVisionOS/issues/385)

* [If game runs with no draw it's black but should default to 1st color](https://github.com/PixelVision8/PixelVisionOS/issues/418)

* [Remove run command from tools if it's not a valid game](https://github.com/PixelVision8/PixelVisionOS/issues/428)

* [Add keyboard support to music tool](https://github.com/PixelVision8/PixelVisionOS/issues/50)

* [Need to make sure tools use arrow keys and not buttons](https://github.com/PixelVision8/PixelVisionOS/issues/427)

* [Need to display a warning when the chip is locked](https://github.com/PixelVision8/PixelVisionOS/issues/383)

* [Need to add warning to upgrade OS](https://github.com/PixelVision8/PixelVisionOS/issues/425)

* [Settings action keys not mapped on initial install](https://github.com/PixelVision8/PixelVisionOS/issues/419)

* [When pasting in similar name file, ask to overwrite](https://github.com/PixelVision8/PixelVisionOS/issues/361)

* [Moving a child folder of the same name up a directory replaces the parent](https://github.com/PixelVision8/PixelVisionOS/issues/394)

* [Check if valid game before running](https://github.com/PixelVision8/PixelVisionOS/issues/384)

* [Chip editor needs a way to lock down specs based on build](https://github.com/PixelVision8/PixelVisionOS/issues/386)

* [Error building with empty info.json file](https://github.com/PixelVision8/PixelVisionOS/issues/392)

* [Need to fix disk order](https://github.com/PixelVision8/PixelVisionOS/issues/413)

* [Draw and Tune should validate folder based on their respective files](https://github.com/PixelVision8/PixelVisionOS/issues/421)

* [Setting's tool crashes when remapping keys](https://github.com/PixelVision8/PixelVisionOS/issues/379)

* [Need to clear icon selection when clicking on window bg](https://github.com/PixelVision8/PixelVisionOS/issues/400)

* [Missing wait cursor animation frame](https://github.com/PixelVision8/PixelVisionOS/issues/410)

* [Disable mute on the toolbar while wait cursor is active](https://github.com/PixelVision8/PixelVisionOS/issues/411)

* [New file options are missing](https://github.com/PixelVision8/PixelVisionOS/issues/416)

* [Tilemap input field highlight is the mask color](https://github.com/PixelVision8/PixelVisionOS/issues/408)

* [Empty json tilemap can't be parsed](https://github.com/PixelVision8/PixelVisionOS/issues/415)

* [Need to clean up loading error screen in tilemap tool](https://github.com/PixelVision8/PixelVisionOS/issues/414)

* [Rename file in folder to same name and it replaces it](https://github.com/PixelVision8/PixelVisionOS/issues/387)

* [Renaming info.json doesn't add the correct extension](https://github.com/PixelVision8/PixelVisionOS/issues/381)

* [Need to highlight folder mouse is over when dragging](https://github.com/PixelVision8/PixelVisionOS/issues/308)

* [Input fields are not calculating width correctly for text input](https://github.com/PixelVision8/PixelVisionOS/issues/409)

* [Input field triggers edit on mouse release over](https://github.com/PixelVision8/PixelVisionOS/issues/39)

* [Text editor throws error when trying to type out of bounds](https://github.com/PixelVision8/PixelVisionOS/issues/355)

* [Installer icon shouldn't be able to be dragged](https://github.com/PixelVision8/PixelVisionOS/issues/402)

* [Add wait cursor when long file action is taking place](https://github.com/PixelVision8/PixelVisionOS/issues/401)

* [Installer needs to show wait cursor when running](https://github.com/PixelVision8/PixelVisionOS/issues/407)

* [Need to move SpriteBuilder folder validation into SpriteTool](https://github.com/PixelVision8/PixelVisionOS/issues/406)

* [Need to correctly block back button](https://github.com/PixelVision8/PixelVisionOS/issues/396)

* [Need to disable file creation options based on if the template exists](https://github.com/PixelVision8/PixelVisionOS/issues/395)

* [Move project template path to the bios](https://github.com/PixelVision8/PixelVisionOS/issues/398)

* [Fix issue with saving current path on shutdown](https://github.com/PixelVision8/PixelVisionOS/issues/397)

* [Moving a lot of files needs to show a progress bar](https://github.com/PixelVision8/PixelVisionOS/issues/363)

* [Trash is not being refreshed when full](https://github.com/PixelVision8/PixelVisionOS/issues/393)

* [Need to look into why a game can't run without colors.png](https://github.com/PixelVision8/PixelVisionOS/issues/391)

* [Need to fix ValidateGameInDir to look for data, info and code](https://github.com/PixelVision8/PixelVisionOS/issues/390)

* [Workspace Tool needs to use WorkspacePath](https://github.com/PixelVision8/PixelVisionOS/issues/389)

* [Fix issue where System, Lib, and Tool folders don't get correct icon](https://github.com/PixelVision8/PixelVisionOS/issues/388)

* [Can't create a folder on a disk](https://github.com/PixelVision8/PixelVisionOS/issues/376)

* [Create special OS installer](https://github.com/PixelVision8/PixelVisionOS/issues/377)

* [Flag picker doesn't restore last selection when switching layers](https://github.com/PixelVision8/PixelVisionOS/issues/369)

### SDK (v1.9.6)

* [Add disk invalidation to optimize calls to total disks](https://github.com/PixelVision8/PixelVision8/issues/64)

* [Clamp dimensions of TextureData](https://github.com/PixelVision8/PixelVision8/issues/65)

* [C# runner doesn't reset sprite counter](https://github.com/PixelVision8/PixelVision8/issues/57)

* [Need "safe mode" when booting up](https://github.com/PixelVision8/PixelVision8/issues/54)

* [Need to disable disks from bios](https://github.com/PixelVision8/PixelVision8/issues/62)

## V0.9.5 Beta

Below are the issues that have been addressed in this release:

### Pixel Vision OS (v2.5.0)

* [Build size check is not correctly calculating the size](https://github.com/PixelVision8/PixelVisionOS/issues/375)

* [Setting tile to Flag 8 doesn't save correctly](https://github.com/PixelVision8/PixelVisionOS/issues/373)

* [Show OS in Workspace](https://github.com/PixelVision8/PixelVisionOS/issues/60)

* [Changes to disk are not saving](https://github.com/PixelVision8/PixelVisionOS/issues/78)

* [Need to figure out a way to include Music Tool in "free" OS](https://github.com/PixelVision8/PixelVisionOS/issues/115)

* [All game editor tools should launch game with CTRL + R](https://github.com/PixelVision8/PixelVisionOS/issues/371)

* [Need to display flag value in mouse over message](https://github.com/PixelVision8/PixelVisionOS/issues/370)

* [Ejecting second disk throws error](https://github.com/PixelVision8/PixelVisionOS/issues/360)

* [Using tile fill on small maps doesn't reset the wait cursor](https://github.com/PixelVision8/PixelVisionOS/issues/353)

* [Tilemap changes sprites in flag mode with arrow keys](https://github.com/PixelVision8/PixelVisionOS/issues/366)

* [Changing the sprite with the arrows in the picker shows a preview when it shouldn't](https://github.com/PixelVision8/PixelVisionOS/issues/352)

* [Render issue when scrolling in text editor](https://github.com/PixelVision8/PixelVisionOS/issues/277)

* [Need to test out CPS preview with more than 8 colors](https://github.com/PixelVision8/PixelVisionOS/issues/344)

* [Sprite optimization not invalidating data](https://github.com/PixelVision8/PixelVisionOS/issues/287)

* [Canvas preview color shows mask on last color](https://github.com/PixelVision8/PixelVisionOS/issues/249)

* [Sprite tool should hide unused colors in picker](https://github.com/PixelVision8/PixelVisionOS/issues/125)

* [Selecting draw tool in palette mode doesn't select first color](https://github.com/PixelVision8/PixelVisionOS/issues/359)

* [Rename sprite didn't add .png to end of filename](https://github.com/PixelVision8/PixelVisionOS/issues/343)

* [BG color should never be out of bounds](https://github.com/PixelVision8/PixelVisionOS/issues/365)

* [Need to show message that a file has been copied to the clipboard](https://github.com/PixelVision8/PixelVisionOS/issues/364)

* [Restarting the sprite tool should restore last sprite size](https://github.com/PixelVision8/PixelVisionOS/issues/358)

* [Flip H and V should change the pixel data](https://github.com/PixelVision8/PixelVisionOS/issues/334)

* [Need to clear sprite cache when drawing](https://github.com/PixelVision8/PixelVisionOS/issues/333)

* [Font tool renames file if just editing pixels](https://github.com/PixelVision8/PixelVisionOS/issues/356)

* [Canvas is not updated correctly when first loaded](https://github.com/PixelVision8/PixelVisionOS/issues/357)

* [Clean up all the templates and the chip builder settings](https://github.com/PixelVision8/PixelVisionOS/issues/275)

* [Update BG color flag when moving between pages](https://github.com/PixelVision8/PixelVisionOS/issues/286)

* [Optimize color picker renderer](https://github.com/PixelVision8/PixelVisionOS/issues/285)

* [Can't add system color in palette mode](https://github.com/PixelVision8/PixelVisionOS/issues/111)

* [Last color on page shows error](https://github.com/PixelVision8/PixelVisionOS/issues/247)

* [Adding color breaks color picker drag state](https://github.com/PixelVision8/PixelVisionOS/issues/248)

* [Hold down shift to select all libs in build tool](https://github.com/PixelVision8/PixelVisionOS/issues/348)

* [Need to replace the about text are with the new text area components](https://github.com/PixelVision8/PixelVisionOS/issues/312)

* [Font pen tool is buggy](https://github.com/PixelVision8/PixelVisionOS/issues/38)

* [Support changing font name](https://github.com/PixelVision8/PixelVisionOS/issues/354)

* [Need to show wait cursor in Tilemap editor](https://github.com/PixelVision8/PixelVisionOS/issues/351)

* [Move clean install to a modal](https://github.com/PixelVision8/PixelVisionOS/issues/154)

* [Fix scrolling in build tool](https://github.com/PixelVision8/PixelVisionOS/issues/349)

* [Need to disable build options when not available](https://github.com/PixelVision8/PixelVisionOS/issues/279)

* [Delete color-map in project if palette mode is false](https://github.com/PixelVision8/PixelVisionOS/issues/350)

* [Chip editor doesn't clear all colors](https://github.com/PixelVision8/PixelVisionOS/issues/284)

* [Song editor input field loses selection when done editing](https://github.com/PixelVision8/PixelVisionOS/issues/325)

* [Input field cursor issue](https://github.com/PixelVision8/PixelVisionOS/issues/329)

* [Can't copy and paste palette colors between pages](https://github.com/PixelVision8/PixelVisionOS/issues/345)

* [Text Editor scrolling is not working correctly at edges](https://github.com/PixelVision8/PixelVisionOS/issues/330)

* [Switching from eyedropper to pen doesn't update color](https://github.com/PixelVision8/PixelVisionOS/issues/338)

* [Need to recalculate color CPS in canvas when switching sizes](https://github.com/PixelVision8/PixelVisionOS/issues/339)

* [Hi .. any chance we could get the name of the chip we are hovering over in the hint text ?](https://github.com/PixelVision8/PixelVisionOS/issues/336)

* [Need to make sure system templates are correct](https://github.com/PixelVision8/PixelVisionOS/issues/342)

* [Swapping palette colors doesn't work](https://github.com/PixelVision8/PixelVisionOS/issues/340)

* [Changing color modes doesn't convert sprites to greyscale colormap space](https://github.com/PixelVision8/PixelVisionOS/issues/341)

### SDK (v1.9.5)

* [Make ConvertTextToSprites() private](https://github.com/PixelVision8/PixelVision8/issues/60)

* [MetaData changes don't carry over between resets](https://github.com/PixelVision8/PixelVision8/issues/59)

* [Add gif capture back in](https://github.com/PixelVision8/PixelVision8/issues/37)

* [Fix font parsing](https://github.com/PixelVision8/PixelVision8/issues/50)

* [C# Runner requires hard-coded scaling to scale display](https://github.com/PixelVision8/PixelVision8/issues/55)

* [Fonts need separate memory space](https://github.com/PixelVision8/PixelVision8/issues/28)

* [Modify PaletteOffset method to support a second shift option](https://github.com/PixelVision8/PixelVision8/issues/56)

## V0.9.4 Beta

Below are the issues that have been addressed in this release:

### Pixel Vision OS (v2.4.0)

* [Color preview breaks in palette mode](https://github.com/PixelVision8/PixelVisionOS/issues/266) 

* [Text editor loses selection when scrolling](https://github.com/PixelVision8/PixelVisionOS/issues/331)

* [Text editor is not drawing line numbers correctly](https://github.com/PixelVision8/PixelVisionOS/issues/327)

* [If text editor is not in code mode, disable highlighting](https://github.com/PixelVision8/PixelVisionOS/issues/314)

* [Change name pop-up crashes when hitting enter](https://github.com/PixelVision8/PixelVisionOS/issues/303)

* [Make sure input field validation is working correctly](https://github.com/PixelVision8/PixelVisionOS/issues/306)

* [Hex input for color tool doesn't disable correctly](https://github.com/PixelVision8/PixelVisionOS/issues/302)

* [Need to move code highlighter to pro](https://github.com/PixelVision8/PixelVisionOS/issues/297)

* [New input field needs to cap number values](https://github.com/PixelVision8/PixelVisionOS/issues/293)

* [Drive should only show PV8 stripes when bootabl](https://github.com/PixelVision8/PixelVisionOS/issues/178)

* [New input field input issues](https://github.com/PixelVision8/PixelVisionOS/issues/294)

* [Need to clean up vertical scrolling in text editor](https://github.com/PixelVision8/PixelVisionOS/issues/322)

* [New input cursor issue on first edit](https://github.com/PixelVision8/PixelVisionOS/issues/295)

* [Text editor doesn't clear selection when releasing mouse out of field](https://github.com/PixelVision8/PixelVisionOS/issues/328)

* [Need to limit page down in text editor from going past the last line](https://github.com/PixelVision8/PixelVisionOS/issues/313)

* [Need to add API to the highlighter](https://github.com/PixelVision8/PixelVisionOS/issues/305)

* [Keep text editor from scrolling past bottom when selecting with mouse](https://github.com/PixelVision8/PixelVisionOS/issues/304)

* [Need to make sure all tools have the correct text field colors](https://github.com/PixelVision8/PixelVisionOS/issues/296)

* [Code editor is not setting the invalidate flag when editing](https://github.com/PixelVision8/PixelVisionOS/issues/326)

* [Input fields are not correctly padding numbers](https://github.com/PixelVision8/PixelVisionOS/issues/298)

* [Need to add support for scrolling back into Text Area](https://github.com/PixelVision8/PixelVisionOS/issues/299)

* [New input area for sound channels in chip editor out of sync](https://github.com/PixelVision8/PixelVisionOS/issues/301)

* [Sprite tool palette mode using first color as mask](https://github.com/PixelVision8/PixelVisionOS/issues/323)

* [Can't select sprite editor id text field](https://github.com/PixelVision8/PixelVisionOS/issues/310)

* [Music tool sound build is broken since it relies on old text field component](https://github.com/PixelVision8/PixelVisionOS/issues/316)

* [Quitting map tool throws out of bounds error](https://github.com/PixelVision8/PixelVisionOS/issues/324)

* [Palettes are not loading/saving correctly](https://github.com/PixelVision8/PixelVisionOS/issues/292)

* [Music tool only exports the first song](https://github.com/PixelVision8/PixelVisionOS/issues/320)

* [Font name text not correctly aligned in the font editor](https://github.com/PixelVision8/PixelVisionOS/issues/318)

* [Text area and fields are not showing tooltip](https://github.com/PixelVision8/PixelVisionOS/issues/315)

* [Flag flood fill doesn't doesn't use the currently selected flag value](https://github.com/PixelVision8/PixelVisionOS/issues/262)

* [Double click to edit color](https://github.com/PixelVision8/PixelVisionOS/issues/280)

* [Opening a model doesn't capture focus](https://github.com/PixelVision8/PixelVisionOS/issues/281)

* [Convert to palette mode breaks sprite picker display](https://github.com/PixelVision8/PixelVisionOS/issues/274)

* [Need to clean up color picker dragging](https://github.com/PixelVision8/PixelVisionOS/issues/272)

* [Color picker over state blocks BG icon](https://github.com/PixelVision8/PixelVisionOS/issues/246)

* [Color picker selection renders over drop down menu](https://github.com/PixelVision8/PixelVisionOS/issues/245)

* [Fix rendering issue in text editor](https://github.com/PixelVision8/PixelVisionOS/issues/269)

* [Color picker drag and drop throws out of bounds error](https://github.com/PixelVision8/PixelVisionOS/issues/273)

* [Export tilemap as an image](https://github.com/PixelVision8/PixelVisionOS/issues/271)

* [Need to support tilemaps smaller than the viewport](https://github.com/PixelVision8/PixelVisionOS/issues/268)

* [Sprite/Tilemap tool shortcut buttons are trigger when Ctrl is pressed](https://github.com/PixelVision8/PixelVisionOS/issues/265)

* [Flip vertical rollover button issue in sprite tool](https://github.com/PixelVision8/PixelVisionOS/issues/264)

* [Tilemap cursor doesn't update correctly when switching tools via keyboard](https://github.com/PixelVision8/PixelVisionOS/issues/250)

* [Black screen in Famisystem template instead of drawing text](https://github.com/PixelVision8/PixelVisionOS/issues/176)

* [Should only draw canvas when invalid](https://github.com/PixelVision8/PixelVisionOS/issues/263)

* [Tilemap draw tool doesn't pick currently selected tile](https://github.com/PixelVision8/PixelVisionOS/issues/251)

* [Tilemap background color doesn't disable in flag mode](https://github.com/PixelVision8/PixelVisionOS/issues/252)

* [Need to clear tile selection when switching to flag layer](https://github.com/PixelVision8/PixelVisionOS/issues/253)

* [Switching to selection tool from eraser in tilemap tool breaks preview](https://github.com/PixelVision8/PixelVisionOS/issues/254)

* [Tilemap editor scrolling becomes miss-aligned](https://github.com/PixelVision8/PixelVisionOS/issues/255)

* [Tile preview color offset is wrong in palette mode](https://github.com/PixelVision8/PixelVisionOS/issues/257)

* [Clearing sprite doesn't update sprite preveiw](https://github.com/PixelVision8/PixelVisionOS/issues/259)

* [Optimizing sprites doesn't update the preview window](https://github.com/PixelVision8/PixelVisionOS/issues/261)

* [Need a way to apply color offset to tile in palette mode](https://github.com/PixelVision8/PixelVisionOS/issues/258)

* [Tilemap flood fill doesn't draw all tiles](https://github.com/PixelVision8/PixelVisionOS/issues/256)

* [Cursor not resetting correctly](https://github.com/PixelVision8/PixelVisionOS/issues/3)

* [Add disabled background to Tilemap Tool](https://github.com/PixelVision8/PixelVisionOS/issues/22)

* [Need to make transparent palette colors clearer in canvas](https://github.com/PixelVision8/PixelVisionOS/issues/103)

* [Tilemap editor doesn't draw empty tiles](https://github.com/PixelVision8/PixelVisionOS/issues/234)

* [Need a color per sprite preview in canvas](https://github.com/PixelVision8/PixelVisionOS/issues/239)

* [Need to scroll when dragging sprite](https://github.com/PixelVision8/PixelVisionOS/issues/242)

* [Selecting sprite doesn't scroll to the right position](https://github.com/PixelVision8/PixelVisionOS/issues/235)

* [When dragging sprite in picker, snap to grid](https://github.com/PixelVision8/PixelVisionOS/issues/241)

* [Need to keep sprite drag from triggering canvas save](https://github.com/PixelVision8/PixelVisionOS/issues/243)

* [Add undo/redo to font tool](https://github.com/PixelVision8/PixelVisionOS/issues/244)

* [Tilemap.png file should open in Image Preview Tool](https://github.com/PixelVision8/PixelVisionOS/issues/240)

* [Sprite editor tool shortcuts](https://github.com/PixelVision8/PixelVisionOS/issues/236)

* [Sprite editor needs undo/redo](https://github.com/PixelVision8/PixelVisionOS/issues/237)

* [Need color per sprite preview](https://github.com/PixelVision8/PixelVisionOS/issues/238)

* [Empty sound plays but doesn't let you edit it](https://github.com/PixelVision8/PixelVisionOS/issues/228)

* [Wav Sample doesn't play on "Any" channel](https://github.com/PixelVision8/PixelVisionOS/issues/231)

* [Square wave panel is not enabled correctly](https://github.com/PixelVision8/PixelVisionOS/issues/229)

* [Enable loading SFX from wav file](https://github.com/PixelVision8/PixelVisionOS/issues/216)

* [Color picker color space doesn't render on second time](https://github.com/PixelVision8/PixelVisionOS/issues/230)

* [Empty song patterns should not show 00](https://github.com/PixelVision8/PixelVisionOS/issues/208)

* [Move undo/redo to the menu](https://github.com/PixelVision8/PixelVisionOS/issues/221)

* [Need to add channel selector to sound tool](https://github.com/PixelVision8/PixelVisionOS/issues/219)

* [Need to make sure current selection filename is unique](https://github.com/PixelVision8/PixelVisionOS/issues/227)

* [Wave selector needs to reflect channel type](https://github.com/PixelVision8/PixelVisionOS/issues/220)

* [Need to limit built in shortcuts to numbers only](https://github.com/PixelVision8/PixelVisionOS/issues/15)

* [Tilemap.png should launch Tilemap Tool if .json doesn't exist](https://github.com/PixelVision8/PixelVisionOS/issues/77)

* [Gif files should show the correct icon](https://github.com/PixelVision8/PixelVisionOS/issues/226)

* [Shortcut font not displaying](https://github.com/PixelVision8/PixelVisionOS/issues/224)

* [Need to wire up volume in Music Tool](https://github.com/PixelVision8/PixelVisionOS/issues/210)

* [Need a way to select a channel wave](https://github.com/PixelVision8/PixelVisionOS/issues/222)

* [Display wav in music tool](https://github.com/PixelVision8/PixelVisionOS/issues/225)

* [Dragging icons should always be on top](https://github.com/PixelVision8/PixelVisionOS/issues/218)

* [Disabel automatic bios saving for system configuration](https://github.com/PixelVision8/PixelVisionOS/issues/172)

* [Play pattern button rewinds to beginning of song](https://github.com/PixelVision8/PixelVisionOS/issues/215)

* [Music Tool (v 0.9.3 Mac)- Index was outside the bounds](https://github.com/PixelVision8/PixelVisionOS/issues/150)

* [Need to limit number of songs to 10](https://github.com/PixelVision8/PixelVisionOS/issues/194)

* [Need to limit song pattern input field to total pattern count](https://github.com/PixelVision8/PixelVisionOS/issues/203)

* [Need a way to select the song's pattern](https://github.com/PixelVision8/PixelVisionOS/issues/204)

* [Playing a song doesn't work](https://github.com/PixelVision8/PixelVisionOS/issues/205)

* [Change pattern when song is playing](https://github.com/PixelVision8/PixelVisionOS/issues/206)

* [After playing a song, need to disable input arrows correctly](https://github.com/PixelVision8/PixelVisionOS/issues/211)

* [New project doesn't have song end marker](https://github.com/PixelVision8/PixelVisionOS/issues/212)

* [Need to remove pattern name from Music Editor](https://github.com/PixelVision8/PixelVisionOS/issues/214)

* [Need to be able to export SFX as .wav](https://github.com/PixelVision8/PixelVisionOS/issues/18)

* [Up directory icon becomes unresponsive](https://github.com/PixelVision8/PixelVisionOS/issues/202)

* [Disk icon now showing up correctly](https://github.com/PixelVision8/PixelVisionOS/issues/199)

* [Opening disk from folder should mount it](https://github.com/PixelVision8/PixelVisionOS/issues/213)

* [Need to create a disk tool](https://github.com/PixelVision8/PixelVisionOS/issues/179)

* [Installer needs a way to reboot the system](https://github.com/PixelVision8/PixelVisionOS/issues/163)

* [Can't select Run or Up Directory icons in Explorer](https://github.com/PixelVision8/PixelVisionOS/issues/200)

* [Context menu not correct when opening new directory](https://github.com/PixelVision8/PixelVisionOS/issues/198)

* [Add CRT shader](https://github.com/PixelVision8/PixelVisionOS/issues/169)

* [Need to implement ordinal sorting for file system](https://github.com/PixelVision8/PixelVisionOS/issues/197)

* [Icon disappears on left side of the screen when dragging](https://github.com/PixelVision8/PixelVisionOS/issues/196)

* [Need to fix issue with file drag delay](https://github.com/PixelVision8/PixelVisionOS/issues/188)

* [Shouldn't be able to drag folder on top of itself](https://github.com/PixelVision8/PixelVisionOS/issues/195)

* [Block folder from being copied into itself](https://github.com/PixelVision8/PixelVisionOS/issues/191)

* [Run game from text editor](https://github.com/PixelVision8/PixelVisionOS/issues/192)

* [Hide code lines when not editing code](https://github.com/PixelVision8/PixelVisionOS/issues/193)

* [Folder copy and paste is broken](https://github.com/PixelVision8/PixelVisionOS/issues/175)

* [Look for system folder](https://github.com/PixelVision8/PixelVisionOS/issues/174)

* [Need to add drag and drop support](https://github.com/PixelVision8/PixelVisionOS/issues/84)

* [Move C# workspace methods over to Lua](https://github.com/PixelVision8/PixelVisionOS/issues/183)

* [Issue renaming files](https://github.com/PixelVision8/PixelVisionOS/issues/189)

* [Trash folder shouldn't test to validate game](https://github.com/PixelVision8/PixelVisionOS/issues/190)

* [Dragging files to trash should give them a unique name](https://github.com/PixelVision8/PixelVisionOS/issues/187)

* [Limit icons that can be dragged](https://github.com/PixelVision8/PixelVisionOS/issues/184)

* [Ejecting disks order](https://github.com/PixelVision8/PixelVisionOS/issues/186)

* [Install script should only work when on a disk](https://github.com/PixelVision8/PixelVisionOS/issues/185)

* [Lock filename when creating editor specific files](https://github.com/PixelVision8/PixelVisionOS/issues/182)

* [Disable menu mute when modal is active](https://github.com/PixelVision8/PixelVisionOS/issues/180)

* [Need to limit resolution scale base on display](https://github.com/PixelVision8/PixelVisionOS/issues/177)

* [Knob is not using hit rect property](https://github.com/PixelVision8/PixelVisionOS/issues/171)

* [Quitting sprite tool throws error](https://github.com/PixelVision8/PixelVisionOS/issues/170)

* [Need to create songs for the music chip/editor](https://github.com/PixelVision8/PixelVisionOS/issues/6)

* [Add logic to copy files from disk to drive in Installer Tool](https://github.com/PixelVision8/PixelVisionOS/issues/155)

* [Wire up info.json file to launch Build Tool](https://github.com/PixelVision8/PixelVisionOS/issues/165)

* [Create the build tool](https://github.com/PixelVision8/PixelVisionOS/issues/166)

* [Installer throws error when trying to display less lines of text in about](https://github.com/PixelVision8/PixelVisionOS/issues/164)

* [Change system folder icons](https://github.com/PixelVision8/PixelVisionOS/issues/167)

* [Info.json file needs a special icon](https://github.com/PixelVision8/PixelVisionOS/issues/168)

* [Installer throws error if there are less items than it can display](https://github.com/PixelVision8/PixelVisionOS/issues/162)

* [Installer doesn't show the correct total if items are deselected](https://github.com/PixelVision8/PixelVisionOS/issues/161)

* [Installer needs a way to reset the check values](https://github.com/PixelVision8/PixelVisionOS/issues/160)

* [Installer needs an option to edit the raw text file](https://github.com/PixelVision8/PixelVisionOS/issues/159)

* [Wire up Installer Tool's file scroller](https://github.com/PixelVision8/PixelVisionOS/issues/152)

* [Wire up installer tool's about message scrolling](https://github.com/PixelVision8/PixelVisionOS/issues/153)

* [Need to connect the install.txt to the Installer Tool](https://github.com/PixelVision8/PixelVisionOS/issues/156)

* [Fix flood fill when using shapes to clear](https://github.com/PixelVision8/PixelVisionOS/issues/158)

### SDK (v1.9.4)

* [Need API to quickly calculate the palette color offset](https://github.com/PixelVision8/PixelVision8/issues/45)

* [Need to fix disk count and Back()](https://github.com/PixelVision8/PixelVision8/issues/43)

* [Limit game history to not add existing game when reloading](https://github.com/PixelVision8/PixelVision8/issues/42)

* [Restore load history correctly](https://github.com/PixelVision8/PixelVision8/issues/40)

* [Clean up threading](https://github.com/PixelVision8/PixelVision8/issues/39)

* [Print doesn't work](https://github.com/PixelVision8/PixelVision8/issues/38)

* [Error ejecting disk](https://github.com/PixelVision8/PixelVision8/issues/34)

* [Need to expose the log calls via the Lua API](https://github.com/PixelVision8/PixelVision8/issues/31)

* [Add flip h/v to Canvas DrawSprite method](https://github.com/PixelVision8/PixelVision8/issues/27)

## V0.9.3 Beta

Below are the issues that have been addressed in this release:

### Pixel Vision OS (v2.3.0)

* [BG color shouldn't be set to mask color](https://github.com/PixelVision8/PixelVisionOS/issues/143)

* [Update new radio button design](https://github.com/PixelVision8/PixelVisionOS/issues/112)

* [Need to configure new chip template values](https://github.com/PixelVision8/PixelVisionOS/issues/139)

* [Add warning to color editor when same color exists](https://github.com/PixelVision8/PixelVisionOS/issues/147)

* [Need to add RGB color space picker to the color editor modal](https://github.com/PixelVision8/PixelVisionOS/issues/142)

* [Need to display system paths correctly in workspace explorer tool](https://github.com/PixelVision8/PixelVisionOS/issues/144)

* [Need to add total songs to chip editor](https://github.com/PixelVision8/PixelVisionOS/issues/121) 

* [Need to limit disks when workspace exists](https://github.com/PixelVision8/PixelVisionOS/issues/134) 

* [Need to expose song total in the Chip Editor](https://github.com/PixelVision8/PixelVisionOS/issues/131) 

* [Create menu option to lock specs](https://github.com/PixelVision8/PixelVisionOS/issues/140)

* [Chip editor doesn't update menu items based on state](https://github.com/PixelVision8/PixelVisionOS/issues/141)

* [Need to enable chip picker](https://github.com/PixelVision8/PixelVisionOS/issues/137)

* [Create chip editors for Tune/Draw](https://github.com/PixelVision8/PixelVisionOS/issues/52)

* [Need to expose total colors in Chip Editor](https://github.com/PixelVision8/PixelVisionOS/issues/132)

* [Disable input field when losing focus](https://github.com/PixelVision8/PixelVisionOS/issues/11)

* [Chip tool is not saving the custom graphics](https://github.com/PixelVision8/PixelVisionOS/issues/130)

* [Fix image preview sprites](https://github.com/PixelVision8/PixelVisionOS/issues/21)

* [Palette mode dictates the transparent color in Sprite Tool](https://github.com/PixelVision8/PixelVisionOS/issues/119) 

* [Add flip to sprite tool](https://github.com/PixelVision8/PixelVisionOS/issues/73)

* [Color Tool's eye dropper should ignore transparent colors](https://github.com/PixelVision8/PixelVisionOS/issues/129)

* [Reindexing colors is not mapping transparent correctly](https://github.com/PixelVision8/PixelVisionOS/issues/114)

* [Need to remove eraser in palette mode](https://github.com/PixelVision8/PixelVisionOS/issues/128)

* [Sprites are not saved correct when switching to palette Mode](https://github.com/PixelVision8/PixelVisionOS/issues/126)

* [Colors per sprite is not saved when adding colors to palette](https://github.com/PixelVision8/PixelVisionOS/issues/127)

* [128 color limitation in Sprite Tool](https://github.com/PixelVision8/PixelVisionOS/issues/110)

* [Need to fix Sprite Tool button tool tips](https://github.com/PixelVision8/PixelVisionOS/issues/124)

* [Copy, paste and delete palette colors not working](https://github.com/PixelVision8/PixelVisionOS/issues/92)

* [Color Tool isn't limiting pages based on specs](https://github.com/PixelVision8/PixelVisionOS/issues/113)

* [Fix color picker when total colors is less than 64](https://github.com/PixelVision8/PixelVisionOS/issues/122)

* [Delete color in direct color mode removes non-unique colors](https://github.com/PixelVision8/PixelVisionOS/issues/95)

* [Need to add BG marker to system color picker](https://github.com/PixelVision8/PixelVisionOS/issues/117)

* [Need to add color map mode to Color Tool](https://github.com/PixelVision8/PixelVisionOS/issues/99)

* [Set BG color from color tool](https://github.com/PixelVision8/PixelVisionOS/issues/107)

* [Color picker needs to display the color offset value](https://github.com/PixelVision8/PixelVisionOS/issues/120)

* [Need to add color offset to sprite preview](https://github.com/PixelVision8/PixelVisionOS/issues/118)

* [Disable Run if a project doesn't have code](https://github.com/PixelVision8/PixelVisionOS/issues/116)

* [See palette color ID](https://github.com/PixelVision8/PixelVisionOS/issues/93)

* [Switching to palette mode should remove all duplicate colors](https://github.com/PixelVision8/PixelVisionOS/issues/108)

* [New Sound and New Music generating blank JSON files](https://github.com/PixelVision8/PixelVisionOS/issues/80)

* [Malformed JSON in template](https://github.com/PixelVision8/PixelVisionOS/issues/106)

* [Need to save palette mode](https://github.com/PixelVision8/PixelVisionOS/issues/100)

* [UI breaks switching between color modes](https://github.com/PixelVision8/PixelVisionOS/issues/104)

* [Issues selecting when in color picker mode](https://github.com/PixelVision8/PixelVisionOS/issues/102)

* [Color picker issue in palette mode](https://github.com/PixelVision8/PixelVisionOS/issues/101)

* [Canvas not using correct color](https://github.com/PixelVision8/PixelVisionOS/issues/98)

* [Sprite Editor needs to support palette mode](https://github.com/PixelVision8/PixelVisionOS/issues/94)

* [Dragging colors to palette doesn't work](https://github.com/PixelVision8/PixelVisionOS/issues/91)

* [Can't reorder palette colors](https://github.com/PixelVision8/PixelVisionOS/issues/90)

* [Palette pages are off](https://github.com/PixelVision8/PixelVisionOS/issues/89)

* [Palette's first page is not selected](https://github.com/PixelVision8/PixelVisionOS/issues/88)

* [Add support for palettes](https://github.com/PixelVision8/PixelVisionOS/issues/87)

* [Can't run disks from disks](https://github.com/PixelVision8/PixelVisionOS/issues/85)

* [Need to show .pv8 files as disks](https://github.com/PixelVision8/PixelVisionOS/issues/83)

* [Disks are not saving to the bios](https://github.com/PixelVision8/PixelVisionOS/issues/86)

### MonoGame Runner (v0.9.3)

* [User bios isn't loading correctly](https://github.com/PixelVision8/MonoGameRunner/issues/17)

* [Ejecting .pv8 disk crashes runner](https://github.com/PixelVision8/MonoGameRunner/issues/18)

### SDK (v1.9.1)

* [Make Pixel Vision 8's 16 color palette the default colors in the Color Chip](https://github.com/PixelVision8/SDK/issues/24)

* [Remove pages from ColorChip](https://github.com/PixelVision8/SDK/issues/23)

## V0.9.2 Beta

Below are the issues that have been addressed in this release:

### Pixel Vision OS (v2.2.0)

* [Remove extra pixels from palette window](https://github.com/PixelVision8/PixelVisionOS/issues/71) 

* [Show all colors in direct color mode](https://github.com/PixelVision8/PixelVisionOS/issues/69)

* [Enable menu items by name](https://github.com/PixelVision8/PixelVisionOS/issues/66)

* [Backspace deletes 2 characters](https://github.com/PixelVision8/PixelVisionOS/issues/64)

* [Increase delay for scaling shortcuts in boot](https://github.com/PixelVision8/PixelVisionOS/issues/57)

* [Need to combine rename/new file modals bug](https://github.com/PixelVision8/PixelVisionOS/issues/56)

* [Build message is empty bug](https://github.com/PixelVision8/PixelVisionOS/issues/79)

### MonoGame Runner (v0.9.2)

* [Seeing InvalidOpertionException when loading .pv8 game](https://github.com/PixelVision8/MonoGameRunner/issues/16)

## V0.9.1 Beta

Below are the issues that have been addressed in this release:

### Pixel Vision OS (v2.1.0)

* [Need to wire up music tool menu](https://github.com/PixelVision8/PixelVisionOS/issues/54)

* [Need to force uppercase for notes](https://github.com/PixelVision8/PixelVisionOS/issues/48)

* [Note field should allow empty value](https://github.com/PixelVision8/PixelVisionOS/issues/51)

* [Need to add track mute checkbox](https://github.com/PixelVision8/PixelVisionOS/issues/41)

* [Need to wire up track mute checkbox](https://github.com/PixelVision8/PixelVisionOS/issues/45)

* [Instrument not changing](https://github.com/PixelVision8/PixelVisionOS/issues/44)

* [Need to clean up the Tilemap Tool](https://github.com/PixelVision8/PixelVisionOS/issues/37)

* [Issue naming new project](https://github.com/PixelVision8/PixelVisionOS/issues/46)

* [Music note field not working](https://github.com/PixelVision8/PixelVisionOS/issues/42)

* [Music Tool stepper issue](https://github.com/PixelVision8/PixelVisionOS/issues/49)

* [Clicking on empty track makes noise](https://github.com/PixelVision8/PixelVisionOS/issues/47)

* [Issue playing Music Demo](https://github.com/PixelVision8/PixelVisionOS/issues/25)

* [Wire up song generator config fields](https://github.com/PixelVision8/PixelVisionOS/issues/40)

* [Sound history not working](https://github.com/PixelVision8/PixelVisionOS/issues/1)

* [Gun SFX template is not working](https://github.com/PixelVision8/PixelVisionOS/issues/17)

* [Fix wave buttons](https://github.com/PixelVision8/PixelVisionOS/issues/29)

* [Knobs disappear with modals](https://github.com/PixelVision8/PixelVisionOS/issues/34)

* [Chip editor tray issues](https://github.com/PixelVision8/PixelVisionOS/issues/36)

* [New file dialog names are wrong](https://github.com/PixelVision8/PixelVisionOS/issues/27)

* [Disk doesn't highlight after reload](https://github.com/PixelVision8/PixelVisionOS/issues/33)

* [Slider scroll value issue](https://github.com/PixelVision8/PixelVisionOS/issues/13)

* [Ejecting disk issue](https://github.com/PixelVision8/PixelVisionOS/issues/26)

* [Shouldn't be able to eject drive](https://github.com/PixelVision8/PixelVisionOS/issues/31)

* [Log message display error](https://github.com/PixelVision8/PixelVisionOS/issues/32)

* [Fix Slider when mouse is offscreen](https://github.com/PixelVision8/PixelVisionOS/issues/35)

### MonoGame Runner (v0.9.1)

* [Need to save to tmp directory](https://github.com/PixelVision8/MonoGameRunner/issues/7)

* [Glitch error when loading games](https://github.com/PixelVision8/MonoGameRunner/issues/1)

* [Ejecting OS disk with game in drive](https://github.com/PixelVision8/MonoGameRunner/issues/4)

* [If game doesn't have autoload it doesn't load](https://github.com/PixelVision8/MonoGameRunner/issues/5)

* [Print doesn't work](https://github.com/PixelVision8/MonoGameRunner/issues/6)

* [Issue loading Libs](https://github.com/PixelVision8/MonoGameRunner/issues/2)

### SDK (v1.9.1)

* [Need to flip the order of arguments in DrawPixels()](https://github.com/PixelVision8/SDK/issues/16)


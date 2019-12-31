The color map allows the engine to better understand how to index sprite, font and tilemap PNG colors when they don’t match up to the system colors. Without a `color-map.png`, the engine automatically attempts to use the system colors as the index for each color found in a sprite. With the color map, you can set the colors of your sprites independent of the game’s actual system colors re-map them to default colors so they render correctly. Let’s take a look at a few sprites and how their colors are indexed when imported:

<p style="text-align:center"><img src="images/ParsingColorMapData_image_0.png" /></p>

Here you can see that these sprites contain four colors, not including transparency which is represented as magenta. They could work well with a Game Boy color palette, but that system uses four shades of green:

<p style="text-align:center"><img src="images/ParsingColorMapData_image_1.png" /></p>

To fix this, we can create a color map that has the native sprite colors in the same order as the system colors, like this:

<p style="text-align:center"><img src="images/ParsingColorMapData_image_2.png" /></p>

Now when the sprites are loaded up in memory, they will automatically use the correct system colors:

<p style="text-align:center"><img src="images/ParsingColorMapData_image_3.png" /></p>

Here is an example of the color mapper converting the grayscale sprites into the system’s four shades of green:

<p style="text-align:center"><img src="images/ParsingColorMapData_image_4.png" /></p>

As a best practice, you should always design your sprites in shades of gray and include a `color-map.png`. That way, the engine knows how to correctly parse your sprite and tilemap data independently from the system colors.


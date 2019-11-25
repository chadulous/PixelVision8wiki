# Clearing the Display

When you create a new project without any code in it, the display simply shows the background color. This default color is 0 which is the first color in the `ColorChip`. If the color is out of range, it will default to the background color as well.

<p style="text-align:center"><img src="images/ClearingTheDisplay_image_0.png" /></p>

You can always override the default background by calling `BackgroundColor(colorID)` in your code. Likewise, you can manually set the default background color in the Color Editor.

<p style="text-align:center"><img src="images/ClearingTheDisplay_image_1.png" /></p>

Simply select the color you want to use and from the drop-down menu, select Set BG Color.

<p style="text-align:center"><img src="images/ClearingTheDisplay_image_2.png" /></p>

Now if you refresh the game, you can see the new color. 

<p style="text-align:center"><img src="images/ClearingTheDisplay_image_3.png" /></p>

This value can also be changed by hand in the `data.json` file. The background color property is part of the ColorChip.

<p style="text-align:center"><img src="images/ClearingTheDisplay_image_4.png" /></p>

In order to see the background color, you’ll need to tell the renderer to clear the screen. The easiest way to do this is by calling `Clear()`at the beginning of your game’s `Draw()` method.

Not only does this method display the current background color, but it also removes the previous frame's pixel data. If you were to render a sprite to the display and move it without calling clear, it would ghost.

<p style="text-align:center"><img src="images/ClearingTheDisplay_image_5.png" /></p>

You can update the background color at any time, and the next time the engine calls `Clear()`,  the color reflects the change. Try adding this to your `Update()` method:

`BackgroundColor(math.random(0, 3))`

Now when you refresh your game, the background will randomly change between the first 3 colors. Understanding how to correctly clear the display is critical to creating clean render logic for your game.


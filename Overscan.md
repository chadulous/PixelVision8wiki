The `DisplayChip`’s `overscan `property tells the engine how many pixels to crop from the right and bottom side of the screen. Leveraging Pixel Vision 8's overscan area is useful when trying to hide sprites off-screen to keep them from wrapping. Older consoles had the ability to "blank", or not render, a row or column of the display to account for this. This was one way they were able to account for the non-visible areas CRT monitors had around their edges and to deal with sprites wrapping around the display.

If no overscan value is set, the sprites will immediately wrap around the right and bottom edges of the screen. Let’s take a look at two turtle shells as they move horizontally and vertically towards the edge of the screen.  As you can see, Any pixel data that goes past the edge of the screen immediately wrap to the opposite side of the screen.

<p style="text-align:center"><img src="images/Overscan_image_0.png" /></p>

We can use the overscan to hide sprites offscreen. Let’s say we change the overscan `X` and `Y` values to `1`. This will effectively give us an 8-pixel offscreen buffer on the right and bottom of the display. Here you can see the overscan area in black.

<p style="text-align:center"><img src="images/Overscan_image_1.png" /></p>

The display will automatically remove the overscan area. If we look at the screen with the new overscan value, we’ll see that the turtle shell no longer appears on the right side of the screen when its `X` greater than `248 `pixels.

<p style="text-align:center"><img src="images/Overscan_image_2.png" /></p>

When overscan is combined with the `DrawSprites()` API you can automatically handle hiding sprites offscreen by setting the `onScreen `argument to true. The DrawSprites() method will check to see which sprites are inside of the visible area and not render the ones outside of it. This allows you to account for sprite wrapping and you can use the overscan area to hide sprites offscreen.

It’s important to note that if your game is running at the maximum resolution, `512` x `480`, there will be no overscan. If you need a buffer to hide images off-screen, the maximum resolution you can display your game at will effectively be `504` x `472`.


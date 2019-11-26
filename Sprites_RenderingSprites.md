# Rendering Sprites

You can draw sprites to the display via the `DrawSprite()` method. This method requires a sprite ID as well as an x and y position for where to place the sprite on the screen. By default, the display wraps sprite so if you draw a sprite to an `x` or `y` position past the display’s dimensions, it part of it will appear on the opposite side of the screen. 

<p style="text-align:center"><img src="images/RenderingSprites_image_0.png" /></p>

When rendering a sprite to the display, there are two optional boolean flags for flipping the sprite horizontally or vertically. 

<p style="text-align:center"><img src="images/RenderingSprites_image_1.png" /></p>

Next, you can define if the sprite appears above or below the background layer. Here is an example of a pip sprite on the tilemap layer and the player in front and behind of it.

<p style="text-align:center"><img src="images/RenderingSprites_image_2.png" /></p>


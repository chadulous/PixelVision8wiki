Clearing the display removes all of the existing pixel data, replacing it with the default background color. The `Clear()` API allows you to specify what region of the display to clear. By calling` Clear()`, with no arguments, it automatically clears the entire display. You can manually define an area of the screen to clear by supplying optional `x`, `y`, `width`, and `height` argument values. 

When clearing a specific area of the display, anything outside of the defined boundaries remains on the next draw phase. This is useful for drawing a HUD but clearing the display below for a scrolling map and sprites. The `Clear()` can only be used once during the draw phase.

## Usage

`Clear ( x, y, width, height )`

## Arguments

<table>
  <tr>
    <td>Name</td>
    <td>Value</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>x</td>
    <td>int</td>
    <td>This is an optional value that defaults to 0 and defines where the clear's X position should begin. When X is 0, clear starts on the far left-hand side of the display. Values less than 0 or greater than the width of the display are ignored.</td>
  </tr>
  <tr>
    <td>y</td>
    <td>int</td>
    <td>This is an optional value that defaults to 0 and defines where the clear's Y position should begin. When Y is 0, clear starts at the top of the display. Values less than 0 or greater than the height of the display are ignored.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>int</td>
    <td>This is an optional value that defaults to the width of the display and defines how many horizontal pixels to clear. When the width is 0, clear starts at the x position and ends at the far right-hand side of the display. Values less than 0 or greater than the width are adjusted to stay within the boundaries of the screen's visible pixels.</td>
  </tr>
  <tr>
    <td>height</td>
    <td>int</td>
    <td>This is an optional value that defaults to the height of the display and defines how many vertical pixels to clear. When the height is 0, clear starts at the Y position and ends at the bottom of the display. Values less than 0 or greater than the height are adjusted to stay within the boundaries of the screen's visible pixels.</td>
  </tr>
</table>


## Example

In this example, we are going to use a simple time to toggle between clearing the entire screen or just the center of the screen:

    class ClearExample : GameChip
    {
        // Create a new random generator
        Random random = new Random();

        // We'll store the display's boundaries here
        private Point display;
        
        // Create a delay and time value
        private int delay = 2000;
        private int time = 0;

        // This flag will toggle between a full or partial clear
        private bool clearFlag = false;

        // Store random integers for drawing a random character to the screen
        private int charID, x, y, colorID;

        public override void Init()
        {
            // Save the display's boundaries when the game starts up
            display = Display();
        }

        public override void Update(int timeDelta)
        { 
            // Increase the time value base on the timeDelta between the last frame
            time = time + timeDelta;

                       // Text to see if time is greater than the delay
            if(time &gt; delay)
            {

                // Toggle the clear flag
                clearFlag = !clearFlag;

                // Reset the timer
                time = 0;

            }
        }

        public override void Draw()
        { 
            // Test the clear flag and do a full or partial clear based on the value
            if (clearFlag == true)
            {
                Clear();
            } else {
                Clear(16, 16, display.X - 32, display.Y - 32);
            }

            // Perform the next block of code 10 times
            for (int i = 0; i &lt; 10; i++)
            {
             
                // Assign random values to each of these variable
                charID = random.Next(32, 126);
                x = random.Next(0, display.X);
                y = random.Next(0, display.Y);
                colorID = random.Next(1, 15);

                // Draw a random charIDacter at a random position on the screen with a random color
                DrawText(Convert.ToChar(charID).ToString(), x, y, DrawMode.Sprite, "large", colorID);

            }
        }
    }

Running this code will output the following:

<p style="text-align:center"><img src="images/ClearOutput_image_0.png" /></p>


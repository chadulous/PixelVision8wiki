A fast way to calculate the distance between two points.

## Usage

```csharp
CalculateDistance ( x0, y0, x1, y1 )
```

## Arguments

| Name | Value | Description                     |
|------|-------|---------------------------------|
| x0   | int   | The first point’s x position\.  |
| y0   | int   | The first point’s y position\.  |
| x1   | int   | The second point’s x position\. |
| y1   | int   | The second point’s y position\. |



## Returns

| Value | Description                                                  |
|-------|--------------------------------------------------------------|
| int   | Returns an integer for the distance between the two points\. |


## Example

In this example, we will calculate the distance between 2 points and use a canvas to visualize it:



## Lua

```lua
local pointA = NewPoint(8, 8)
local pointB = NewPoint(248, 232)
local canvas = NewCanvas(256, 240)
local distance = 0

function Init()

  -- Set the canvas stroke to a white 1x1 pixel brush
  canvas:SetStroke({15}, 1, 1)

end

function Update(timeDelta)

  -- Update position B with the MousePosition
  pointB = MousePosition()

  -- Calculate the distance between pointA and pointB
  distance = CalculateDistance(pointA.x, pointA.y, pointB.x, pointB.x)

end

function Draw()

  -- Redraw the display
  RedrawDisplay()

  -- Clear the canvas with the background color
  canvas:Clear(0)

  -- Draw 2 circles around each point
  canvas:DrawCircle(pointA.x - 4, pointA.y - 4, pointA.x + 4, pointA.y + 4)
  canvas:DrawCircle(pointB.x - 4, pointB.y - 4, pointB.x + 4, pointB.y + 4)

  -- Draw a line between the two points
  canvas:DrawLine(pointA.x, pointA.y, pointB.x, pointB.y)

  -- Draw the distance value above pointB
  canvas:DrawText(tostring(distance), pointB.x, pointB.y - 12, "small", 15, - 4)

  -- Draw the canvas to the display
  canvas:DrawPixels()

end
```



## C#

```csharp
class CalculateDistanceExample : GameChip
{
    private Point pointA = new Point(8, 8);
    private Point pointB = new Point(248, 232);
    private Canvas canvas;
    private int distance;

    public override void Init()
    {

        // Create a new canvas and pass this GameChip into the constructor
        canvas = new Canvas(256, 240, this);

        // Set the canvas stroke to a white 1x1 pixel brush
        canvas.SetStroke(new []{15}, 1, 1);

    }

    public override void Update(int timeDelta)
    { 

        // Update position B with the MousePosition
        pointB = MousePosition();

        // Calculate the distance between pointA and pointB
        distance = CalculateDistance(pointA.X, pointA.Y, pointB.X, pointB.X);

    }

    public override void Draw()
    {

        // Redraw the display
        RedrawDisplay();

        // Clear the canvas with the background color
        canvas.Clear(0);

        // Draw 2 circles around each point
        canvas.DrawCircle(pointA.X - 4, pointA.Y - 4, pointA.X + 4, pointA.Y + 4);
        canvas.DrawCircle(pointB.X - 4, pointB.Y - 4, pointB.X + 4, pointB.Y + 4);

        // Draw a line between the two points
        canvas.DrawLine(pointA.X, pointA.Y, pointB.X, pointB.Y);

        // Draw the distance value above pointB
        canvas.DrawText(distance.ToString(), pointB.X, pointB.Y - 12, "small", 15, -4);

        // Draw the canvas to the display
        canvas.DrawPixels();

    }
}
```



Running this code will output the following:

![image alt text](images/CalculateDistanceOutput_image_0.png)



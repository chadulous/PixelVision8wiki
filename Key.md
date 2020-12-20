# Key()

While the main forms of input for Pixel Vision 8 are the controllers, you can test for keyboard input by calling the `Key()` API. When this API is called, it returns the current state of that specific key. The method accepts the `Keys` enum, or an `int`, for a specific key. In addition, you need to provide the input state to check for. The `InputState `enum has two states, `Down` and `Released`. By default, `Down` is automatically used which returns `true` when the key is being pressed in the current frame. When using `Released`, the API returns `true `only when the key was `Down `in the last frame and `Up `in the current frame.

## Usage

```csharp
Key ( key, state )
```

## Arguments

| Name  | Value      | Description                                                                                                                             |
|-------|------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| key   | Keys       | This argument accepts the Keys enum or an int for the key's ID\.                                                                        |
| state | InputState | Optional InputState enum\. Returns down state by default\. This argument accepts InputState\.Down \(0\) or InputState\.Released \(1\)\. |

## Returns

| Value | Description                                                   |
|-------|---------------------------------------------------------------|
| bool  | This method returns a bool based on the state of the button\. |

## Keys

These are the valid keys that Pixel Vision 8 can see and their corresponding ID.

| Enum            | Value | Enum                   | Value |
|-----------------|-------|------------------------|-------|
| Keys\.None      | 0     | Keys\.S                | 83    |
| Keys\.Backspace | 8     | Keys\.T                | 84    |
| Keys\.Tab       | 9     | Keys\.U                | 85    |
| Keys\.Enter     | 13    | Keys\.V                | 86    |
| Keys\.Escape    | 27    | Keys\.W                | 87    |
| Keys\.Space     | 32    | Keys\.X                | 88    |
| Keys\.PageUp    | 33    | Keys\.Y                | 89    |
| Keys\.PageDown  | 34    | Keys\.Z                | 90    |
| Keys\.End       | 35    | Keys\.NumPad0          | 96    |
| Keys\.Home      | 36    | Keys\.NumPad1          | 97    |
| Keys\.Left      | 37    | Keys\.NumPad2          | 98    |
| Keys\.Up        | 38    | Keys\.NumPad3          | 99    |
| Keys\.Right     | 39    | Keys\.NumPad4          | 100   |
| Keys\.Down      | 40    | Keys\.NumPad5          | 101   |
| Keys\.Insert    | 45    | Keys\.NumPad6          | 102   |
| Keys\.Delete    | 46    | Keys\.NumPad7          | 103   |
| Keys\.D0        | 48    | Keys\.NumPad8          | 104   |
| Keys\.D1        | 49    | Keys\.NumPad9          | 105   |
| Keys\.D2        | 50    | Keys\.Multiply         | 106   |
| Keys\.D3        | 51    | Keys\.Add              | 107   |
| Keys\.D4        | 52    | Keys\.Separator        | 108   |
| Keys\.D5        | 53    | Keys\.Subtract         | 109   |
| Keys\.D6        | 54    | Keys\.Decimal          | 110   |
| Keys\.D7        | 55    | Keys\.Divide           | 111   |
| Keys\.D8        | 56    | Keys\.LeftShift        | 160   |
| Keys\.D9        | 57    | Keys\.RightShift       | 161   |
| Keys\.A         | 65    | Keys\.LeftControl      | 162   |
| Keys\.B         | 66    | Keys\.RightControl     | 163   |
| Keys\.C         | 67    | Keys\.LeftAlt          | 164   |
| Keys\.D         | 68    | Keys\.RightAlt         | 165   |
| Keys\.E         | 69    | Keys\.OemSemicolon     | 186   |
| Keys\.F         | 70    | Keys\.OemPlus          | 187   |
| Keys\.G         | 71    | Keys\.OemComma         | 188   |
| Keys\.H         | 72    | Keys\.OemMinus         | 189   |
| Keys\.I         | 73    | Keys\.OemPeriod        | 190   |
| Keys\.J         | 74    | Keys\.OemQuestion      | 191   |
| Keys\.K         | 75    | Keys\.OemTilde         | 192   |
| Keys\.L         | 76    | Keys\.OemOpenBrackets  | 219   |
| Keys\.M         | 77    | Keys\.OemPipe          | 220   |
| Keys\.N         | 78    | Keys\.OemCloseBrackets | 221   |
| Keys\.O         | 79    | Keys\.OemQuotes        | 222   |
| Keys\.P         | 80    | Keys\.OemBackslash     | 226   |
| Keys\.Q         | 81    | Keys\.OemClear         | 254   |
| Keys\.R         | 82    |                        |       |

## Input State Enumes

There are two input states you can use to test a key’s current state:

| Enum                 | Value |
|----------------------|-------|
| InputState\.Down     | 0     |
| InputState\.Released | 1     |

## Example

In this example, we are going to test for any of the number keys to be pressed:



## Lua

```lua
-- List of keys to test for
local keyStates = {
  {name = Keys.Alpha0, state = false},
  {name = Keys.Alpha1, state = false},
  {name = Keys.Alpha2, state = false},
  {name = Keys.Alpha3, state = false},
  {name = Keys.Alpha4, state = false},
  {name = Keys.Alpha5, state = false},
  {name = Keys.Alpha6, state = false},
  {name = Keys.Alpha7, state = false},
  {name = Keys.Alpha8, state = false},
  {name = Keys.Alpha9, state = false}
}

function Init()

  -- Create labels for all of the keys
  for i = 1, #keyStates do
    DrawText("Key " .. tostring(i - 1) .. " is down ", 1, i, DrawMode.Tile, "large", 15)
  end

end

function Update(timeDelta)

  -- Loop through all of the number keys and save the current state value
  for i = 1, #keyStates do
    keyStates[i].state = Key(keyStates[i].name)
  end

end

function Draw()

  -- Redraw the display
  RedrawDisplay()

  -- Loop through all the keys and display their current down state
  for i = 1, #keyStates do
    DrawText(tostring(keyStates[i].state), 128, (i * 8), DrawMode.Sprite, "large", 14)
  end

end
```



## C#

```csharp
class KeyExample : GameChip
{
    // List of keys to test for
    private Dictionary&lt;Keys, bool&gt; keyStates = new Dictionary&lt;Keys, bool&gt;()
    {
        {Keys.Alpha0, false},
        {Keys.Alpha1, false},
        {Keys.Alpha2, false},
        {Keys.Alpha3, false},
        {Keys.Alpha4, false},
        {Keys.Alpha5, false},
        {Keys.Alpha6, false},
        {Keys.Alpha7, false},
        {Keys.Alpha8, false},
        {Keys.Alpha9, false}
    };

    public override void Init()
    {

        // Use this counter during the foreach loop below
        var counter = 1;

        // Create labels for all of the keys
        foreach (var keyState in keyStates)
        {
            DrawText("Key " + keyState.Key + " is down ", 1, counter, DrawMode.Tile, "large", 15);
            counter++;
        }

    }

    public override void Update(int timeDelta)
    {
        
        // Need t o get a list of all the Dictionary's keys so we can iterate over them while updating each value
        var keyNames = new List&lt;Keys&gt;(keyStates.Keys);

        // Loop through all of the number keys and save the current state value
        foreach (Keys keyName in keyNames)
        {
            keyStates[keyName] = Key(keyName);
        }
    }

    public override void Draw()
    {
        // Redraw the display
        RedrawDisplay();

        // Use this counter during the foreach loop below
        var counter = 1;

        // Loop through all the keys and display their current down state
        foreach (var key in keyStates.Keys)
        {
            DrawText(keyStates[key].ToString(), 128 + 36, (counter * 8), DrawMode.Sprite, "large", 14);
            counter++;
        }

    }
}
```



Running this code will output the following:

![image alt text](images/KeyOutput_image_0.png)



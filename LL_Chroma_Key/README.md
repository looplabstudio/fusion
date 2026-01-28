# LoopLab Studio: Chroma Key Node

Technical documentation for `LL_Chroma_Key` - a macro that supports procedural animation and general best practices:  

- Creates a chroma key `Background` node with easy color switching.
- Displays [project pixel dimensions and normalized aspect ratios](../Macro-Reference/Project-Dimensions.md).
- Displays [composition frames and time expressed multiple ways](../Macro-Reference/Composition-Frames-Time.md).


## Why use a Key Node? 

Fusion compositions often start with a `Background` node that: 

- Establishes the comp's resolution and aspect ratio.
- Prevents unwanted resolution changes when merging nodes of different sizes and aspects.
- Provide a consistent frame of reference for positioning and scaling elements.
- Set a transparent or chroma key background for the composition.


## User Controls


```lua
Tool_Key.Key_Color: 1

0 Transparent: 0 0 0 0 
1 Green: 0 1 0 1
2 Blue: 0 0 1 1
3 Black: 0 0 0 1
4 White: 1 1 1 1

```

## Color Calculations

```lua
-- Red (R)
Tool_Key.Key_Red

  (Key_Color== 4) and 1 or 0

-- Green (G)	
Tool_Key.Key_Green

  ((Key_Color== 1) or (Key_Color== 4)) and 1 or 0

-- Blue (B)	
Tool_Key.Key_Blue

  ((Key_Color== 2) or (Key_Color== 4)) and 1 or 0

-- Alpha (A)	
Tool_Key.Key_Alpha

  (Key_Color== 0) and 0 or 1

```

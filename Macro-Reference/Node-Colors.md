# DaVinci Resolve Fusion: Node Colors

A quick grab of Fusion node colors used in `.setting` files.


## Location

```lua
{
	Tools = ordered() {
		Tool_Name = Custom {
			CtrlWZoom = false,
			Inputs = {},
			ViewInfo = OperatorInfo {},

			-- Orange
			Colors = { TileColor = { R = 0.92156862745098, G = 0.431372549019608, B = 0 }, },
			
			UserControls = ordered() {}
		},
		Tool_NameLUTIn1 = LUTBezier {},
		Tool_NameLUTIn2 = LUTBezier {},
		Tool_NameLUTIn3 = LUTBezier {},
		Tool_NameLUTIn4 = LUTBezier {}
	},
	ActiveTool = "Tool_Name"
}
```

## Colors

```lua
-- Orange
Colors = { TileColor = { R = 0.92156862745098, G = 0.431372549019608, B = 0 }, },
```

```lua
-- Apricot
Colors = { TileColor = { R = 1, G = 0.658823529411765, B = 0.2 }, },
```

```lua
-- Yellow
Colors = { TileColor = { R = 0.886274509803922, G = 0.662745098039216, B = 0.109803921568627 }, },
```

```lua
-- Lime
Colors = { TileColor = { R = 0.623529411764706, G = 0.776470588235294, B = 0.0823529411764706 }, },
```

```lua
-- Olive
Colors = { TileColor = { R = 0.372549019607843, G = 0.6, B = 0.125490196078431 }, },
```

```lua
-- Green
Colors = { TileColor = { R = 0.266666666666667, G = 0.56078431372549, B = 0.396078431372549 }, },
```

```lua
-- Teal
Colors = { TileColor = { R = 0, G = 0.596078431372549, B = 0.6 }, },
```

```lua
-- Navy
Colors = { TileColor = { R = 0.0823529411764706, G = 0.384313725490196, B = 0.517647058823529 }, },
```

```lua
-- Blue
Colors = { TileColor = { R = 0.474509803921569, G = 0.658823529411765, B = 0.815686274509804 }, },
```

```lua
-- Purple
Colors = { TileColor = { R = 0.6, G = 0.450980392156863, B = 0.627450980392157 }, },
```

```lua
-- Violet
Colors = { TileColor = { R = 0.584313725490196, G = 0.294117647058824, B = 0.803921568627451 }, },
```

```lua
-- Pink
Colors = { TileColor = { R = 0.913725490196078, G = 0.549019607843137, B = 0.709803921568627 }, },
```

```lua
-- Tan
Colors = { TileColor = { R = 0.725490196078431, G = 0.690196078431373, B = 0.592156862745098 }, },
```

```lua
-- Beige
Colors = { TileColor = { R = 0.776470588235294, G = 0.627450980392157, B = 0.466666666666667 }, },
```

```lua
-- Brown
Colors = { TileColor = { R = 0.6, G = 0.4, B = 0 }, },
```

```lua
-- Chocolate
Colors = { TileColor = { R = 0.549019607843137, G = 0.352941176470588, B = 0.247058823529412 }, },
```

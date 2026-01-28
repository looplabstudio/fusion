# DaVinci Resolve Fusion: Node Dimensions

A quick grab for dynamically getting the dimensions of a Fusion node using Domain of Definition (DoD).

```lua
-- Node Pixel Width
Tool_Name.Node_Px_Width

    Node_Name.Output.Width

-- Node Pixel Height
Tool_Name.Node_Px_Height

    Node_Name.Output.Height

-- Node Left Edge
Tool_Name.Node_Edge_Left

    Node_Name.Output.DataWindow[1]

-- Node Right Edge
Tool_Name.Node_Edge_Right

    Node_Name.Output.DataWindow[3]

-- Node Top Edge
Tool_name.Node_Edge_Top

    Node_Name.Output.DataWindow[4]

-- Node Bottom Edge
Tool_Name.Node_Edge_Bottom

    Node_Name.Output.DataWindow[2]

-- Node Width Normalized
-- ((Node_Name.Output.DataWindow[3] - Node_Name.Output.DataWindow[1]) / Node_Name.Output.Width)

    ((Node_Edge_Right - Node_Edge_Left) / Node_Px_Width)

-- Node Height Normalized
-- ((Node_Name.Output.DataWindow[4] - Node_Name.Output.DataWindow[2]) / Node_Name.Output.Height)

    ((Node_Edge_Top - Node_Edge_Bottom) / Node_Px_Height)

```


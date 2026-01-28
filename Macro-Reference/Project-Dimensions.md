# DaVinci Resolve Fusion: Project Dimensions and Aspect Ratio

A quick grab for dynamically getting project dimensions. 


## Documentation

```lua
-- Screen width as pixels
Tool_Name.Px_Width

  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Width\")",

-- Screen height as pixels
Tool_Name.Px_Height

  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Height\")",

-- Aspect Ratio (16:9 = 1.777778)
Tool_Name.Aspect

  (Px_Width / Px_Height)

-- Inverse Aspect Ration (16:9 = 0.5625)
Tool_Name.Aspect_Inv

  (1 / Aspect)

```

## Instance Inputs

```lua

-- Project_Dimensions
Project_Dimensions = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Project_Dimensions",
  Name = "Project Dimensions",
  Page = "Controls",
  Default = 0, 
},
Px_Width = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Px_Width",
  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Width\")",
  Name = "Px Width",
  Page = "Controls",
  Default = 1920,
},
Px_Height = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Px_Height",
  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Height\")",
  Name = "Px Height",
  Page = "Controls",
  Default = 1080,
},
Aspect = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Aspect",
  Expression = "(Px_Width / Px_Height)",
  Page = "Controls",
  Default = 1.777778,
},
Aspect_Inv = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Aspect_Inv",
  Expression = "(1 / Aspect)",
  Name = "Aspect Inv",
  Page = "Controls",
  Default = 0.5625,
},

```

## Inputs

```lua
-- Inputs 
Px_Width = Input {
  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Width\")",
},
Px_Height = Input {
  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Height\")",
},
Aspect = Input { 
  Expression = "(Px_Width / Px_Height)", 
},
Aspect_Inv = Input { 
  Expression = "(1 / Aspect)", 
},

```

## UserControls

```lua
-- UserControls
Project_Dimensions = {
  LINKS_Name = "Dimensions",
  LBLC_NumInputs = 4,
  LINKID_DataType = "Number",
  INPID_InputControl = "LabelControl",
  LBLC_DropDownButton = true,
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
Px_Width = {
  LINKS_Name = "Px_Width",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = false,
  INP_External = false,
  INP_Passive = true,
  INP_SplineType = "Default",
  ICS_ControlPage = "Controls",
},
Px_Height = {
  LINKS_Name = "Px_Height",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = false,
  INP_External = false,
  INP_Passive = true,
  INP_SplineType = "Default",
  ICS_ControlPage = "Controls",
},
Aspect = {
  LINKS_Name = "Aspect",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = false,
  INP_External = false,
  INP_Passive = true,
  INP_SplineType = "Default",
  ICS_ControlPage = "Controls",
},
Aspect_Inv = {
  LINKS_Name = "Aspect_Inv",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = false,
  INP_External = false,
  INP_Passive = true,
  INP_SplineType = "Default",
  ICS_ControlPage = "Controls",
},

```

# DaVinci Resolve Fusion: Composition Frames and Time

A quick grab for dynamically getting Fusion composition frames and time information. 


## Composition Frames

```lua
-- Frame Rate (60)
Tool_Key.FPS

  comp:GetPrefs("Comp.FrameFormat.Rate")
  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Rate\")", 

-- Total fames in composition
Tool_Key.Total_Frames

  comp.RenderEnd + 1

-- Equals total frames minus 1
-- This leaves a 1-frame buffer at end of comp
-- so that animations fully complete. 
Tool_Key.Available_Frames

    comp.RenderEnd

-- Normalized duration of 1 frame
Tool_Key.Frame_Norm_Duration

    (1 / FPS)

```

## Composition Time

```lua

-- Current frame number
Tool_Key.Time_Frame

    time

-- Current frame expressed as [0-1] progress 
-- across Available_Frames
Tool_Key.Time_Norm

    (math.min(1, math.max(0, (time / Available_Frames))))

-- Current frame expressed in seconds
Tool_Key.Time_Seconds

    (time / FPS)

```


## Instance Inputs

```lua
-- Composition_Frames
Composition_Frames = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Composition_Frames",
  Name = "Composition Frames",
  Page = "Controls",
  Default = 0, 
},
FPS = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "FPS",
  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Rate\")",
  Page = "Controls",
  Default = 30,
},
Total_Frames = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Total_Frames",
  Expression = " comp.RenderEnd + 1",
  Name = "Total Frames",
  Page = "Controls",
  Default = 1001,
},
Available_Frames = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Available_Frames",
  Expression = "comp.RenderEnd",
  Name = "Available Frames",
  Page = "Controls",
  Default = 1000,
},
Frame_Norm_Duration = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Frame_Norm_Duration",
  Expression = "(1 / FPS)",
  Name = "Frame Norm Duration",
  Page = "Controls",
  Default = 0.0333333333333,
},

-- Composition_Time
Composition_Time = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Composition_Time",
  Name = "Composition Time",
  Page = "Controls",
  Default = 0, 
},
Time_Frame = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Time_Frame",
  Expression = "time",
  Name = "Time Frame",
  Page = "Controls",
  Default = 0,
},
Time_Norm = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Time_Norm",
  Expression = "(math.min(1, math.max(0, (time / Available_Frames))))",
  Name = "Time Norm",
  Page = "Controls",
  Default = 0,
},
Time_Seconds = InstanceInput {
  SourceOp = "Tool_Key",
  Source = "Time_Seconds",
  Expression = "(time / FPS)",
  Name = "Time Seconds",
  Page = "Controls",
  Default = 0,
}

```

## Inputs

```lua
--Composition_Frames
FPS = Input {
  Expression = "comp:GetPrefs(\"Comp.FrameFormat.Rate\")", 
},
Total_Frames = Input {
  Expression = " comp.RenderEnd + 1",
},
Available_Frames = Input {
  Expression = "comp.RenderEnd",
},
Frame_Norm_Duration = Input {
  Expression = "(1 / FPS)",
},

-- Composition_Time
Time_Frame = Input {
  Expression = "time",
},
Time_Norm = Input {
  Expression = "(math.min(1, math.max(0, (time / Available_Frames))))",
},
Time_Seconds = Input {
  Expression = "(time / FPS)",
},
```

## UserControls

```lua
Composition_Frames = {
  LINKS_Name = "Composition_Frames",
  LBLC_NumInputs = 4,
  LINKID_DataType = "Number",
  INPID_InputControl = "LabelControl",
  LBLC_DropDownButton = true,
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
FPS = {
  LINKS_Name = "FPS",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
Total_Frames = {
  LINKS_Name = "Total_Frames",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
Available_Frames = {
  LINKS_Name = "Available_Frames",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
Frame_Norm_Duration = {
  LINKS_Name = "Frame_Norm_Duration",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},

Composition_Time = {
  LINKS_Name = "Composition_Time",
  LBLC_NumInputs = 3,
  LINKID_DataType = "Number",
  INPID_InputControl = "LabelControl",
  LBLC_DropDownButton = true,
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
Time_Frame = {
  LINKS_Name = "Time_Frame",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
Time_Norm = {
  LINKS_Name = "Time_Norm",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
Time_Seconds = {
  LINKS_Name = "Time_Seconds",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},

```

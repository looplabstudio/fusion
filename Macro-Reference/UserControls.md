# DaVinci Resolve Fusion: InstanceInputs, Inputs, UserControls

A quick grab of the most common controls used in `.setting` files. 


## Section Labels

```lua
-- InstanceInput
Settings = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "Settings",
  Name = "Settings",
  Page = "Controls",
  Default = 0,
},

-- UserControl
Settings = {
  LINKS_Name = "Settings",
  LBLC_NumInputs = 1,
  LINKID_DataType = "Number",
  INPID_InputControl = "LabelControl",
  LBLC_DropDownButton = true,
  INP_External = false,
  INP_Passive = true,
  INP_Default = 0,
  ICS_ControlPage = "Controls",
},
```

## Button Toggle

```lua
-- InstanceInput
Toggle = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "Toggle",
  Name = "Toggle",
  Page = "Controls",
  Default = 0,
},

-- UserControl
Toggle = {
  LINKS_Name = "Toggle",
  INP_Default = 0,
  { MBTNC_AddButton = "Off" },
  { MBTNC_AddButton = "On" },
  LINKID_DataType = "Number",
  INPID_InputControl = "MultiButtonControl",
  MBTNC_ShowName = true,
  MBTNC_ShowBasicButton = true,
  MBTNC_StretchToFit = true,
  MBTNC_ShowToolTip = false,
  ICS_ControlPage = "Controls",
},
```

## Number Input

```lua
-- InstanceInput
Num_Input = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "Num_Input",
  Name = "Num_Input",
  Page = "Controls",
  Default = 0.0,
},

-- UserControl
Num_Input = {
  LINKS_Name = "Num_Input",
  INP_Default = 0.0,
  INP_MinScale = 0.0,
  INP_MaxScale = 1.0,
  -- INP_MinAllowed = 0.0,
  -- INP_MaxAllowed = 1.0,
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  -- INP_Integer = true,
  ICS_ControlPage = "Controls",
},
```

## Number Calculation (non-editable)

```lua
-- InstanceInput (exposed calc)
Num_Calc = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "Num_Calc",
  Name = "Num_Calc",
  Page = "Controls",
},

-- Input
Num_Calc = Input {
  Expression = "",
},

-- UserControl
Num_Calc = {
  LINKS_Name = "Num_Calc",
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_External = false,
  INP_Passive = true,
  ICS_ControlPage = "Controls",
},
```

## Point Input

```lua
-- InstanceInput
Point_Input = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "Point_Input",
  Name = "Point_Input",
  Page = "Controls",
  DefaultX = 0.5,
  DefaultY = 0.5,
},

-- UserControl
Point_Input = {
  LINKS_Name = "Point_Input",
  INP_DefaultX = 0.5,
  INP_DefaultY = 0.5,
  LINKID_DataType = "Point",
  INPID_InputControl = "OffsetControl",					
  ICS_ControlPage = "Controls",
},
```

## Point Calculation (non-editable)

```lua
-- InstanceInput (exposed calc)
Point_Calc = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "Point_Calc",
  Name = "Point_Calc",
  Page = "Controls",
},

-- Input
Point_Calc = Input {
  Expression = "Point()",
},

-- UserControl
Point_Calc = {
  LINKS_Name = "Point_Calc",
  LINKID_DataType = "Point",
  INPID_InputControl = "OffsetControl",					
  INP_External = false,
  INP_Passive = true,	
  ICS_ControlPage = "Controls",
},
```

## Combo Box

```lua
-- InstanceInput
Combo_Name = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "Combo_Name",
  Name = "Combo_Name",
  Page = "Controls",
  Default = 0,
},

-- UserControl
Combo_Name = {
  LINKS_Name = "Combo_Name",
  INP_Default = 0,
  { CCS_AddString = "Option1" },
  { CCS_AddString = "Option2" },
  { CCS_AddString = "Option3" },
  LINKID_DataType = "Number",
  INPID_InputControl = "ComboControl",
  ICS_ControlPage = "Controls",
},
```

## Angle Input

```lua
-- InstanceInput
Angle = InstanceInput {
  SourceOp = "Tool_Name",
  Source = "Angle",
  Name = "Angle",
  Page = "Controls",
  Default = 0,
},

-- UserControl
Angle = {
  LINKS_Name = "Angle",
  INP_Default = 0,
  INP_MinScale = 0,
  INP_MaxScale = 360,
  INP_MinAllowed = 0,
  INP_MaxAllowed = 360,
  LINKID_DataType = "Number",
  INPID_InputControl = "SliderControl",
  INP_Integer = true,
  ICS_ControlPage = "Controls",
},

```
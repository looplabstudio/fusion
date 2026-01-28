# DaVinci Resolve Fusion: Angle and Rotation

If you hail from the land of Adobe, you know each app can have its own idea of how angles work. Whenever I start working with a new app, one of the first things I do is learn how its angles behave. Here are my notes for DaVinci Resolve Fusion.

## Angle Orientation

Fusion uses unit circle trigonometry for angle-based motion. This means angles operate in a square (1×1) coordinate space, where rotation is centered on a shape’s `Center` or `Pivot`.

Fusion orients angles like this: 

```
     90°
      |
180° —•— 0°/360°
      |
     270°
```

Another way to understand angle orientation is to imagine a line drawn from the shape’s `Center` or `Pivot` to a point on its bounding box — that line defines the angle.

If we think of the angle as a clock hand, Fusion orients angles like this:

```
  0° = 3:00 o'clock
 45° = 1:30 
 90° = 12:00
135° = 10:30
180° = 9:00
225° = 7:30
270° = 6:00
315° = 4:30
```

## Rotation 

- Positive angles = counter-clockwise rotation
- Negative angles = clockwise rotation

### In-Place Rotation

These `Angle` expressions rotate a shape around its own `Center`:

```lua
-- Counter-Clockwise
time * (-30)

-- Clockwise
time * 30

```

### Orbit Rotation

To move a shape in a circular orbit, we animate its `Center` using `math.cos()` and `math.sin()` — this traces a circular path around a target point.

```lua
-- 0.5 =  Screen coordinate to orbit 
    -- Here it is (0.5 ,0.5) which is center screen
-- 0.25 = Distance from orbit point (radius)

--- Orbit_X
0.5 + math.cos(time) * 0.25

-- Orbit_Y
0.5 + math.sin(time) * 0.25

-- Clockwise
Point(0.5 + math.cos(time * -1) * 0.25, 0.5 + math.sin(time * -1) * 0.25)

-- Counter-Clockwise
Point(0.5 + math.cos(time) * 0.25, 0.5 + math.sin(time) * 0.25)

```

Rotation starts at 0° or 3 o'clock by default. To start rotation at 90° or 12 o'clock, use Pi: 

```lua
-- Orbit_X
0.5 + math.cos(time + math.pi/2) * 0.25

-- Orbit_Y
0.5 + math.sin(time + math.pi/2) * 0.25

```

## Linear Movement

When used for linear motion, Fusion angles are normalized to the 1.0 screen space — which means they are tied to the project’s aspect ratio, not to a square.

That’s why, for example, a 45° angle means 'the diagonal between opposite screen corners', and not 'the diagonal of a square'.

Fusion angles produce these directional motions:

```lua
  0° = Left -> Right
 45° = BL -> TR Corners
 90° = Bottom -> Top
135° = BR -> TL Corners
180° = Right -> Left
225° = TR -> BL Corners
270° = Top -> Bottom
315° = TL -> BR Corners
```

### Test Expressions

These `Center` expressions demonstrate simple, angle-based, linear motion. 

```lua
-- Left to Right
Point(0.5 + math.cos(math.rad(0)) * time * 0.1, 0.5)

-- Bottom-Left to Top-Right
Point(0.5 + math.cos(math.rad(45)) * time * 0.1, 0.5 + math.sin(math.rad(45)) * time * 0.1)

-- Bottom to Top
Point(0.5, 0.5 + math.sin(math.rad(90)) * time * 0.1)

-- Bottom-Right to Top-Left
Point(0.5 + math.cos(math.rad(135)) * time * 0.1, 0.5 + math.sin(math.rad(135)) * time * 0.1)

-- Right to Left
Point(0.5 + math.cos(math.rad(180)) * time * 0.1, 0.5)

-- Top-Right to Bottom-Left
Point(0.5 + math.cos(math.rad(225)) * time * 0.1, 0.5 + math.sin(math.rad(225)) * time * 0.1)

-- Top to Bottom
Point(0.5, 0.5 + math.sin(math.rad(270)) * time * 0.1)

-- Top-Left to Bottom-Right
Point(0.5 + math.cos(math.rad(315)) * time * 0.1, 0.5 + math.sin(math.rad(315)) * time * 0.1)

```

## atan2 Protection

`math.atan2()` is a function that calculates the angle (in radians) from the positive x-axis to a point (x, y).

```
angle = math.atan2(y, x)

```

In procedural animation, it's common that the `x` and `y` fed to `atan2` are themselves calculations - often deltas or tangents as seen below. 

When both `x` and `y` are zero, `atan2` is technically undefined, which Fusion interprets as zero.

We need to protect against edge cases where both `x` and `y` could both be zero, but 0 degrees is the wrong calculation. 

```lua
-- Some tangent calculations
Tool_Name.Fallback_Angle: 90
Tool_Name.Tangent_X
Tool_Name.Tangent_Y

-- Converted to degrees
Tool_Name.Angle

  math.deg(math.atan2(Tangent_Y, Tangent_X)) 

-- And protected with a non-zero fallback angle
Tool_Name.Road_Lock 

  (Tangent_X == 0 and Tangent_Y == 0) and Fallback_Angle or Angle

```

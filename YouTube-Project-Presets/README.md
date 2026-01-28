# DaVinci Resolve: Project Settings for YouTube Motion Graphics

A key to great motion graphics is using higher frame rates and project dimensions. This topic covers DaVinci Resolve Project Settings for YouTube. 

- [YouTube_60FPS_UltraHD.preset](https://github.com/looplabstudio/fusion/blob/main/youtube-presets/YouTube_60FPS_UltraHD.preset)
- [YouTube_60FPS_HD.preset](https://github.com/looplabstudio/fusion/blob/main/youtube-presets/YouTube_60FPS_HD.preset)

## References

[YouTube recommended upload encoding settings](https://support.google.com/youtube/answer/1722171)

- Timeline and Frame Rate match YouTube’s ideal delivery format (UHD 3840x2160 @ 60 FPS).
- Video Monitoring is optimized for performance without compromising the project resolution.
- Render Cache and Proxy Settings are well-chosen for Fusion-heavy work.
- Image Scaling settings protect against unintentional resizing — perfect for motion graphics and SVGs.
- Color Management aligns with YouTube standards (Rec.709 / Gamma 2.4).
- Audio targets -14 LUFS, YouTube’s normalization standard.
- Metadata & Path Mapping sections are intentionally blank — no problem there.

## Dimensions: UHD

```yML
# Project Pixel Dimensions
Screen Width: 3840  
Screen Height: 2160    

# Aspect Ratio
16:9
16 / 9 = 1.7777
9 / 16 = 0.5625
```

## Master Settings

### Timeline Format

* 4K Resolution
* Match YouTube's framerate.

```yaml
Timeline Resolution: 3840 x 2160 Ultra HD
Timeline Frame Rate: 60 FPS
PlayBack Frame Rate: 60 FPS
```

### Video Monitoring

During editing, improve performance of previews and playback. 

```yaml
Video Resolution: 1920 x 1080 HD
Format: 60p
SDI Configuration: Single Link  
Data Levels: Video  
Video Bit Depth: 10-bit  
Monitor Scaling: Bilinear  
```

### Optimized Media and Render Cache

During editing, improve the performance of previews & playback while maintaining good image quality.

```yaml
Proxy Media Resolution: Choose Automatically  
Proxy Media Format: DNxHR SQ  
Optimized Media Resolution: Choose Automatically  
Optimized Media Format: DNxHR SQ  
Render Cache Format: DNxHR SQ  
Enable Background Cache: True, 2 seconds  
Automatically Cache Transitions in User Mode: False  
Automatically Cache Composites in User Mode: False  
Automatically Cache Fusion Effects in User Mode: True  
```

### Frame Interpolation

Use defaults. 

```yaml
Retime Process: Nearest
Motion Estimation Mode: Standard Faster
Motion Range: Medium
```

## Image Scaling

### Image Scaling

```yaml
Resize Filter: Sharper
Override Input Scaling: False
Override Output Scaling: False
Deinterlace Quality: Normal
```

### Mismatched Resolution Files: Scaling Options 

Center Crop with No Resizing  

  * Keeps the original resolution of the file and crops any parts that exceed the frame. No scaling is applied.  
  * Best for: Preserving pixel-perfect graphics without auto-scaling.  

Scale Entire Image to Fit  

  * Scales the image proportionally so that it fits entirely within the frame, adding black bars if needed.  
  * Best for: Ensuring everything is visible without cropping.  

Scale Full Frame with Crop  

  * Scales the image proportionally until it fills the entire frame, cropping any excess.  
  * Best for: Filling the frame without black bars, even if some parts are cut off.  

Stretch Frame to All Corners  

  * Stretches the image non-proportionally to fill the frame, distorting its aspect ratio.  
  * Best for: Avoiding black bars when aspect ratio doesn't matter.  

### Input Scaling

Ensures that SVGs, images, and imported elements retain their original scale. 

```yaml
Mismatched Resolution Files: Center Crop with No Resizing
```

### Output Scaling

Ensures that final exports maintain the intended frame composition.

```yaml
Match Timeline Settings: True
Mismatched Resolution Files: Scale Entire Image to Fit
```

## Color Management

### Color Space and Transforms

Match Output Color to YouTube specs.

```yaml
Color Science: DaVinci YRGB  
Timeline Color Space: Rec.709 (Scene)  
Output Color Space: Rec.709 Gamma 2.4  
```

### Lookup Tables

Use defaults. 

```yaml
Input Lookup Table: No LUT
Output Lookup Table: No LUT
Video Monitor Lookup Table: No LUT
Color Viewer Lookup Table: Use Video monitoring selection
Scopes Lookup Table: Use Video monitoring selection
3D Lookup Table Interpolation: Tetrahedral 
```

## General Options

```yaml
```

## Camera Raw

```yaml
```

## Capture and Playback

```yaml
```

## Subtitles and Transcription

```yaml
```

## Fairlight

### Timeline Sample Rate

`48000` is standard for professionals and YouTube.

```yaml
Audio Sample Rate: 48000
```

### Bussing

```yaml
Use Fixed Bus Mapping: False
```

### Audio Metering

* IEC 60268-18: Metering standard that ensures consistent loudness measurement.
* Target Loudness Level: Match YouTube normalization standard, preventing level shifts.
* Loudness Scale: LUFS: Industry standard for measuring perceived loudness.
* Bus Meter Alignment Level: Align audio with proper loudness for streaming.
* Bus Meter High/Low Levels: Help visualize optimal audio ranges.

```yaml
Meter Type: IEC 60268-18
Level Detector: disabled
Scale: disabled
Decay: disabled
Peak Indicator: disabled
Pre Fade Metering on Tracks: False
Target Loudness Level: -14 LUFS  
Loudness Scale: LUFS  
Bus Meter Alignment Level: -14 dBFS  
Bus Meter High Level: -6 dBFS  
Bus Meter Low Level: -12 dBFS  
```

## Path Mapping

```yaml
```

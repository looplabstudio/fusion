# LoopLab Studio: DaVinci Resolve Fusion Support

Centralized support for all LoopLab Studio Fusion products.

small change

## Product Documentation

- [PAC Essentials](./LL_PAC_Essentials/README.md)
- [PAC Oscillate](./LL_PAC_Oscillate/README.md)
- [PAC Orbit](./LL_PAC_Orbit/README.md)
- [ACM Essentials](./LL_ACM_Essentials/README.md)

## How to Install DRFX Files

Typically, when you download effects, the download is a `.zip` containing a `.drfx` file, README, and LICENSE. Unzip this file to a convenient location. Navigate to this location in your file explorer.

1. Launch DaVinci Resolve.
1. In your file explorer, double-click the `.drfx` file.
1. DaVinci displays a confirmation prompt. Click `Install`.
1. Restart Resolve. Effects are ready to use.

LoopLab Studio tools are typically available on the Fusion page, in the Effects panel, under `Templates > Fusion > Effects > LoopLab Studio`.

## Feature Requests

Have a suggestion? We'd love to know! Please [submit an issue using the Feature Request template](https://github.com/looplabstudio/fusion/issues) telling us: 

- What procedural animation problem are you trying to solve?
- Is there a specialized tool you'd like to see?
- Can we improve any of our existing tools to better fit your workflow and goals?
- Is there something you'd like us to document better?

## Bug Reports

Every LoopLab Studio tool is thoroughly tested for mathematical accuracy and performance. 

Before submitting a bug report, please:
 
1. Exit Fusion and restart your device.
1. Fix red nodes - these usually indicate a typo in an `Expression` field.
1. Relink your `Transform` or other node to the tool's `Curve` link.
1. Double-check node wiring. 

If your project is complex, please perform a simplified test: 

1. Download the [test_fusion_comp.setting](../fusion/test-fusion-comp/README.md) file.
1. Start a new project and add a new Fusion comp.
1. Switch to the Fusion page and drag `test_fusion_comp.setting` to the canvas.
1. Add the LoopLab tool to the canvas. 
1. Link one of the `Test_` nodes to the tool's `Curve` and test. 

If the steps above do not resolve the issue, please [submit an issue using the Bug Report template](https://github.com/looplabstudio/fusion/issues) and we will do everything we can to remedy the problem.


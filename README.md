# AdMesh Unity SDK

AdMesh lets you place image or video ads on meshes in a Unity game.

This repo is the public Unity package only. It does not include private tools, internal publishing notes, or server-side business logic.

## What this package includes

- Unity runtime scripts for loading and showing ads
- an inspector for configuring placements in the Editor
- placeholder assets for testing
- a sample bootstrap script

## What you need before you start

- Unity `2022.3` or newer
- an AdMesh SDK key
- at least one AdMesh ad unit ID

## Install

### Option 1: Unity Package Manager

Open `Window > Package Manager`, choose `Add package from git URL`, and use this repo URL.

### Option 2: Local package

Copy this repo into your Unity project's `Packages/` folder and reference it as a local package.

## Quick start

### 1. Initialize the SDK once

Create a startup script and initialize AdMesh when your game starts:

```csharp
using AdMesh.Core;
using UnityEngine;

public sealed class GameBootstrap : MonoBehaviour
{
    private void Awake()
    {
        AdMeshPlugin.Initialize("YOUR_SDK_KEY");
    }
}
```

### 2. Add a placement

Add `AdMeshPlacementComponent` to any GameObject that has a `Renderer`.

Set these fields in the Inspector:

- `Ad Unit ID`
- `Ad Format`
- `Use Real Ads`

### 3. Test safely

Keep `Use Real Ads` turned off while you are building or testing your scene.

Turn it on only after:

- your SDK key is correct
- your ad unit is correct
- you are ready to request live ads

## Optional config file

You can also create `StreamingAssets/admesh_config.json` from the example file:

```json
{
  "sdkKey": "YOUR_SDK_KEY",
  "adSelectorUrl": "https://your-selector-endpoint",
  "eventCollectorUrl": "https://your-event-endpoint"
}
```

If you pass values directly to `AdMeshPlugin.Initialize(...)`, those values are used first.

## Supported media

- Images: `.png`, `.jpg`, `.jpeg`
- Video: `.mp4`

## Package layout

- `Runtime/` contains the runtime SDK code
- `Editor/` contains the Unity inspector tools
- `StreamingAssets/` contains the config template
- `Samples~/` contains a basic sample

## Notes

- This SDK is for fixed in-game ad surfaces.
- Ad delivery decisions are handled by AdMesh services.
- Server-side business rules are not stored in this package.

## Support

- Portal: https://dev.admesh.cloud
- Email: support@admesh.cloud

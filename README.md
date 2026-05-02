# AdMesh Unity SDK

Unity SDK for integrating image and video ad placements on in-game surfaces.

## What this package includes

- runtime code for requesting, loading, and rendering AdMesh placements
- Unity Editor inspectors for placement setup
- a configuration template in `StreamingAssets`
- a basic sample in `Samples~/BasicPlacement`

## Supported engine version

- Unity `2022.3` or newer

## Installation

### Unity Package Manager

Use `Add package from git URL` in the Unity Package Manager and point it to this repository.

### Local package

Copy the package into your project's `Packages/` folder and reference it as a local package.

## Quick start

Initialize the SDK once when your game starts:

```csharp
using AdMesh.Core;
using UnityEngine;

public sealed class GameBootstrap : MonoBehaviour
{
    private void Awake()
    {
        AdMeshPlugin.Initialize("YOUR_ADMESH_SDK_KEY");
    }
}
```

Then:

1. Add `AdMeshPlacementComponent` to a GameObject with a `Renderer`.
2. Set the `Ad Unit ID`.
3. Keep `Use Real Ads` disabled while validating the scene.
4. Configure fallback content if you want a custom development placeholder.

## Configuration

The package uses the public AdMesh production endpoints by default:

- `https://select.admesh.cloud`
- `https://events.admesh.cloud`

You can also provide a minimal config file at `StreamingAssets/admesh_config.json`:

```json
{
  "sdkKey": "YOUR_ADMESH_SDK_KEY"
}
```

## Test and fallback mode

- Keep `Use Real Ads` disabled during development and QA.
- Use fallback content while validating placement surfaces and layout.
- Enable live serving only after the app and ad unit are configured in AdMesh.

## Production setup

Before turning on live serving:

- create or select your app in AdMesh
- create the target ad unit
- verify your SDK key and ad unit ID
- validate the placement in a development build first

## Events and telemetry

When configured, the SDK may contact AdMesh services and send delivery, diagnostic, and heartbeat events required for ad serving, verification, reporting, and abuse prevention.

## Advanced configuration

Most integrations should use the default AdMesh production endpoints. Only override service URLs for approved staging or self-hosted testing workflows.

## Troubleshooting

- If a placement stays on fallback content, verify the SDK key and ad unit ID first.
- If a video placement does not play, confirm the source asset and renderer setup.
- If the package does not initialize from config, check the `StreamingAssets/admesh_config.json` location and JSON format.

## Links

- Website: [admesh.cloud](https://admesh.cloud)
- Developer Portal: [dev.admesh.cloud](https://dev.admesh.cloud)
- Privacy Notice: [PRIVACY.md](./PRIVACY.md)
- Terms: [TERMS.md](./TERMS.md)
- Third-Party Notices: [THIRD_PARTY_NOTICES.md](./THIRD_PARTY_NOTICES.md)
- Release Checklist: [PUBLIC_RELEASE_CHECKLIST.md](./PUBLIC_RELEASE_CHECKLIST.md)
- Release Process: [RELEASE_PROCESS.md](./RELEASE_PROCESS.md)

## License

Unless otherwise noted, AdMesh-authored source code in this repository is licensed under Apache-2.0. See [LICENSE](./LICENSE).

## Third-party notices

See [THIRD_PARTY_NOTICES.md](./THIRD_PARTY_NOTICES.md).

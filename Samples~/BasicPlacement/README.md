# Unity Sample: Basic Placement

This sample shows the minimum setup for a single AdMesh placement in Unity.

## Included files

- `GameBootstrap.cs` for one-time SDK initialization at startup

## Scene setup

1. Create an empty GameObject named `AdMeshBootstrap`.
2. Add `GameBootstrap` to it.
3. Add a plane or quad with a `Renderer`.
4. Add `AdMeshPlacementComponent` to that object.
5. Set:
   - `Ad Unit ID`
   - `Use Real Ads = false` while testing
   - optional fallback content

## What to verify

- the placement initializes without blocking the scene
- fallback content renders during development
- a live creative loads after valid app and ad unit configuration
- the game continues normally if AdMesh requests fail

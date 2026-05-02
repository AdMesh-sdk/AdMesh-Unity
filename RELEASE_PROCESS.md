# Release Process

Use this process when preparing a public AdMesh SDK release.

## 1. Align the version

- update the plugin/package version
- update the changelog
- confirm README examples still match the shipped API

## 2. Review public language

- remove internal, defensive, or placeholder wording
- confirm public URLs point to approved AdMesh destinations
- confirm README, PRIVACY, TERMS, and notices are current

## 3. Review release hygiene

- check for secrets and production credentials
- confirm third-party notices are still accurate
- confirm sample content still reflects supported integration patterns

## 4. Check git identity

- confirm the repo-local git identity is the approved public release identity
- confirm the release commit message uses the current format

## 5. Commit convention

Use commit messages like:

- `release(unity-sdk): prepare public SDK package [vX.Y.Z]`
- `docs(unity-sdk): clean README and legal notices [vX.Y.Z]`
- `fix(unity-sdk): align public package metadata [vX.Y.Z]`

## 6. Final gate

Do not push publicly until the repo is at least `PASS WITH WARNINGS` on:

- README quality
- license clarity
- third-party notices
- privacy/terms disclosure
- public URL hygiene
- version alignment
- git identity

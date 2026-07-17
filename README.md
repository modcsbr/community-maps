# modcsbr community maps

This repository catalogues optional community maps and map-related assets for `modcsbr`.

The initial catalogue contains payloads for four community maps. Redistribution for these initial entries is treated as `permission-granted` by the modcsbr project owner. Provenance, authorship, hashes, and known gaps are still documented per map so future maintainers can audit or replace files if better primary sources appear.

## Release packages

Every push to `main` runs GitHub Actions and creates a release containing:

- one ZIP per map, such as `cs_rio.zip`;
- `community-maps-full.zip` with the full catalogue;
- `manifest-index.json` with release asset metadata;
- `checksums.sha256` for release artifact validation.

Each per-map ZIP preserves the repository layout under `maps/<map-id>/`. The `modcsbr` development installer can download a release into its local `.downloads/` cache, validate hashes, and copy `maps/<map-id>/files/**` into the generated `runtime/xash3d/modcsbr` folder.

## Policy

- Every map must have a `manifest.json`.
- Every map must have a human-readable `README.md`.
- Every hosted binary must have SHA256, MD5, size in bytes, source URL, authorship notes, and redistribution status.
- Mirrors without clear credits are not enough for new binaries unless the project owner explicitly grants permission for inclusion.
- Files with unknown permission may be documented but must not be committed.
- Valve/Steam assets must not be committed.

## Layout

```text
maps/
  cs_rio/
    README.md
    manifest.json
    files/
      maps/
      gfx/
      sound/
schemas/
  map-manifest.schema.json
```

Each `files/` directory preserves the Counter-Strike relative paths expected by the map package.

## Status values

`redistribution`:

- `allowed`
- `permission-granted`
- `unknown`
- `not-allowed`
- `valve-owned`
- `remove`

`source_status`:

- `primary`
- `archived-primary`
- `community-preserved`
- `mirror-only`
- `unverified`

## Initial catalogue

- `cs_rio`: hosted; redistribution permission granted by project-owner decision; authorship has conflicting public reports.
- `de_sampa`: hosted; redistribution permission granted by project-owner decision; archived Mataleone page provides strong provenance.
- `fy_pool_day`: hosted; redistribution permission granted by project-owner decision; original author credited as Squall by community sources.
- `fy_poolparty`: hosted; redistribution permission granted by project-owner decision; original author credited as Squall by community sources.

## Related policy

See the main project policy draft:

- `modcsbr/specs/backlog/third-party-maps-and-assets-policy.md`

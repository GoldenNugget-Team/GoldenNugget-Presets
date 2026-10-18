# GoldenNugget Presets

The community preset catalog for [GoldenNugget](https://github.com/GoldenNugget-Team/GoldenNugget).
Open **Presets → Browse Catalog** in the app to see these presets, check how
risky each one is, preview it on a virtual iPhone and import it.

Importing only saves a preset. Nothing reaches your iPhone until you load the
preset and press Apply.

## Submitting a preset

The easy way is from the app:

1. Save your setup as a preset.
2. Select it on the Presets page and click **Submit to Catalog**.
3. Fill in the name, author and description, then click **Open GitHub**.
4. GitHub opens with the file already written. Click **Propose changes**, then
   **Create pull request**.

You need a GitHub account. GitHub makes a copy (fork) of this repository for
you automatically.

### By hand

Add one file to `presets/`. The file name is the preset's id: lowercase
letters, digits and dashes, for example `presets/solid-glass.json`.

```json
{
  "format": 1,
  "name": "Solid Glass",
  "author": "Your name",
  "description": "What it changes, in a sentence or two.",
  "ios_min": "26.0",
  "ios_max": "",
  "tags": ["liquid glass", "minimal"],
  "code": "GN1.…"
}
```

- `code` is the share code from **Share as QR → Copy Code** in the app.
- `ios_min` and `ios_max` are optional. `"18"` means every 18.x release.
- Up to 8 tags of at most 24 characters.
- Name up to 60 characters, author up to 40, description up to 500.
- Templates, icon themes and wallpapers are files on your computer, so they
  are never part of a share code.

## What happens to a pull request

A check runs on every pull request. It reports what is wrong, or shows a table
with each preset's tweak count and risk level. A pull request from someone
outside the team may only add or edit files in `presets/`.

A maintainer then reviews it. A preset is not merged when it:

- is a copy of an existing preset,
- turns off something important (for example thermal monitoring) without
  saying so clearly in the description,
- has a misleading name or description.

After a merge the catalog is published automatically and the app shows the
new preset the next time someone opens the catalog.

## For maintainers

- The check and the published `index.json` are built by
  `tools/preset_catalog.py` in the GoldenNugget repository, with the same
  rules the app applies when it reads the catalog.
- The check runs with `pull_request_target`, so a pull request cannot change
  its own check. It only reads the pull request's files as data.
- Settings → Pages → Source must be **GitHub Actions**.
- Protect `main`: require the **Check presets** status and one review.
- To remove a preset, delete its file on `main`.

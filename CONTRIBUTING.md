# Contributing to the GoldenNugget catalog

Thanks for sharing! Everything here appears in GoldenNugget's **Community
Catalog** after a maintainer reviews it. The [README](README.md) has the full
rules; this is the short version.

## Templates (`templates/*.batter`)

Use **[Batter Builder](https://github.com/GoldenNugget-Team/GoldenNugget-TemplateBuilder/releases/latest)**,
the visual editor for GoldenNugget templates:

1. Build the template: switches, sliders, text boxes and choice lists, no JSON
   by hand. The Check page shows the same problems this catalog's check would.
2. Click **Submit to Catalog**. It saves `<id>.batter` and opens the upload page.
3. Drop the file on the page, click **Propose changes**, then **Create pull request**.

If the pull request's check reports a problem, open the template in Batter
Builder, fix what its Check page lists and upload the file again.

Prefer to write `config.json` yourself? See
[the template documentation](https://github.com/GoldenNugget-Team/GoldenNugget/blob/main/documentation.md)
and check the file with `python nugget_cli.py wallpaper validate my-template.batter`.

## Presets (`presets/*.json`)

Submit them from GoldenNugget: select the preset on the Presets page and click
**Submit to Catalog**. The [README](README.md#submitting-a-preset) explains the
file format for submitting by hand.

## What gets reviewed

Every pull request is checked automatically, then reviewed. A submission is
not merged when it copies an existing one, turns off something important
without saying so, has a misleading name or description, or is a template
whose tweaks write somewhere its description does not explain.

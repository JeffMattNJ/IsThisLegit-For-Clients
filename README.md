# Is This Legit? — For Clients

Hosting repo for the **Is This Legit?** Outlook add-in (Matthijssen Business Systems). Works in classic Outlook, new Outlook and Outlook on the web.

**Live URL:** https://JeffMattNJ.github.io/IsThisLegit-For-Clients/taskpane.html

## Files

| File | Purpose |
|---|---|
| `taskpane.html` | The add-in UI and all 37 checks (footer: Version 1.0.5.1) |
| `commands.html` | FunctionFile the manifest requires (minimal; loads Office.js) |
| `icon-16.png`, `icon-32.png`, `icon-80.png` | Ribbon and store icons referenced by the manifest |
| `icon-128.png` | Spare high-res icon (not referenced by 1.0.5.1) |
| `manifest/manifest-1.0.5.1.xml` | Manifest to upload to each client tenant |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |

## Manifest rules

- GUID `7f3a9c2e-1b4d-4e8f-a6c0-2d5e9b3f7a1c`: never change it.
- Each upload to a tenant needs a higher version. Current version is **1.0.5.1**, so the next one is **1.0.5.2**.
- Save with no BOM and no CRLF. Validate with `npx office-addin-manifest validate <file>`.
- Admin Center → Settings → Integrated Apps → Is This Legit? → Update → **Upload manifest file from device**.
- When you change the version, update the `Version x.x.x.x` footer in `taskpane.html` to match.

## Pages setup

Settings → Pages → Source: **Deploy from a branch** → `main` / `(root)`.

# Is This Legit? — For Clients (PRODUCTION)

Production hosting for the **Is This Legit?** Outlook add-in (Matthijssen Business Systems). Every client tenant loads from here. Works in classic Outlook, new Outlook and Outlook on the web.

**Live URL:** https://JeffMattNJ.github.io/IsThisLegit-For-Clients/taskpane.html

> Do not test changes here. Test in [`domain-age-alert`](https://github.com/JeffMattNJ/domain-age-alert) first.

## Files

| File | Purpose |
|---|---|
| `taskpane.html` | The add-in UI and all 37 checks (footer: Version 1.0.5.1) |
| `commands.html` | FunctionFile the manifest requires (minimal; loads Office.js) |
| `icon-16.png`, `icon-32.png`, `icon-80.png` | Ribbon and store icons referenced by the manifest |
| `icon-128.png` | Spare high-res icon (not referenced) |
| `manifest-1.0.5.1.xml` | Production manifest, uploaded to every client tenant |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |

## Manifest rules

- Production GUID `7f3a9c2e-1b4d-4e8f-a6c0-2d5e9b3f7a1c`: never change it.
- Each upload to a tenant needs a higher version. Current version is **1.0.5.1**, so the next one is **1.0.5.2**.
- Save with no BOM and no CRLF. Validate with `npx office-addin-manifest validate <file>`.
- **Existing tenant:** Integrated Apps → Is This Legit? → Update → Upload manifest file from device.
- **New tenant:** Integrated Apps → Upload custom apps → upload from device → All users.
- When you change the version, update the `Version x.x.x.x` footer in `taskpane.html` to match.

## Promoting a tested change

1. Test it in `domain-age-alert` with the TEST add-in. The footer there shows **TEST BUILD**.
2. Copy the **same** `taskpane.html` here, without editing it. The TEST label only appears when the file is served from `domain-age-alert`.
3. Merge, wait about 60 seconds, then confirm the footer has no TEST label.

# Fusion Avatar Packs

Community-made profile pictures for Fusion. Create a pack, share one link, and anyone can use your avatars on their profiles, on iPhone, iPad, Mac and Apple TV.

## Add a pack to Fusion

1. Copy a pack link (a URL to a `.json` file — see [Packs](#packs) below or make your own).
2. In Fusion, go to **Settings → Profiles → Avatar Packs**, paste the link, and tap **Add**.

## Use an avatar on a profile

1. Go to **Settings → Profiles**, or the **Select Your Profile** screen at launch.
2. Hold a profile (long-press on iPhone/iPad, click-and-hold the touchpad on Apple TV, right-click on Mac).
3. Choose **Change Avatar** and pick an image from any of your packs. **Remove Avatar** switches back to the default icon.

Packs are shared by all profiles: add a pack once and every profile can pick from it. The pack list also syncs to your other devices via iCloud, and each profile's chosen avatar travels with the profile. Packs auto-refresh once a day, so when the creator adds new images you get them automatically.

## Create your own pack

A pack is a single JSON file. Host it anywhere that serves raw files — a GitHub repo is perfect.

**1. Make a repo and upload your images** (PNG or JPG, square works best — they're shown as rounded tiles).

**2. Add a `pack.json`:**

```json
{
  "title": "My Awesome Avatars",
  "images": [
    { "name": "Luffy",  "url": "https://raw.githubusercontent.com/you/your-repo/main/images/luffy.png" },
    { "name": "Zoro",   "url": "https://raw.githubusercontent.com/you/your-repo/main/images/zoro.png" },
    { "name": "Nami",   "url": "https://raw.githubusercontent.com/you/your-repo/main/images/nami.png" }
  ]
}
```

- `title` — the pack name shown in Fusion.
- `name` — the label under each avatar.
- `url` — a direct link to the image file.

A bare array also works if you skip the title:

```json
[
  { "name": "Luffy", "url": "https://…/luffy.png" }
]
```

**3. Share the raw link to your JSON.** On GitHub, open `pack.json` and press the **Raw** button — that URL is your pack link:

```
https://raw.githubusercontent.com/you/your-repo/main/pack.json
```

That's it. Anyone who adds this link gets your pack.

### Tips for creators

- **Square images, 256–512 px** are ideal — big enough for the Apple TV picker, small enough to load fast.
- **Keep image URLs stable.** Users who picked an avatar keep pointing at the URL they chose. If you must move files, keep the same `name` in the JSON — Fusion refreshes the pack daily and users re-picking will get the new URL.
- **Add images any time.** Just edit `pack.json`; every user's app picks up the change within a day (or instantly with the Refresh button).
- **Removing images** doesn't break anyone: a profile using a removed image keeps showing it from cache, and falls back to the default icon if the file disappears entirely.

## Packs

| Pack | Creator | Link |
|------|---------|------|
| Example Pack | @you | `https://raw.githubusercontent.com/…/pack.json` |

*Made a pack? Open a PR adding it to this table!*

## FAQ

**Do the images upload to Fusion's servers?** No — Fusion loads them straight from the creator's link and caches them on-device. There are no servers.

**What happens if a pack goes offline?** Avatars already in use keep displaying from cache; the pack just stops refreshing. Worst case a profile falls back to its default icon. Nothing breaks.

**Does removing a pack remove my avatar?** Your chosen avatar keeps its image (the URL is stored with the profile). Removing a pack only takes it out of the picker — for every profile, since packs are shared.

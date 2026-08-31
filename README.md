# FIC Field Photo — v1.5.1

Take photos of field issues on a company iPad, dictate a description with the
keyboard mic, and the description + date/time + job + name + FIC logo get
stamped onto each photo. Photos collect into the current SET; one Export sends
the whole set to the Photos library at once. Nothing is deleted at export —
the exported set is only cleared when you deliberately tap Start New Set (and
confirm), so a failed or cancelled export never loses photos. Works fully
offline after the first install; photos never leave the iPad until you export.

Files: `index.html` (the whole app), `sw.js` (offline cache), `icon.png`
(home-screen icon).

## One-time hosting setup (GitHub Pages, free)

1. Go to github.com and create a free account (this login is the key to
   updating the app — keep it in the password manager).
2. Click **New repository**. Name it `field-photo`, leave it **Public**,
   click **Create repository**.
3. Click **uploading an existing file**, drag in `index.html`, `sw.js`, and
   `icon.png`, click **Commit changes**.
4. Go to **Settings → Pages**. Under "Build and deployment", set Source to
   **Deploy from a branch**, branch **main**, folder **/ (root)**. Save.
5. After a minute or two the page shows the address, e.g.
   `https://YOURNAME.github.io/field-photo/`. That's the app.

Alternative: skip GitHub entirely by having whoever manages
farwestinsulation.com drop the same three files into a folder on the website —
the address becomes e.g. `farwestinsulation.com/fieldphoto/`.

## Installing on each iPad (once per iPad)

1. Open the address in **Safari** on the iPad (needs internet this one time).
2. Tap the **Share** button → **Add to Home Screen** → **Add**.
3. Open it from the home screen icon once while still online — after that
   first launch the app is cached and no longer needs service.
4. First photo: Safari will ask permission for the camera — tap Allow.

## Daily use

Enter job number and name once (the iPad remembers them). Tapping the job box
shows big buttons for the last few jobs — tap one instead of typing. Then per
issue: **Take Photo** → Apple camera → tap the description box → tap the
**mic key** on the keyboard and talk → green **✓ Save Photo** (grey ↺ Retake /
red ✕ Cancel). Repeat for every issue. When done: **Export Set** →
tap **Save Image** on the popup and the whole set lands in Photos at once.
Next visit: **Start New Set** (tap twice — it deletes the exported set), or
just take another photo to keep adding to the old set. Tap a thumbnail to get
**Edit note** (fix the description and re-stamp) or **Remove** (tap twice).
Botched set? **↻ Restart** (tap twice) clears all its photos and keeps the
job and name.
If unexported photos sit for more than a day, an orange warning shows at the
top until they're exported.

## Updating the app later

Replace `index.html` (and `sw.js` if it changed) in the GitHub repository —
Add file → Upload files → commit. Every iPad picks up the new version the next
time the app is opened with service; with no service it keeps running the
version it has. Bump the version number in both files when releasing.

## Notes / known limits

- Dictation runs on-device (works offline) on iPads with an A12 chip or newer
  (iPad 8th gen, Air 3, any 2018+ Pro, or later). Older iPads can still type.
- If a user cancels the export popup, nothing is marked exported and nothing
  can be deleted — just tap Export Set again.
- Re-exporting a set sends ALL its photos again (simple and predictable), so
  export once per set when possible.

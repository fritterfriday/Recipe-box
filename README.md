# Recipe Box — your personal, subscription-free cookbook

Recipe Box is a free, self-contained, open-source-style web app for iPhone, iPad, Mac and other devices. **No account, subscriptions, app store publishing, external JavaScript packages, or backend.** All of the app's source files are included here and can be modified freely.

## Features

- Add, edit, delete, search, sort, favorite and categorize recipes.
- Attach a photo from Photos or Files. Images are compressed before local storage.
- Save ingredients (one per line), directions (one step per line), notes, tags and source links.
- Scale ingredients for different numbers of servings (numeric amounts at the start of a line scale automatically).
- Add all ingredients for a recipe to a shopping list. Check items off; copy/share shopping list.
- Optional *manually entered* nutritional information per serving.
- Print recipes or copy a structured text version.
- Runs offline after a successful first online load, using a service worker.
- Export recipes, photos and shopping list to a single JSON backup; import/merge that backup on another device. Also export a self-contained readable HTML cookbook to open independently of the app.

**Important:** Recipes are stored on *each device's own* local browser/web-app data. The app **does not auto-sync between iPhone/iPad/Mac or to iCloud.** Export and import backup files to move them. **Do not delete the web app or clear its website data unless you have saved a current backup.** Device storage may be evicted by the operating system.

## Install with free GitHub Pages (easy, no ongoing fees)

1. Unzip the archive. You should see `index.html`, `app.js`, `styles.css`, `sw.js`, `manifest.webmanifest`, `.nojekyll`, and the `icons` directory.
2. Log into GitHub at https://github.com/ and create a new **Public** repository called `recipe-shelf` (or another name). On GitHub Free, Pages requires a public repository. Only your app's CODE is public; **do not upload any backups or personal recipes to your repository.**
3. In the repository, click **Add file > Upload files**. Upload all app files **including the icons directory** (and `.nojekyll` if your file manager shows it). Commit them to the main branch. Do not upload the ZIP itself as the site.
4. Go to **Settings > Pages > Build and deployment**. Select **Deploy from a branch**, `main`, `/(root)` and Save.
5. Open the website URL shown by GitHub Pages (usually `https://YOUR-USERNAME.github.io/recipe-box/`). Loading this URL serves the app files over HTTPS, which allows proper offline caching.
6. **iPhone / iPad:** In **Safari**, load that URL. Tap Page Menu or Share > Share > **Add to Home Screen**. Keep **Open as Web App** enabled and tap Add. Open it using its new Home Screen icon.
7. **Mac (macOS Sonoma or newer):** In Safari, load the URL, then **File > Add to Dock**. Or keep the site as a regular Safari tab.

GitHub is needed only for hosting the static app files, and the site remains available on the web even if your device is off. Your saved recipe data stays in local device storage and is not uploaded to GitHub. After the first online visit, you can use the installed app offline. Avoid posting sensitive information in the public *source code* or repository.

## Try it locally on your computer

Run from inside this folder:

```sh
python3 -m http.server 8765
```

Then open http://localhost:8765 in a browser. Safari and Chromium support the app. This is a local test environment; other phones cannot access `localhost` on your computer.

## Device-to-device transfers and backup

- Settings > **Export backup**. Save the `.json` download to the Files app > iCloud Drive, an external drive, or a computer.
- On your other device, open *its installed copy* of Recipe Box, then Settings > **Import backup**.
- Imports merge by recipe ID; matching records from the backup overwrite matching records on that device, and unmatched recipes remain.
- You should keep occasional dated exports even if you only use one device. **Important:** Safari and a Home Screen app can have *separate storage*. If you have already saved recipes in Safari before installing, export from Safari, then import from inside the Home Screen app.
- Photos are included as compressed JPEG data in each backup. Backups with many photos can be large.

## Source and licensing

All code is included, has no external runtime dependencies, and is free for personal or commercial use under the MIT License in `LICENSE`. You may edit, rehost or fork your copy at any time.

## Limitations in this version

- **No automatic iCloud sync**. Manual import/export is needed to transfer between devices.
- **No automatic extraction from Instagram or recipe websites, and no automatic OCR**. Enter or paste ingredients, instructions, and a source URL manually. Attach a food photo if you like.
- **No automatic macro calculation**. Optional calorie/protein/carb/fat fields are values you type in and should be verified against the actual ingredients.
- Storage can be cleared by the OS. Frequent backups matter, especially when changing phones or updating device software.

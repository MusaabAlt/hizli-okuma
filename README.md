# Hızlı Okuma Teknikleri — Web package

This folder is prepared to run the original Flash application in a modern browser using Ruffle.

## Files

- `index.html` — browser launcher
- `hizlioku_main.swf` — the main SWF extracted from the original Windows Flash projector (`hizlioku.exe`)
- `okumenu.swf` — external Flash menu loaded by the application
- `random.swf` — external Flash component loaded by the application
- `data.xml` — original application data; kept byte-for-byte in its legacy encoding
- `.nojekyll` — tells GitHub Pages not to process the site through Jekyll
- `.gitattributes` — keeps SWF/XML files byte-preserved by Git

The original `.exe` is not needed on the website.

## Publish with GitHub Pages

1. Create a new GitHub repository, for example `hizli-okuma`.
2. Upload **the contents of this folder** to the repository root. Do not upload only the ZIP.
3. Commit the files to the `main` branch.
4. Open **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**.
6. Select branch **main** and folder **/(root)**, then save.
7. After GitHub finishes deployment, open the Pages URL shown in Settings → Pages.

For a repository named `hizli-okuma`, the URL normally has this form:

`https://YOUR-USERNAME.github.io/hizli-okuma/`

## Important

The page loads Ruffle from its official npm CDN endpoint:

`https://unpkg.com/@ruffle-rs/ruffle`

The visitor therefore needs internet access to load Ruffle.

The application itself is old ActionScript/Flash content. The main movie is Flash version 9 and loads `okumenu.swf`, `random.swf`, and `data.xml` using relative paths. Keep those filenames in the same directory as `hizlioku_main.swf`.

The original application also uses Flash `FSCommand` actions such as fullscreen/quit. Browser behavior can differ from the old Windows projector for those commands, while the normal Flash interface may still work through Ruffle.

# FREQ by Porto Labs

The 15-slide FREQ deck as HTML/CSS and an offline Figma import plugin. This edition includes the simple Tap / Drag / Hold diagrams, Theo Bliss's portrait and Co-Founder · CPO role, and the corrected team biographies: Ex-Polymarket under Richard Melkonian, and Advertising at Apple / TBWA Media Arts Lab under Peter Xan.

## Open in Figma

1. Clone this repository or choose **Code → Download ZIP** and extract it.
2. Open Figma Desktop and create a blank **Design** file.
3. Choose **Plugins → Development → Import plugin from manifest**, then select `manifest.json`.
4. Run **FREQ Deck Import** from the development plugins menu.
5. Save or move the resulting Figma file into your team's project.

The importer creates 15 separate 1280 × 720 frames, with editable text, rectangles, circles and gesture vectors. Chrome artwork and photographs remain image layers. It runs offline and does not request network access. Re-running creates a new page and leaves your previous edits intact.

Install **Space Grotesk**, **IBM Plex Mono** and **Avenir Next** for the closest type match. Space Grotesk and IBM Plex Mono are open fonts available through Figma or Google Fonts. Avenir Next is not redistributed here; use your licensed installation. Missing fonts fall back to Inter and are reported when the import completes.

This is an import kit, not a binary `.fig` file or an already-created cloud Figma project. Figma import creates fixed-position slide frames, not responsive auto-layout components. Native Figma visual review is still required, especially if fonts are substituted. The root PDF (also in `reference/` inside the source archive) is the visual authority.

## Open the HTML deck

The root `index.html` is a single portable file with embedded CSS, fonts, images and presentation controls. Open it directly in a browser. For the editable source folder, extract `editable-source.zip` and run:

```sh
npm run dev
```

Then visit `http://localhost:8140`. Use **Present**, arrow keys and Escape. The HTML is real positioned text, CSS shapes, SVG gestures and image assets, not screenshots of PDF pages. Browser text metrics and rounded corners can differ slightly from the reference PDF.

## Edit and rebuild

Extract `editable-source.zip` first and run `npm run build` to regenerate the bundled Figma plugin. It contains the structured HTML/CSS source, assets, slide data and build scripts listed below.

- `source/slides.json`: slide copy, positions, colours, font sizes and image crops.
- `deck.css`: typography and browser layout.
- `assets/`: original photographs, chrome art, approved mark and web fonts.
- `figma/runtime.js`: editable native-node importer.
- `reference/FREQ-2026-10-20.pdf`: latest approved visual reference.

After editing the source data or importer, run `npm run build`. It updates `index.html` and embeds the assets and slide data into `figma/code.js`. No npm dependencies are required for the build or preview. HTML edits do not sync automatically with Figma; re-import the rebuilt plugin into a new page.

## Source and permissions

Published publicly at the founder's explicit request on 20 October 2026. Product screens are concepts, not proof of working pairing, generation or payments. Team biography additions are founder-supplied. Photography, brand assets, generated artwork and deck copy remain subject to their respective rights. Public repository access does not grant a general reuse licence. Open-font licences are in `FONT-LICENSES.txt`.

Figma API references: [plugin manifest](https://developers.figma.com/docs/plugins/manifest/), [fonts](https://developers.figma.com/docs/plugins/api/properties/figma-loadfontasync/), [images](https://developers.figma.com/docs/plugins/working-with-images/).

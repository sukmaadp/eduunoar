
WebAR Template — A-Frame + AR.js (marker-based)
=============================================

What you got here
-----------------
- index.html  -> Web page that launches camera AR using AR.js (A-Frame).
- angklung.glb -> Your uploaded 3D model (placed to appear on top of the marker).
- package.zip  -> This zip (if you downloaded as archive).

How to use (quick)
------------------
1. Extract all files to a folder and serve with a static server (recommended):
   - Python 3: `python -m http.server 8000` from the folder, then open `http://localhost:8000` on your phone/PC.
   - Or upload to any static host (Netlify, GitHub Pages, Vercel, Surge, etc.).

2. Open `index.html` on a mobile browser (Chrome on Android or Safari on iOS).
   Allow camera permission when asked.

3. Print or show the "Hiro" marker on another screen. The default marker used here is the AR.js preset 'hiro'.
   Example Hiro marker image (search "AR.js hiro marker") — it's a black-and-white square marker.
   Point your camera to the marker and your angklung model should appear above it.

Customizing
-----------
- Replace the model:
  Put any `.glb` file next to index.html and replace `angklung.glb` filename in the <a-entity> `gltf-model` attribute.

- Scale / position / rotation:
  Adjust `scale`, `position`, and `rotation` attributes in index.html to fit the marker size.

- Swap marker to a different preset:
  AR.js supports `hiro` (preset) and custom pattern markers. To use a custom marker pattern:
   1. Use `artoolkit` pattern generator (see AR.js docs) to create a `.patt` file from an image.
   2. Change `<a-marker preset="hiro">` to `<a-marker type="pattern" url="my-marker.patt">` and place `my-marker.patt` in the same folder.

Notes about image-target (real-card scanning)
--------------------------------------------
- If you want the AR to trigger by *any real-world image* (like your card front), AR.js uses NFT (image-tracking) which requires additional preprocessing (descriptor files).
- A simpler modern option is to use **mind-ar-js** (MindAR), which supports image targets and comes with an offline tool to generate a target file from your card image.
  - MindAR: https://hiukim.github.io/mind-ar-js-docs/
  - To use MindAR you will need to run the provided CLI tool to generate a `.mind` target file and then plug it into a MindAR scene. This template uses marker-based AR for easiest testing.

Extras / Next steps I can help with
-----------------------------------
- I can convert this template to use **MindAR image tracking** and prepare the `.mind` target if you give me the card image (front) now.
- I can also optimize the glb (reduce polycount, bake textures) for faster mobile performance.
- Or I can produce a QR-code + quick-host steps so users can scan a QR to open the AR page.

---
Enjoy! If you'd like, I can now:
A) Convert the template to MindAR image tracking (you must upload the card image), or
B) Tweak scale/position/animation of the angklung model and produce an updated index.html, or
C) Produce a ready-to-deploy ZIP for download (I already zipped below).

# Images

This folder holds images for the RiekeFest website. No images are included yet.

Place image files here and reference them from `index.html` / `css/style.css`
using relative paths like `images/filename.jpg`.

## Known placeholders in the site

The following places in `index.html` and `css/style.css` are marked with
`PLACEHOLDER` comments and are waiting for real images:

1. **George and Marcia Rieke photo** — About section (`#about`), the
   `.about-image.placeholder-box` block in `index.html`.
2. **Steward Observatory / Tucson photo** — Venue and Travel section
   (`#venue`), the `.venue-image.placeholder-box` block in `index.html`.
3. **Hero background** — currently a CSS-only starfield (no photo). To use a
   real astronomical image (e.g. a JWST or Spitzer mosaic, or an image of the
   Galactic Center) instead, add the image file here and set a
   `background-image` on the `.hero` rule in `css/style.css`.

## Suggested workflow to add an image

1. Copy the image file into this `images/` folder (e.g. `images/rieke-portrait.jpg`).
2. In `index.html`, replace the relevant placeholder `<div class="placeholder-box">`
   contents with an `<img>` tag, for example:

   ```html
   <div class="about-image">
     <img src="images/rieke-portrait.jpg" alt="George and Marcia Rieke">
   </div>
   ```

3. Only use images the organizers have rights to publish.

# RiekeFest 2027 Website

A simple, static website for **RiekeFest: The Growth of Infrared Astronomy
and Active Galaxies from the Galactic Center to the Edge of the Universe**
(March 15&ndash;19, 2027, Tucson, Arizona).

The site is plain HTML and CSS with no JavaScript, no build step, no
database, and no framework. It can be deployed by copying the folder onto
any web server.

## Files

```
riekefest/
├── index.html          Single-page site (Home, About, Program, Dates,
│                        Venue, Registration, Organizers, Contact)
├── css/
│   └── style.css        All styling, including CSS variables for colors
├── images/
│   └── README.md         Notes on where to add images
└── README.md             This file
```

## 1. Previewing locally

No build tools are required. Either:

- Double-click `index.html` to open it directly in a browser, or
- Serve the folder locally, e.g. from a terminal in this directory:

  ```
  python3 -m http.server 8000
  ```

  then open `http://localhost:8000` in a browser.

## 2. Changing dates and text

Most frequently-edited text lives directly in `index.html`, marked with
`<!-- EDIT HERE -->` comments. Key spots:

- **Hero section** (top of `index.html`, inside `<section id="top" class="hero">`):
  conference name, subtitle, dates, and location.
- **Important Dates table** (`<section id="dates">`): edit the right-hand
  column of the table — all values (registration opens, deadlines, venue,
  banquet) are in one place.
- Search the file for `To be announced` and `Coming soon` to find all
  currently-unknown details that need updating as information is confirmed.

## 3. Adding images

See [images/README.md](images/README.md) for full details. In short:

1. Copy an image file into `images/`.
2. Find the relevant `placeholder-box` in `index.html` (search for
   `PLACEHOLDER`) and replace its contents with an `<img>` tag pointing to
   the new file.

Images currently expected: a photo of George and Marcia Rieke (About
section), and a photo of Steward Observatory / Tucson / JWST / Spitzer
(Venue section). A hero background image can also be added by editing the
`.hero` rule in `css/style.css`.

## 4. Adding speakers and schedule entries

The Scientific Program section (`<section id="program">` in `index.html`)
currently lists topic areas only, with a "Detailed program and speaker list
coming soon" notice. Once a schedule is available:

1. Look for the HTML comment starting with `TEMPLATE: Individual talk entry`
   near the end of the program section.
2. Copy the `<div class="session">...</div>` block once per session, and the
   `<div class="talk">...</div>` block once per talk within a session.
3. Fill in the time, speaker, and title for each talk.
4. You can remove the "coming soon" placeholder paragraph once real content
   is added.

## 5. Changing the venue and registration information

- **Venue and Travel** (`<section id="venue">`): each subsection (Venue,
  Accommodation, Travel to Tucson, Local Transportation, Conference Banquet)
  currently says "Details coming soon." Replace each `<p>Details coming
  soon.</p>` with the real information as it becomes available.
- **Registration** (`<section id="registration">`): currently states that
  registration opens later in 2026 and lists placeholders (fee, deadline,
  abstract submission, dietary requirements, banquet attendance). Update the
  list items directly; add an actual registration form/link once the
  registration process is finalized.

## 6. Deploying to a basic Apache/Nginx web directory

Because the site is static, deployment is just a file copy:

1. Copy the entire `riekefest/` folder to the target location on the web
   server, e.g.:

   ```
   scp -r riekefest/ user@server:/var/www/html/riekefest
   ```

   or copy it into whatever document root Apache/Nginx is configured to
   serve (e.g. `/var/www/html/`, `/srv/www/`, or a subdirectory under the
   Steward Observatory web space).

2. No server configuration, database, or application server is required —
   any web server that can serve static files will work.

3. If the site is hosted at a sub-path (e.g.
   `https://example.edu/~irgroup/riekefest/`), all links and asset paths in
   this project are relative, so no changes should be needed.

## Notes

- No conference venue, registration process, or committee members beyond
  the LOC chair have been invented. All unknown details are explicitly
  marked "To be announced" or "Coming soon" and should be filled in as
  information becomes available.
- Colors, spacing, and other design values are controlled by CSS variables
  at the top of `css/style.css` under `:root`.

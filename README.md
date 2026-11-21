# Jorge Gallegos — Academic website (Nature / APS-inspired)

## Start
Open `index.html` locally or upload **all files and the `images/` directory** to the root of `gallegosjf2002.github.io` on GitHub Pages. Do not upload the old `.git/` folder. Navigation: Home → About → Research → Projects → Teaching → Certificates → CV → Contact.

## Customize the design
- `style.css`: `:root` contains colors, typography, widths. Main green is `--green: #087b62`.
- `site.js`: EN/ES language toggle (auto-selects browser language on first visit; remembers choice), animations, mobile navigation and image carousel.
- In each HTML page, add `data-en="English text" data-es="Texto español"` to a text element to translate it. Example: `<h3 data-en="New section" data-es="Nueva sección">New section</h3>`. Text without these attributes remains as written. This is a **bilingual site, not machine translation**; no API costs or unreliable automatic translations.
- For new pages, copy a current page, update the `<title>`, page intro and navigation in all pages. All pages currently use the same shared header/footer.

## Add certificates (Google Drive)
1. Upload the certificate PDF to Google Drive.
2. Right-click → Share → General access → **Anyone with the link** → Viewer. Only do this for certificates you intend to publish. Test in a private browser window.
3. Copy the direct file URL `https://drive.google.com/file/d/FILE_ID/view`.
4. Open `certificates-data.js`. Duplicate one object in `window.CERTIFICATES`, change `title`, `provider`, `year`, `status`, `category` (Physics, Astrophysics, Computing), and `links: [{"label":"Certificate","url":"https://drive.google.com/file/d/FILE_ID/view"}]`.
5. Add additional `links` objects for multiple PDFs from the same program. Entries without links display no dead buttons.
6. Save, commit and push. The filter/search gallery updates automatically.

**Google Drive note:** Google Drive is a file host, not a public certificate database. The site does not automatically enumerate private Drive folders. You can maintain certificates manually as above, or build a separate Google Apps Script/Drive API integration with appropriate permissions. Do not expose private Drive API credentials in a GitHub Pages repository.

## Add research papers and presentations
- `publications.html`: duplicate a `<article class="paper-card">` for a publication. Insert the **verified** DOI and direct preprint URL only when available.
- Duplicate a `<article class="conference-item">` for a talk or poster. Add a link with `<a class="text-link" href="https://drive.google.com/file/d/FILE_ID/view" target="_blank" rel="noopener noreferrer">Poster ↗</a>`.
- The preprint status is recorded as reported in the supplied CV; update when journal status changes.

## Add projects
- Duplicate a `<article class="project-card">` in `projects.html` and `index.html` (or later migrate projects to a JSON data file). Keep descriptions concise and include only verified links.

## Teaching materials and downloadable CV
- Put your own PDF at `docs/Jorge_Gallegos_CV.pdf` and add a download link to `cv.html`.
- Put course PDFs under `docs/` or use public Google Drive links. The previous `docs/class_notes.pdf` was **not present** in the uploaded archive, so no broken link is shown.

## Quality checklist
- Verify public links in an incognito browser.
- Confirm all image files exist (the old carousel contained a missing extension and a duplicate image; fixed here).
- Update research/preprint statuses and certificate completion statuses periodically.
- Test desktop and mobile, keyboard navigation, and EN/ES switch.
- Google Fonts require internet; local serif/sans-serif fallbacks are provided.

## Known limitations
- English/Spanish toggle translates tagged headings and descriptions. Proper names, some detailed research lists, bibliographic titles, certificate records and certain supporting text remain in their source language to preserve accuracy. For full bilingual coverage, add translated strings to all remaining elements.
- No backend, analytics, automated Google Drive synchronization or verified PDF CV is included.

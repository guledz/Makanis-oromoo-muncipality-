# Bulchiinsa Magaalaa Makkanniisa Oromoo: Municipality Website

Makkanniisa Oromoo City Administration, Oromia Region, East Hararghe Zone, Ethiopia.

A static, mobile-first municipal portal built as a single HTML page. It needs no server, build step, framework or internet connection.

## 1. Contents of this folder

| File | Description |
|---|---|
| `index.html` | The complete website (HTML, CSS and JavaScript). The logo and all 99 photos are embedded inside it, so it works even if opened alone. |
| `logo.png` | Municipality logo taken from the cover of the report. |
| `suuraa-002.jpg` to `suuraa-100.jpg` | The 99 field-documentation photos from the report's photo annex (Section 9), resized for web. Numbers follow the image order in the report. |
| `README.md` | This file. |

All files sit in the same folder with no subfolders.

## 2. How to open it

- **Locally:** double-click `index.html`. It opens in any modern browser (Chrome, Edge, Firefox, Safari, Android/iOS browsers).
- **Online:** upload the files to any static host.

### Deploy to GitHub Pages
1. Create a new GitHub repository.
2. Upload all files from this folder to the repository root.
3. Go to **Settings, then Pages**, choose **Deploy from a branch**, select `main` and `/ (root)`, and save.
4. The site will appear at `https://<username>.github.io/<repository>/`.

All paths are relative and navigation uses `#` links, so it also works from a GitHub Pages subdirectory.

## 3. Source of content

The only source is the uploaded report **"Gabaasa Raawwii Hojii Kurmaana 1ffaa Bara 2019"** (Q1 2019 Ethiopian calendar). Facts, statistics, project figures, captions and photos come from it.

Nothing official was invented. Information the report does not provide is shown as a clearly marked placeholder in square brackets, such as `[LAKKOOFSA BILBILAA]`.

## 4. Pages and features

The site is a single-page application with hash routing (`#home`, `#about`, and so on). The 11 pages are:

1. **Home:** hero image (a completed cluster building from the report), city statistics cards (population, land, houses, roads, water, electricity, telecom), the Q1 dashboard summary and report-based news items.
2. **Waa'ee Keenya (About):** location, history (founded 2017, 1 araddaa and 3 gooxii), boundaries, climate, institutions, houses and businesses, infrastructure, population tables, mission, vision, objectives and values. It also holds the administration section.
3. **Tajaajiloota (Services):** 10 service cards, each opening a validated request form (land, planning, revenue, housing support, education support, complaints, suggestions, service requests and information requests).
4. **Misooma / Pirojektoota (Projects):** the "Raawwii Misoomaa" dashboard with progress bars, the land/cluster cards (Livestock Cluster, Industry Shed, Main Market), the cluster building progress table and the buildings/infrastructure table.
5. **Oduu (News):** searchable news cards. The items are summaries of report findings, labelled with the report as their source.
6. **Beeksisa (Announcements):** a dedicated page for public notices, jobs, meetings, service interruptions and procurement. No announcements are entered yet.
7. **Galmee (Documents):** a searchable document list with metadata. It currently holds the Q1 2019 report.
8. **Suuraa (Gallery):** all 99 photos in the report's 10 categories, with category filters, a masonry layout, a lightbox (previous, next, Esc to close), captions and alt text.
9. **Komii (Complaints):** a complaint form with category, description, location, optional image, contact details and validation. It generates a reference number (`MKO-...`) and has a status lookup.
10. **Kaartaa (Map):** a placeholder list of map layers and a link to OpenStreetMap.
11. **Qunnamtii (Contact):** contact placeholders and a validated contact form.

The footer has quick links, social media placeholders and a copyright line.

## 5. Report data shown on the dashboard

All figures are labelled **Q1 2019** and kept as written in the report.

| Indicator | Plan | Actual | Performance |
|---|---|---|---|
| Revenue | Birr 568,942 | Birr 801,775 | 140.92% |
| Land allocation | 8.79 ha | 8.79 ha | 100% |
| Cluster buildings | 341 units | 48 units | 14.08% |
| Buildings/housing | 8 | 6 | 75% |

Further tables cover the Livestock Cluster (6.54 ha), Industry Shed (1.75 ha), Main Market (0.50 ha), the five building clusters (Furdiisa, Aannanii, Lukkuu, Industry Park, Main Market) and the four buildings (teachers' residences, traditional court, additional classroom, police committee house).

The report also states a government budget of Birr 2,767,827 (100%), annual budget performance of 28.97% and an overall performance of 98.3%. These are shown on the Projects page exactly as reported and have not been reconciled with the other figures.

## 6. Languages

- **Primary:** Afaan Oromoo
- **Secondary:** Amharic and English

The language selector in the header switches the navigation, hero text, button labels and section titles between the three languages. The translations live in the `T` object near the bottom of `index.html`; adding or editing text there makes more of the site translatable without redesigning it. Most page body text is currently in Afaan Oromoo (the report's language), with some English labels.

## 7. Design and accessibility

- Deep green main colour, gold accent, white and light grey backgrounds, dark charcoal text.
- Automatic dark mode through `prefers-color-scheme`.
- Mobile-first responsive layout with a hamburger menu on small screens.
- Sticky header, semantic HTML landmarks, visible keyboard focus, hover states, `aria` labels, alt text on all images, and form validation.
- Dark gradient behind hero text so it stays readable over the photo.
- Respects `prefers-reduced-motion`.
- Photos below the hero use lazy loading.
- SEO and Open Graph meta tags are included.

## 8. Placeholders (not in the report)

These are deliberately left unfilled. Replace them when verified information is available.

- Mayor and municipal leadership names, departments and responsibilities
- Municipality address, phone, email and office hours
- Map coordinates (no coordinates were invented)
- Social media links
- Download link for the report file
- Announcements

The meeting participants named in the report's meeting minutes are not used on the site, because their official municipal roles could not be confirmed.

## 9. TODO: backend and integration

The forms do not connect to any government system.

- **Service, complaint and contact forms:** demo only. Complaints are saved in the visitor's own browser (`localStorage`), so the status lookup only works on the same device and browser. Connect a real API or database before using this for real submissions.
- **Document download and PDF preview:** link the real file for each document, for example `<a href="report.pdf" download>`.
- **News and announcements:** connect a CMS or JSON file.
- **Map:** add verified coordinates and embed an OpenStreetMap or Leaflet map.
- **Project filters and photo galleries per project:** the full filterable project cards (agriculture, livestock, dairy, poultry, industry, market, education, housing, irrigation, roads, electricity, water) are not built yet.
- **Separate news detail pages, year filter and photo-to-project links** are not built yet.
- **Logo:** replace `logo.png` with the official version if one exists.

## 10. Editing tips

- Open `index.html` in any text editor. Statistics, tables and text are plain HTML and JavaScript arrays (`S`, `D`, `SV`, `N`).
- Photos are embedded as base64 inside the `G` array. To use the separate `suuraa-xxx.jpg` files instead, replace each `s:"data:image..."` value with the file name.
- The file is about 6 MB because of the embedded photos.

## 11. Credits and notes

- Content and photographs: *Gabaasa Raawwii Hojii Kurmaana 1ffaa Bara 2019*, Bulchiinsa Mana Qoppheessaa Guddatuu Makkanniisa Oromoo.
- Image captions are the report's own descriptions. Review them before public release.
- This site is not an official government publication until the municipality verifies and approves its content.

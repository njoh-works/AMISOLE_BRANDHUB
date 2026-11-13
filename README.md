# Amisolè Brand Hub

The Amisolè brand hub as a standalone static website: logo, colour, typography, art direction, templates, labels and trims, hats and downloads, on the brand's 4-column grid.

It's plain HTML, CSS and JavaScript, with no build step, framework or database.

## What's in the folder

| Path | What it is |
| --- | --- |
| `index.html` | The whole page: layout, styles and scripts |
| `content.json` | **Everything you edit:** headings, paragraphs, contact, links and the download list |
| `assets/logos/` | Master logo SVGs (wordmark, stacked, monogram, in Black and Paper) |
| `assets/caps/` | Product shots for the hats section |
| `assets/mood/` | Moodboard and landing photography |
| `fonts/` | Century Schoolbook BT Roman (self-hosted). Archivo loads from Google Fonts. |
| `_headers` | Keeps the hub out of search engines when it's hosted on Cloudflare Pages or Netlify |

## Editing content

Open `content.json`, change the text, and save. The change goes live with the next deploy.

- **`text`**: every editable heading and paragraph. Each key matches a `data-edit` attribute in `index.html`. Example: `"hero.updated": "Last updated 12 November 2026"`.
- **`links.assetFolder`**: the shared asset folder (Google Drive, Dropbox or SharePoint). This one link drives "Open the asset folder" and every logo's "Download" link.
- **`links.deck`** and **`links.guidelines`**: optional links shown in the templates section and the footer. Leave them empty to hide them.
- **`downloads`**: the rows of the download table. Each row needs a `title`, `type`, `updated` and `url`. Rows without a `url` are hidden.

To change a photo, replace the file in `assets/` with one of the same name, or update its path in `index.html`.

## Hosting with a partner login

The recommended setup keeps the files in a private GitHub repository, deploys them automatically, and puts an email login in front of the site.

1. **GitHub:** create a private repository and upload the contents of this folder to it.
2. **Cloudflare Pages:** create a project and connect the repository. Use "None" as the framework preset, leave the build command empty, and set the output directory to `/`. Every change to the repository then redeploys the site automatically.
3. **Custom domain:** in the Pages project, add a domain such as `brand.amisole.com`.
4. **Partner login (Cloudflare Zero Trust → Access):**
   - Add a self-hosted application for that domain.
   - Add a policy that allows specific partner email addresses, or whole partner domains such as `@partnerstore.com`.
   - Partners enter their email, receive a one-time code, and see the hub. They don't need an account anywhere.

Netlify or Vercel work the same way, using their own password or SSO protection.

## Before sharing outside the company

- **Photography:** the images in `assets/mood/` are references taken from the brand deck's moodboard. They're cleared for internal use only. Replace them with commissioned or licensed Amisolè photography first.
- **Century Schoolbook BT:** this is a commercial Bitstream/Monotype typeface, and the supplied files are flagged for restricted embedding. Confirm the licence covers web use before the hub goes live.

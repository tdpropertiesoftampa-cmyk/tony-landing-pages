# Tony Damiano Landing Pages

Four mobile-first lead magnet pages. Plain HTML and CSS, no build step.

| Page | File | Lead magnet |
|---|---|---|
| Flip investors | `flip.html` | Flip Deal Checklist |
| Land and lot investors | `land.html` | Land Deal Checklist |
| New construction buyers | `build.html` | New Construction Buyer List |
| As-is sellers | `as-is.html` | As-Is Seller Prep Guide |

`index.html` is a private list of the four links (it is set to noindex).

## 1. Turn on GitHub Pages

1. Merge this branch into `main` (or choose this branch in the next step).
2. On GitHub, open the repo, then **Settings**, then **Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Pick your branch (`main`) and the folder `/ (root)`, then click **Save**.
5. Wait a minute or two. The page shows your live address, usually `https://YOUR-USERNAME.github.io/tony-landing-pages/`.
6. Your short links will be that address plus the file name, for example `.../flip.html`.

Tracking tip: add `?src=` to any link, for example `flip.html?src=instagram`. The value is saved with each lead.

## 2. Replace the logo and photo

Put your real files in the `assets` folder using these exact names:

- `assets/logo-toplisting-exp.png` (footer logo)
- `assets/tony.jpg` (square photo works best, at least 320 by 320 pixels)

On GitHub: open the `assets` folder, click **Add file**, then **Upload files**, and commit. Until you do, the images show as empty slots.

## 3. Connect the form endpoints

1. Open `config.js`.
2. Replace each `https://REPLACE-ME.example.com/...` with the form URL from your CRM or form service (one per page: `flip`, `land`, `build`, `asis`).
3. Save and commit.

Each submission sends these fields: `first_name`, `email`, `phone`, `consent`, `lead_magnet`, `tag`, `source`, and `page_url`. If you use a Zapier Catch Hook, the page sends the lead without waiting for a reply (Zapier does not send one browsers can read), so it shows the thank-you message once the request is sent. Your service must accept a cross-origin POST (CORS) and answer with a success status. Until you replace the placeholders, the form shows the friendly error with Tony's phone number instead of the thank-you message.

The pages say the download is on its way, so set up an automatic email or text that delivers the checklist when a lead comes in. The checklists themselves are not in this repo yet.

## 4. Add your own domain later

1. Buy or pick a domain (or subdomain such as `go.yourdomain.com`).
2. In **Settings, Pages, Custom domain**, enter it and save. GitHub adds a `CNAME` file for you.
3. At your domain provider, add the DNS record GitHub shows. For a subdomain, add a `CNAME` record pointing to `YOUR-USERNAME.github.io`. For a root domain, add the `A` records listed in GitHub's Pages help.
4. Back in Pages, tick **Enforce HTTPS** once it becomes available.

## Checklist PDFs

The four checklist PDFs live in the `d` folder, inside a folder with a long random name. The link is not listed anywhere and `robots.txt` asks search engines to skip it, but anyone who has a link can open the file. To update a checklist, upload a new PDF with the same file name to that folder on GitHub.

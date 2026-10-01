# Word Of Mouth Plumbing LLC — site v2

Fresh static website for **Mike Rahm / Word Of Mouth Plumbing LLC**.  
Built to **leave Wix Premium** (no monthly site host fee). This repo is the free host: GitHub Pages, deploy from branch `main`, folder `/` (root). Keep `womplumbing.com` at the registrar (~$10–20/year — domain only, not a website plan).

**Do not change DNS for womplumbing.com until Mike APPROVES a cutover. Do not cancel Wix.**

`index.html` is at the repository root (not inside a `wom-site-v2/` folder). There is no `CUTOVER.md` in this build; cutover steps are in this README and still require Mike’s approval.

## Pages switch (still needs an admin)

The site files are on `main`. GitHub Pages is **not enabled yet**. The token that pushed this repo cannot change Settings → Pages (the API returns 403, and a GitHub Actions attempt failed the same way). A repository admin has to do this once:

1. Open [Settings → Pages](https://github.com/WOMP27DEBUG/plumbing-website-one-/settings/pages).
2. Source: **Deploy from a branch**.
3. Branch: **main**. Folder: **/ (root)**. Save.
4. Do **not** enter a custom domain on that screen.

Free preview after that save (staging only — `womplumbing.com` stays on Wix):

https://womp27debug.github.io/plumbing-website-one-/

## Business (locked)

| Field | Value |
|--------|--------|
| Name | Word Of Mouth Plumbing LLC |
| Phone | (845) 476-9348 |
| Email | wordofmouthplumbing27@gmail.com |
| NAP | 577 Goshen Tpk, Middletown, NY 10941 |
| Domain (later) | womplumbing.com |
| Hours | Emergency Mon–Fri (24/7); Sat 9:00 AM–3:00 PM; Sun closed |
| Focus | Emergency, heat/boiler, water heaters, drains/frozen pipes |

## Pages

| File | Purpose |
|------|---------|
| `index.html` | Home — winter CTAs above the fold |
| `emergency.html` | Emergency plumber Middletown NY |
| `boiler-heat.html` | Boiler / heat |
| `water-heaters.html` | Water heater repair & replace |
| `drains.html` | Drains & frozen pipes |
| `service-area.html` | Towns + NAP |
| `about.html` | Owner-operated / insured |
| `contact.html` | Phone, SMS, email, hours |

Phone click-to-call is in the **top bar**, **header CTA**, **hero**, and (on mobile) a **sticky Call / Text bar**. No fake reviews. No competitor names.

## Preview on the box

```bash
python3 -m http.server 8765
```

Open: `http://127.0.0.1:8765/` (or the box browser at that URL).

Optional: `python3 -m http.server 8765 --bind 0.0.0.0`

## Cost honesty: free site host ≠ free domain

| Piece | Typical cost |
|--------|----------------|
| **This site (HTML/CSS/JS)** | Free to host on GitHub Pages or Cloudflare Pages |
| **womplumbing.com registration** | ~$10–20 / year at the registrar (GoDaddy, Namecheap, Cloudflare Registrar, Google Domains successor, etc.) |
| **Wix Premium** | Cancel after DNS points at the new host and search/GBP look healthy (Mike APPROVE) |

You still pay for the **domain name**. You do **not** need Wix (or any paid website builder) to run this static site.

---

## Free host path A — GitHub Pages (recommended simple)

1. Create a GitHub account (free) if needed.
2. New repo, e.g. `womplumbing-site` (public for free project Pages, or private with GitHub free limits as applicable).
3. Site files are already at this repo root (`index.html` next to this README). Do not nest them in a subfolder.
4. **Settings → Pages →** Deploy from branch `main` (root), or use GitHub Actions static HTML.
5. Wait for `https://<user>.github.io/womplumbing-site/` to load and test phone links on mobile.
6. **Custom domain:** Pages → Custom domain → `womplumbing.com` (+ `www` if desired). GitHub shows the DNS records to add.
7. At the **domain registrar** (not Wix), set:
   - **A records** for `@` to GitHub Pages IPs (current list is in GitHub Docs: “Managing a custom domain for your GitHub Pages site”), **or**
   - **CNAME** for `www` → `<user>.github.io`
8. Enable **Enforce HTTPS** in Pages once DNS validates.
9. Only then: cancel Wix Premium / remove Wix DNS when Mike confirms the new site is live.

## Free host path B — Cloudflare Pages

1. Free Cloudflare account; add or transfer DNS for `womplumbing.com` (optional but clean).
2. **Workers & Pages → Create →** Upload assets, or connect a Git repo containing this folder.
3. Build command: none (static). Output directory: `/` (project root).
4. **Custom domains →** attach `womplumbing.com` and `www`.
5. Cloudflare provisions HTTPS. Point registrar nameservers to Cloudflare **or** add the CNAME/A records Cloudflare shows.
6. Test, then leave Wix when ready.

## Migrate off live Wix (later — APPROVE required)

1. Preview and approve content on this v2 site.
2. Pick GitHub Pages **or** Cloudflare Pages; deploy a staging URL first.
3. Update Google Business Profile website URL only after the custom domain serves this site on HTTPS.
4. At registrar: change DNS from Wix to GitHub/Cloudflare (steps above). TTL: lower to 300s a day before cutover if possible.
5. Keep Wix paid for a short overlap (e.g. 1–2 weeks) so rollback is possible.
6. Submit `https://womplumbing.com/sitemap.xml` in Google Search Console.
7. Cancel Wix Premium after traffic/calls look normal — **stops the monthly site fee**; keep paying only domain (~$10–20/yr).

## Local file map

```
index.html … contact.html
css/styles.css
js/site.js
brand/          # logos from prior pack
img/            # job + GBP photos
robots.txt
sitemap.xml
README.md
.nojekyll       # serve files as-is (skip Jekyll)
```

## Out of scope (this build)

- No Wix publish / editor changes  
- No DNS or registrar changes until Mike APPROVES  
- No fake reviews or competitor mentions  

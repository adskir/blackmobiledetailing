# Black Mobile Detailing — blackmobiledetailing.com

Static landing page for Black Mobile Detailing (Siarhei Khrantsou), mobile car detailing in Toronto & GTA.
Built and maintained by [ClickBari](https://clickbari.it).

## Structure

| File | Purpose |
|---|---|
| `index.html` | The whole site (HTML + inline CSS/JS) |
| `privacy-policy.html` | Privacy policy (PIPEDA), linked from footer and cookie banner |
| `*.webp` | Images (hero, service cards, case photos, reviews, portrait) |
| `sitemap.xml`, `robots.txt` | SEO |

No build step: what is in `main` is exactly what is served.

## Deploy

Hosting: OVHcloud Web Hosting (`ladycas.cluster021.hosting.ovh.net`), multisite folder `blackmobiledetailing`.
OVH native Git integration pulls `main` on every push (webhook). Push to `main` → live in ~1 min.

## Form

Booking form posts to Formspree (`https://formspree.io/f/mlgkbbkv`, ClickBari account).
Submissions arrive at the ClickBari inbox with subject "New booking request — Black Mobile Detailing".
Spam protection: Formspree honeypot field `_gotcha`.

## DNS (Namecheap BasicDNS)

| Type | Host | Value |
|---|---|---|
| A | @ | 94.23.69.227 |
| A | www | 94.23.69.227 |
| AAAA | @ | 2001:41d0:301:11::21 |
| TXT | ovhcontrol | OZJ2IcJIZUKGaFGAZKP7fA |

## TODO

- [ ] Enable Let's Encrypt SSL in OVH (after DNS propagates)
- [ ] Add `www.blackmobiledetailing.com` to the OVH site
- [ ] Add `.htaccess` redirect → `https://www.` (only after SSL is active)
- [ ] Test the form after go-live (check Formspree allowed domains)

# Psycho Scaling — landing page

Static site (plain HTML/CSS/JS, no build step). Upload these files as they are to any static host (GitHub Pages, Netlify, Vercel, your own server).

## Pages

| File | What it is |
|---|---|
| `index.html` | The landing page. Every "Book My Free Scaling Call" button opens `book-a-call.html` and carries the ad's UTM tags along. |
| `book-a-call.html` | Booking page: headline, the ₹5L disclaimer and your Calendly (`founders-psychoscaling/call-with-shashwat`). After a booking it opens `thank-you.html`. |
| `thank-you.html` | Shown after a booking. Holds the founders' thank-you video. |
| `privacy-policy.html`, `terms-and-conditions.html` | Legal pages linked in the footer. |
| `Content/` | Images used by the pages. Keep the folder name and paths as they are. |

## Still to set before going live

Settings live in the `CONFIG` block near the bottom of each page.

1. **Meta Pixel — set (`1667189860954273`).** Events: `index.html` → PageView · `book-a-call.html` → PageView + Lead · `thank-you.html` → PageView + Schedule (once per visit, so a refresh doesn't count a second booking). Add `?preview=1` to any page URL to test it without firing the pixel. Check the events once in Events Manager → Test events after going live.
2. **Thank-you video:** `VIDEO` in `thank-you.html` (`type: 'youtube'` with the video ID, or `'mp4'` with a file path).
3. **Calendly redirect:** the booking page already sends people to `thank-you.html`. Keep Calendly's own "redirect to an external site" setting **off**, or bookings get counted twice.
4. **Calendly questions:** add the booking questions from the doc "Calendly Bookings → Google Sheet (Zap)", Part 2 ("Calendly on its own"), so every booking arrives with the brand's details.

## Hosting on GitHub Pages with your own subdomain

See the doc "How to host your website on GitHub" in the shared Drive folder. In short: put these files in your repository's `main` branch → Settings → Pages → Deploy from branch `main` / root → add your subdomain → point a CNAME record at `<your-github-username>.github.io` in your DNS.

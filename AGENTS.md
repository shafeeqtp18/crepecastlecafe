# Base44 Setup Notes

## Project
Static restaurant website (Crepe Castle Cafe) — pure HTML/CSS/JS with one PHP form handler (`php/form-process.php`). No build system, no framework, no package manager.

## Running
Served with PHP's built-in dev server (`php -S 0.0.0.0:3000 -t /app`) via `docker-compose.base44.yml`. The repo is bind-mounted at `/app`, so edits to HTML/CSS/JS/PHP appear immediately on refresh — no rebuild needed.

## Verification
- `curl http://localhost:3000/index.html` should return the homepage HTML.
- Pages: `index.html`, `menu.html`, `about.html`, `gallery.html`, `contact.html`, `reservation.html`, `stuff.html`.

## Notes
- The contact/reservation form posts to `php/form-process.php`, which calls PHP `mail()`. This requires a configured SMTP server to actually send email; without one the form submission returns an error but the site renders fully. No external credentials are required to boot.
- `CNAME` points at `www.crepecastlecafe.com` (GitHub Pages artifact, irrelevant to local dev).

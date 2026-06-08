# My Recommendation — Marketing Website

Static marketing website for the **REC App** (My Recommendation), a community-driven platform for discovering and recommending service professionals.

Live on GitHub Pages.

---

## Pages

| File | URL | Description |
|------|-----|-------------|
| `index.html` | `/` | Home page |
| `our-services.html` | `/our-services.html` | Service categories overview |
| `app-info.html` | `/app-info.html` | App features and carousel |
| `about-us.html` | `/about-us.html` | Who We Are / mission |
| `terms.html` | `/terms.html` | Terms and Conditions |
| `services/yoga-instructor.html` | `/services/yoga-instructor.html` | Yoga Instructor service page |
| `services/nail-technician.html` | `/services/nail-technician.html` | Nail Technician service page |
| `services/bartender.html` | `/services/bartender.html` | Bartender service page |
| `services/golf-cart.html` | `/services/golf-cart.html` | Golf Beverage Cart Attendant page |

---

## Project Structure

```
myrecweb/
├── index.html
├── our-services.html
├── app-info.html
├── about-us.html
├── terms.html
├── style.css            # Shared stylesheet used by all pages
├── components.js        # Shared header and footer injected into every page
├── services/
│   ├── yoga-instructor.html
│   ├── nail-technician.html
│   ├── bartender.html
│   └── golf-cart.html
└── images/
    ├── shared/          # Logo, how-it-works icons
    ├── home/            # Home page images
    ├── our-services/    # Service category images
    └── app-info/        # App carousel images
```

---

## Architecture

### Shared Header & Footer (`components.js`)
All pages include a single `<script src="components.js">` (or `../components.js` for pages in `/services/`). The script injects the full header navigation and footer into placeholder `<div>` elements:

```html
<div id="site-header"></div>
<!-- page content -->
<div id="site-footer"></div>
<script src="components.js"></script>
```

To update the nav or footer across all 9 pages, edit **only `components.js`**.

### Shared Styles (`style.css`)
All global styles — reset, tokens, buttons, header, footer, mailing list, dropup — live in `style.css`. Page-specific styles are kept in an inline `<style>` block within each HTML file.

---

## Making Changes

**Add a new nav link:** Edit the `components.js` header and mobile menu sections.

**Change the footer:** Edit the `components.js` footer section.

**Add a new service page:** 
1. Create `services/your-service.html` using an existing service page as a template.
2. Add a card to `our-services.html`.
3. Add the link to the nav dropdown and mobile menu in `components.js`.

**Update global styles:** Edit `style.css`.

---

## Deployment

The site is deployed via **GitHub Pages** directly from the `main` branch. Push to `main` to deploy — no build step required.

```bash
git add .
git commit -m "your message"
git push
```

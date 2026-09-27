# Toy Haven

A front-end e-commerce website for collectible figurines, toys, board games and diecast model cars, built with vanilla HTML5, CSS3 and JavaScript (no frameworks, no backend). Built as a university front-end web development assignment.

## Tech Stack

- HTML5 (semantic elements)
- CSS3 (Flexbox, Grid, custom properties, media queries, animations)
- Vanilla JavaScript (DOM APIs, `localStorage`, `IntersectionObserver`)
- No React/Vue/Angular/Bootstrap/Tailwind/jQuery/PHP/backend/database

## File Structure

```
Toy-Haven/
├── index.html
├── products.html
├── cart.html
├── checkout.html
├── wishlist.html
├── feedback.html
├── css/style.css
├── css/redesign.css  (updated colour palette)
├── css/layout.css    (new homepage, navigation and catalogue structure)
├── js/
│   ├── main.js        (shared nav/cart/wishlist utilities + home page logic)
│   ├── products.js     (product data + products.html logic)
│   ├── cart.js
│   ├── checkout.js
│   ├── wishlist.js
│   └── feedback.js
├── images/
│   ├── logo.png, banner1-4.jpg
│   └── products/ (22 product images)
├── manifest.json
├── sw.js               (service worker for offline caching)
├── favicon.ico
└── README.md
```

## How to Run Locally

Because the site uses `fetch`-like relative paths and a service worker, it should be served over `http://`, not opened directly as a `file://` URL.

**Option A — VS Code Live Server**
1. Open the `Toy-Haven` folder in VS Code.
2. Install the "Live Server" extension.
3. Right-click `index.html` → "Open with Live Server".

**Option B — Python's built-in server**
```bash
cd Toy-Haven
python3 -m http.server 8000
```
Then visit `http://localhost:8000` in your browser.

**Option C — just double-click `index.html`**
This works for browsing the site, but the service worker won't register (browsers block SW on `file://`); everything else still functions normally.

## How to Test Each Feature

| Feature | How to test |
|---|---|
| Hamburger menu | Resize the browser below 768px width, click the hamburger icon — it should animate and reveal the nav links. |
| Hero slider | Watch the homepage banner auto-advance every ~4.5s; use the arrow buttons and dots; hover over it to pause. |
| Category cards | Click a category card on the homepage — you'll land on Products pre-filtered to that category. |
| Search | On Products, type a product name into the search box — the grid updates instantly. |
| Filter | Choose a category in the horizontal category bar — the grid updates without a page reload. |
| Sort | Use the sort dropdown on Products (price, name, rating). |
| Product modal | Click "View" on any card — a modal opens; close with the X, an outside click, or the Escape key. |
| Product of the Day | Visible on the homepage; the pick is based on today's date and stays the same all day. |
| Add to Cart / Wishlist | Click the respective buttons on any card, in the modal, or on Product of the Day. |
| Cart quantities | On Cart, use +/− or type directly in the quantity box; totals recalculate live. |
| Cart persistence | Add items, refresh the page — the cart is unchanged (stored in `localStorage`). |
| Checkout validation | Submit the checkout form empty, then with a bad email — inline error messages appear. |
| Order placement | Fill the form correctly and submit — an animated success message with an order number appears, and the cart clears. |
| Order history | Check `localStorage` key `toyHavenOrders` in DevTools → Application tab after checking out. |
| Wishlist statuses | On Wishlist, change an item's status dropdown (Interested/Owned/Not Interested) and use the filter pills. |
| Newsletter | Submit an invalid email on the homepage newsletter form, then a valid one — success message appears. |
| Feedback form | Submit the form on Support with an empty field, then correctly — a confirmation message appears. |
| FAQ accordion | Click any FAQ question on Support — it expands/collapses with a smooth animation. |
| Reduced motion | Enable "Reduce motion" in your OS accessibility settings — animations shorten automatically. |

## Recommended External Testing (per assignment brief)

- **HTML validation**: https://validator.w3.org/ (paste each page's HTML or its URL once hosted).
- **CSS validation**: https://jigsaw.w3.org/css-validator/
- **Accessibility**: https://wave.webaim.org/ (test each page once hosted, or via the WAVE browser extension).
- **Lighthouse**: Chrome DevTools → Lighthouse tab → run for both Mobile and Desktop, checking Performance, Accessibility, Best Practices and SEO.
- **Responsive testing**: Chrome DevTools → Device Toolbar, test at common breakpoints (360px, 768px, 1024px, 1440px).

## How to Upload to GitHub

1. Create a new repository on GitHub, e.g. `toy-haven`.
2. In the `Toy-Haven` project folder:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Toy Haven website"
   git branch -M main
   git remote add origin https://github.com/USERNAME/toy-haven.git
   git push -u origin main
   ```

## How to Enable GitHub Pages

1. On GitHub, open your repository → **Settings** → **Pages**.
2. Under "Build and deployment", set **Source** to "Deploy from a branch".
3. Choose the `main` branch and the `/ (root)` folder, then **Save**.
4. After a minute, your site will be live at:
   `https://USERNAME.github.io/toy-haven/`

All CSS, JS and image paths in this project are relative, so the site works correctly at that nested URL.

## Notes

- All product images are original placeholder graphics generated for this project (not copied from any existing website).
- The checkout process is a simulation only — no real payment is processed and no backend/database is used; everything is stored in the browser's `localStorage`.

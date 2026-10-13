# MK Store - Clothing E-Commerce

A frontend-only online clothing store built for the MTech Solutions Frontend Development Internship, Batch 01, Task 02.
MK Store sells everyday clothing: tops, bottoms, outerwear and accessories.

## Pages (hash routing, every page is directly linkable)
| Page | Route |
|---|---|
| Home | `#/` |
| Shop | `#/shop` |
| Product details | `#/product/<id>` |
| About | `#/about` |
| Contact | `#/contact` |
| Cart | `#/cart` |
| Checkout | `#/checkout` (confirmation at `#/order`) |

## Features
- 10 products in 4 categories (Tops, Bottoms, Outerwear, Accessories), each with ID, name, category, price, image, description and specifications.
- Shop: search, category filter and sorting (name / price) working together, live result count, "Clear Filters" empty state.
- Product page: breadcrumbs, large image, size selector, quantity (whole numbers, minimum 1), Add to Cart, related products, friendly "not found" state. Add to Cart asks for a size first.
- Sizes: clothing S, M, L, XL; jeans and chinos 28 to 36; cap and scarf are one size. On product cards, Add to Cart opens a size popup (one-size items add directly).
- Cart: add, increase, decrease, remove, line totals, subtotal, delivery and total. The same product in different sizes is a separate row; the same size increases quantity. Badge shows total units. Saved in localStorage; bad or outdated saved data is ignored safely.
- Checkout: validated shipping form, order summary, "Place Order" and a confirmation page with an order reference. No card or payment fields.
- Contact: validated form with a confirmation message.
- Responsive (mobile, tablet, desktop), keyboard accessible, visible focus states, announced cart and form messages, reduced-motion support. Dark tech theme (navy and electric blue) with a custom circle cursor on mouse devices.

## Motion
- Hero: intro fade-up, slow zoom, gradient shimmer on the headline and parallax on scroll.
- "Build the look": a pinned scroll section where hoodie, jeans and cap fly in and assemble as you scroll.
- Cards, categories and services reveal with a stagger and tilt in 3D with a light glow under the mouse.
- A scrolling text strip that speeds up with scroll speed.
- All of it switches off with `prefers-reduced-motion`.

## Technologies
HTML in `index.html`, CSS in `css/style.css`, JavaScript in `js/script.js`. No build step, no dependencies. Fonts (Sora, Inter) load from Google Fonts with system fallbacks.

## Run
Open `index.html` in a browser, or run `npx serve .` (keep all files and folders together).

## Money and delivery
Prices are stored as whole integers (paisa) and shown as `Rs 2,490`. Delivery is a flat Rs 250, free on orders of Rs 10,000 or more. The same rule applies in cart, checkout and confirmation.

## Product images
Real photos (WebP, 4:5) live in `assets/photos/`. To change one, replace the file or edit that product's `img` path in the `IMG` map at the top of `script.js`.

## Limitations
- Frontend only: no backend, database, accounts, email or payment processing.
- Larger sizes cost slightly more (S/28 base price, up to +Rs 200 for XL/36). Product cards show "From" the base price.
- Stock levels are not tracked: every size is always available.

## Deployment
Not deployed or pushed yet. The folder is static and deploys as is.
- Netlify: drag the folder onto https://app.netlify.com/drop, or `npx netlify deploy --prod --dir .`
- Vercel: `npx vercel --prod` (framework preset: Other, no build command).
- GitHub: `git init && git add . && git commit -m "MK Store"`, create a repository, then push.

## Structure
```
MK-STORE/
├── index.html            page markup
├── css/
│   └── style.css         all styles
├── js/
│   └── script.js         data, logic, routing, motion
├── assets/
│   ├── logo.svg          MK Store logo and favicon
│   └── photos/           product, hero, promo and about photos (WebP)
└── README.md
```

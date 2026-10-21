# TechNova

A responsive electronics storefront built as a frontend portfolio project. It demonstrates React component design, routing, catalog search and filters, context-based cart state, browser persistence, and accessible form patterns.

> **Demo only:** Product descriptions, prices, stock, and ratings are sample data. Checkout does not process payment or create a real order. Contact and newsletter forms do not transmit data.

## Features

- Responsive home, catalog, product detail, cart, checkout, about, contact, and custom 404 pages
- Search, category and price filters, and price/rating sorting
- Eight electronics categories in a local fallback catalog
- Product detail routes, related products, quantity controls, and discounts
- Cart powered by Context API and `useReducer`, persisted safely in LocalStorage
- Derived subtotal, sample shipping, and estimated total
- Validated demo checkout with local confirmation; no payment fields
- Contact and newsletter form feedback without backend transmission
- Loading, retry, empty, and fallback catalog states
- Responsive menu, semantic landmarks, keyboard focus styling, and lazy-loaded catalog images

## Stack

React 19, Vite 8, JavaScript, Tailwind CSS 4, React Router DOM 7, Lucide React, Fetch API, and LocalStorage. Exact dependency resolutions are recorded in `package-lock.json`.

## Run locally

```bash
npm install
npm run dev
```

Create a production build with `npm run build`; preview it using `npm run preview`.

## Project structure

```text
src/
├── context/CartContext.jsx
├── data/products.js
├── hooks/useProducts.js
├── services/productService.js
├── utils/money.js
├── App.jsx
├── main.jsx
└── index.css
```

The pages and shared layout/product/cart components are grouped in `App.jsx` for this initial teaching milestone. As the next refactor, split them into the `components/` and `pages/` folders described in the project brief.

## Screenshots

Add screenshots after running the app locally, for example:

- `docs/screenshots/home-desktop.png`
- `docs/screenshots/catalog-mobile.png`

## Links

- Live demo: _Add your Vercel or Netlify URL_
- GitHub repository: _Add your repository URL_

## GitHub setup

From this project folder, run:

```bash
git init
git add .
git commit -m "Build TechNova electronics storefront"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/technova-storefront.git
git push -u origin main
```

## Deploy

**Vercel:** Import the GitHub repository, keep the Vite defaults (`npm run build`, output `dist`), and deploy. For direct links to nested routes, configure the host to serve `index.html` as the SPA fallback.

**Netlify:** Import the repository with build command `npm run build` and publish directory `dist`. Add an SPA redirect rule (`/* /index.html 200`) so product detail routes work on refresh.

No API keys or secrets are required. The catalog service calls the public DummyJSON Products API (`https://dummyjson.com/products?limit=100`) and normalizes available laptop, smartphone, tablet, and mobile accessory products, then adds sample data for categories missing from that source. If the request fails, the complete local catalog is used.

## Known limitations

- This is a frontend demonstration. There is no backend, authentication, inventory system, order transmission, or payment processing.
- API products may not represent a complete electronics catalog; the curated local dataset fills category coverage.
- Product ratings and review counts are explicitly demo values and should not be treated as verified customer reviews.
- Product images load from Unsplash and require an internet connection.
- The initial implementation keeps route components together in `src/App.jsx`; splitting the larger file into focused modules is a useful next mentoring exercise.

## Future improvements

- Split page and component modules into the planned architecture
- Add automated component and interaction tests
- Replace sample catalog content with an electronics API whose terms support the intended use
- Add image fallbacks, persistent wishlist, and accessible filter panels
- Add real backend services only as a separate, clearly scoped project phase


API documentation: [DummyJSON Products API](https://dummyjson.com/docs/products).

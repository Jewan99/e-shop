# ElectroHub

A front-end e-commerce site for electronics (laptops, audio, cameras, wearables,
smart home, and components), built with React, React Router, and Vite.

## Features

- **Home page** — hero section plus "highest rated" and "just added" product rails
- **Shop page** — full catalog with category tabs, text search, price-range filter, and sorting
- **Product detail page** — full spec sheet, quantity selector, add to cart
- **Cart** — quantity editing, line removal, live subtotal/shipping/tax/total, free-shipping threshold
- **Checkout** — shipping + payment form (UI only — no real payment is processed) and an order summary
- **Order confirmation** — generated order number and total
- Cart state is kept in React Context and persisted to `localStorage`, so it survives a page refresh
- 20 mock products across 6 categories in `src/data/products.js` — edit this file to change the catalog

## Getting started

```bash
npm install
npm run dev
```

Then open the local URL Vite prints (usually `http://localhost:5173`).

To build for production:

```bash
npm run build
npm run preview
```

## Project structure

```
src/
  components/     Navbar, Footer, CategoryBar, ProductCard
  context/        CartContext (cart state + localStorage persistence)
  data/           products.js — the product catalog (mock data)
  pages/          Home, Shop, ProductDetail, Cart, Checkout, OrderConfirmation, NotFound
  App.jsx         Route definitions
  main.jsx        App entry point
  index.css       Design tokens + all styling (no external CSS framework)
```

## Notes on extending this

This is a front-end-only demo — there's no backend, database, or real payment
processing. To turn it into a production store, you'd typically add:

- A backend/API (or a service like Stripe + a headless commerce platform) for
  real inventory, orders, and payments
- User accounts and order history
- Real product images instead of the emoji placeholders in `getIcon()`
- Server-side validation for the checkout form

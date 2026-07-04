# Waypost — Hotel Explorer

A React + Vite frontend for the Demo Hotels API (`https://demohotelsapi.pythonanywhere.com/hotels/`).

## Features

- Live data fetched from the Hotels API on load (500 hotels), normalized once in `src/api/hotelsApi.js`
- Search by hotel name or city (debounced)
- Filter by city, max price, and minimum rating
- Sort by price (low/high) or rating
- Client-side pagination (12 hotels per page)
- Hotel detail slide-over with a photo gallery
- Mock booking flow with date/guest selection and a confirmation screen
- Wishlist ("Saved" stays) persisted to `localStorage`
- Loading skeletons, empty state, and error state with retry
- Fully responsive, keyboard-accessible (Escape closes the detail panel, visible focus states)

## Project structure

```
src/
  api/hotelsApi.js       API client + response normalization
  components/            Presentational + interactive UI pieces
  context/               WishlistContext (localStorage-backed)
  hooks/                 useHotels (data/filter/sort/paginate), useDebounce
  utils/format.js        Currency + rating formatting
  App.jsx                Page composition
  main.jsx               React entry point
  index.css              Design system (tokens, layout, components)
```

## Getting started

```bash
npm install
npm run dev
```

Then open the printed local URL (defaults to http://localhost:5173).

## Build for production

```bash
npm run build
npm run preview
```

## Notes

- All booking and confirmation data is client-side only — the Hotels API is read-only, so "Confirm booking" simulates a reservation and does not call any write endpoint.

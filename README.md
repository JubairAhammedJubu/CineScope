# CineScope — Movie Explorer

A responsive, animated movie/show explorer built with React, Vite,
Tailwind CSS v4, and Framer Motion, using the
[TVMaze API](https://www.tvmaze.com/api) for data.

## Features

- **Home page** — animated hero with a floating poster collage pulled
  from top-rated shows, a 3-step "how it works" section, and a
  horizontally scrollable "Trending now" strip.
- **Movie listing page** — live search by title (debounced against the
  TVMaze search endpoint), animated skeleton loaders while the catalog
  loads, a results count, empty/error states, and a responsive
  2–5 column grid of animated show cards (poster, rating badge, title,
  year, genre, "See details").
- **Details modal** — rendered via a portal with a spring scale-in
  animation, backdrop blur, backdrop image, synopsis, rating, release
  year, genres, and network. Closable via the ✕ button, the Escape
  key, or clicking outside the modal.
- Scroll-aware navbar (shrinks + blurs on scroll) with an animated
  mobile menu.
- Fully responsive: single column on mobile, up to 5 columns on large
  desktop screens; reduced-motion is respected for anyone with that
  OS setting on.

## Tech stack

- React 19 + Vite
- React Router
- Tailwind CSS v4
- Framer Motion
- TVMaze REST API (no key required)

## Getting started

```bash
npm install
npm run dev
```

Then open the printed local URL in your browser.

## Build for production

```bash
npm run build
npm run preview
```

## Deploying

This is a static Vite app — it deploys to Vercel, Netlify, or GitHub
Pages with zero configuration (build command `npm run build`, output
directory `dist`).

## Project structure

```
src/
  components/
    Navbar.jsx        Scroll-aware nav with animated mobile menu
    Footer.jsx
    SearchBar.jsx      Debounced input with loading + clear states
    MovieCard.jsx      Poster card with hover reveal + image fallback
    MovieModal.jsx     Portal-rendered details modal (Framer Motion)
    PosterStack.jsx    Floating poster collage used in the hero
  pages/
    Home.jsx
    Listing.jsx
  utils/api.js         TVMaze API calls + small helpers
```

## Card & modal design

- **Movie cards** use a subtle 3D tilt that follows the cursor, a
  cursor-tracking spotlight over the poster, an animated circular
  rating gauge, and a film-ticket-style perforated divider between
  the poster and the info panel.
- **Details modal** uses a two-panel layout (poster on the left,
  scrollable details on the right), a large animated rating ring,
  staggered genre chips, and a small stats grid pulled straight from
  TVMaze (premiere year, network, runtime, schedule, language,
  rating).

# 3D Galaxy Page

An interactive 3D galaxy visualizer rendered in the browser with WebGL. A procedural particle system generates a spiral galaxy of up to 100,000 points that you can rotate, zoom, and restyle live through an on-screen control panel.

## Features

- **Procedural galaxy generation** — spiral galaxy built from particles with configurable particle count (up to 100k), point size, radius, arm count, spin, and randomness (amount + power)
- **Live color mixing** — set inner and outer galaxy colors; particles are color-interpolated along the radius from core to edge
- **Interactive control panel** — sliders and inputs to tune every generation parameter in real time, plus a reset-to-defaults button
- **Orbit controls** — drag to rotate, scroll to zoom, right-drag to pan
- **Animated starscape** — drei `Stars` background, night-environment lighting, and a smooth loading screen while the scene initializes
- **Dark space theme** — full-viewport canvas with Tailwind/shadcn UI overlay

## Tech Stack

- [Next.js 15](https://nextjs.org) (App Router) + React 19 + TypeScript
- [three.js](https://threejs.org) via [@react-three/fiber](https://docs.pmnd.rs/react-three-fiber) and [@react-three/drei](https://github.com/pmndrs/drei)
- [Tailwind CSS 3](https://tailwindcss.com) + [shadcn/ui](https://ui.shadcn.com) components
- [Lucide](https://lucide.dev) icons
- Originally generated with [v0.app](https://v0.app)

## Quick Start

```bash
# install dependencies (npm or pnpm)
npm install
# or: pnpm install

# run the dev server
npm run dev

# open http://localhost:3000
```

Build for production:

```bash
npm run build
npm start
```

## Project Structure

```
3-d-galaxy-page-r5/
├── app/
│   ├── page.tsx        # GalaxyViewer — main scene (Canvas, lights, state)
│   ├── layout.tsx      # Root layout (theme provider, fonts)
│   └── globals.css     # Tailwind base styles
├── components/
│   ├── galaxy.tsx            # Procedural THREE.Points galaxy generator
│   ├── galaxy-controls.tsx   # Live parameter panel (sliders, reset)
│   ├── loading-screen.tsx    # Splash shown while the scene loads
│   └── ui/                   # shadcn/ui primitives (button, card, slider…)
├── lib/
│   └── utils.ts        # cn() helper
├── public/             # Static placeholder assets
└── styles/             # Extra global styles
```

## Environment Variables

None required. Everything renders client-side in the browser.

## Deployment Notes

This is a Next.js App Router application (no static export configured), so it needs a Node.js server runtime such as [Vercel](https://vercel.com), [Netlify](https://netlify.com), or any Node host:

```bash
npm install
npm run build
npm start
```

The build ignores lint and TypeScript errors by design (`next.config.mjs`), so production builds complete even with unused-variable warnings.

---

Built by Girish Lade · https://ladestack.in

# Allied Manufacturing Group — Website

A static React + Vite + Tailwind site (no backend, no database needed).

## Run locally in VS Code

```bash
npm install
npm run dev
```

Open http://localhost:5173

## Build

```bash
npm run build
```

Output goes to `dist/`. Preview it locally with `npm run preview`.

## Deploy to Vercel

1. Push this folder to a GitHub repo.
2. In Vercel, "Add New Project" → import the repo.
3. Framework preset: **Vite**. Build command: `npm run build`. Output directory: `dist`.
4. Deploy. `vercel.json` is already included so client-side routes (e.g. `/services`, `/about`) work correctly on direct load/refresh.

No environment variables are required.

## Adding your logo image

The logo is currently a text/CSS mark (the "A" square + wordmark) built in the `Logo()` component near the top of `src/App.tsx`. To switch to an image file:

1. Drop your logo file into the `public/` folder, e.g. `public/logo.png` (or `.svg`).
2. In `src/App.tsx`, find `function Logo({ light=false })` and replace its contents with an `<img>` tag, e.g.:
   ```tsx
   function Logo({ light=false }: { light?: boolean }) {
     return <img src={light ? '/logo-white.png' : '/logo.png'} alt="Allied Manufacturing Group" className="h-10 w-auto" />;
   }
   ```
   If you only have one version of the logo that works on both light and dark backgrounds, just use one `src` and drop the `light` ternary.

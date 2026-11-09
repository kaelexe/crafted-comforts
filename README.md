# Crafted Comforts

Responsive crochet portfolio inspired by the supplied Figma overview. React + TypeScript + Tailwind CSS 4, built with Vite. Includes an automatically moving hero with pause control and reduced-motion support, category filtering, accessible native gallery dialogs, mobile navigation, and a configurable email inquiry form.

## Run locally

Requires Node.js 22 or newer.

```sh
npm ci
npm run dev
```

## Docker

```sh
docker compose up --build -d
```

Visit http://localhost:8080. Stop with `docker compose down`. The multi-stage image builds the frontend and serves the production output with Nginx. No development server or Node runtime is included in the final image.

## Configure before launch

- The public Figma overview was visible, but original photo exports and precise design measurements were not available. Current artwork is explicitly labeled illustrative placeholder content; titles and copy are draft content. Replace `Artwork` in `src/App.tsx` with actual image elements pointing at photos under `public/creations/`, then update each piece's title, category, and description.
- Copy `.env.example` to `.env`, set `VITE_CONTACT_EMAIL` to the owner's actual email, and rebuild. Vite values are public build-time configuration, so do not put secrets there. The form opens the visitor's mail app; it does not send or store messages on a server. Without an email, it visibly remains a demo.
- Replace the draft about copy with the owner's own story and check the final photos' alternative text.

## Verify

```sh
npm run build
docker compose config
```

The build performs TypeScript checking before generating `dist/`. The Docker container includes an HTTP health check. Figma reference: https://www.figma.com/design/dfRGTlavtil0z8y9kfkLCn/Crafted-Comforts?node-id=0-1

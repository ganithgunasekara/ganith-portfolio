# Ganith Gunasekara — Portfolio

A responsive cyberpunk personal portfolio built with Next.js, React, TypeScript, Tailwind CSS, Framer Motion, Three.js, Lucide and EmailJS.

## Run locally

```bash
npm install
npm run dev
```

Open the local URL printed by Next.js.

## Quality checks

```bash
npm run typecheck
npm run build
```

The site uses Next.js static export. After `npm run build`, deployable static files are in `out/`.

## EmailJS setup

1. Copy `.env.example` to `.env.local`.
2. Set `NEXT_PUBLIC_SITE_URL` to the final site URL for correct social-sharing metadata.
3. Add your EmailJS service ID, template ID and public key.
4. Set `NEXT_PUBLIC_CONTACT_EMAIL` only if you want a public email link in the contact section.
5. Configure the EmailJS template to accept `from_name`, `from_email`, `subject` and `message`.
6. Restart the development server after changing environment variables.

No credentials are committed. If EmailJS is not configured, the form validates input but reports that direct sending is unavailable rather than showing false success.

## Replace personal assets

- **Portraits:** replace `public/images/portrait-placeholder.svg` with a professional image. Keep the same filename to update both hero and about sections. A 4:5 portrait works best. If using a JPG or PNG, update both image paths in `components/hero.tsx` and `components/about.tsx`.
- **CV:** replace `public/ganith-gunasekara-cv.pdf` with your latest CV using the same filename. The download buttons require no code changes.
- **Project previews:** replace the SVG files in `public/projects/` with actual screenshots, then update the `image` paths in `data/portfolio.ts`. A 4:3 screenshot works best; 1200 × 900 px is recommended.
- **Project links:** add real repository and demo URLs to the project data and render them in `components/projects.tsx`. Placeholder text is intentionally non-clickable until real URLs exist.
- **Social and content data:** edit `data/portfolio.ts`.

## Vercel

Import the repository into Vercel and keep the default Next.js detection. Use `npm run build` as the build command and `out` as the output directory if prompted. Add the EmailJS environment variables in the Vercel project settings. The static export is also compatible with other static hosts.

## Accessibility and performance

The site includes keyboard-operable dialogs and tabs, visible focus states, a skip link, reduced-motion support, responsive touch targets, semantic content outside the decorative canvas, and a static fallback for the 3D portrait system.

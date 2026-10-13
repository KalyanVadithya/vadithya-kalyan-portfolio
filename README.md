# Vadithya Kalyan — developer portfolio

A responsive React + TypeScript portfolio with a custom IDE-inspired workspace, Motion animations, project case studies, and browser-local interactions. No backend or API keys are needed.

## Cinematic glassmorphism edition

The current design adds translucent frosted panels, cyan/violet light fields, staged title and code entrances, typewriter positioning, animated file tabs and project filtering, and glass case-study dialogs. Use the motion control in the header to disable animation; the OS reduced-motion preference is also respected.

`src/CinematicWorkspace.tsx` owns the interactive IDE, safe simulated terminal, file viewer, architecture inspector, and animation replay. `src/cinematic.css` is the glassmorphism layer loaded after the base styles. Terminal commands are limited to `help`, `about`, `projects`, `contact`, and `clear`; they never execute shell code.

The complete local project is provided at `C:\Users\Dhanush\StudioProjects\vadithya-kalyan-portfolio`, including installed dependencies and the production build. Open that folder in your editor and run `npm run dev`. You can also run `node node_modules/vite/bin/vite.js --host 127.0.0.1` directly.

The cinematic update was checked at 1440, 390, and 320 CSS pixels. File selection, terminal help and unknown-command handling, architecture controls, motion pause, project filters, and case-study dialogs were checked. The development preview reported a Vite hot-reload WebSocket warning; this feature is not part of the production build.

## Run locally

Use Node.js 20.19+ or 22+.

```sh
npm ci
npm run dev
```

## Production

```sh
npm run build
npm run preview
```

The build performs a strict TypeScript check and emits the static website into `dist/`. Deploy that directory to any static web host. All section links are page anchors; no server rewrite is needed.

On this Windows environment the global npm command shim did not resolve properly when launched by the Sites helper. The equivalent command used successfully was `node "C:/Program Files/nodejs/node_modules/npm/bin/npm-cli.js" run build`. Vite also required execution outside the filesystem sandbox because native realpath calls were blocked.

## Edit content

- `src/data.ts`: profile, social links, projects, technical goals, skills, education settings.
- `src/App.tsx`: reusable workspace, project visualizations, dialogs, sections, and command palette.
- `src/styles.css`: theme tokens, responsive layouts, motion preferences, and presentation.
- `public/`: favicon, sharing image, sitemap, and crawler policy.

Email and résumé are empty and their actions are hidden. Add real values to `profile.email` and `profile.resume` to enable them. Keep résumé PDFs in `public/` and use their root-relative path.

CGPA visibility defaults to false. The Surrey entry also defaults to hidden: confirm the current enrolment status and dates, then update its wording before enabling it. Hidden configuration is still part of the downloadable JavaScript, so do not store confidential information in frontend source.

Eight project/workstream entries preserve the supplied software project descriptions. Full-stack development is presented as a connecting capability, not an invented ninth finished application. The latest attached brief excludes hardware manufacturing and board design. All feature goals are distinguished from verified implementation; only the Website Generator's previously used Perplexity API is stated as supplied implementation history.

GitHub inspection found `calculator`, `CLUB`, and `tribeshub`. These do not match the featured projects; no unrelated repository links were substituted. The GitHub and LinkedIn profile links use the exact supplied accounts.

## Interactions

- Ctrl/Cmd+K or the header command button: search and navigate commands.
- Arrow keys + Enter in the command palette; Escape closes dialogs.
- Project category filters; eight detailed case studies with selectable architecture stages.
- Architecture playback is explicitly a concept simulation, not a live integration.
- Desktop file explorer and mobile file selector open read-only, syntax-highlighted files.
- Keyboard-operated skills tabs, responsive mobile menu, light/dark theme persistence.
- Reduced-motion CSS and Motion configuration disable/reduce animation.

## Verification

- TypeScript check and Vite production build passed.
- Browser rendering checked at 1440, 390, and 320 CSS pixels; no page-width overflow detected.
- All six project filters checked, including the correct visible project sets.
- Case study opening/closing, Escape, stage selection, command search, Ctrl+K, mobile menu, file selection, theme switching, and keyboard skills tabs checked.
- Browser console contained no warnings or errors during interaction checks.
- Social destinations inspected in the rendered links. No message or form was submitted.
- Reduced-motion support inspected in source; a separate OS-level reduced-motion session was not run.
- No automated screen-reader audit or Lighthouse audit was performed.
- Vite emits benign dependency `use client` directive warnings for Motion; these do not prevent the static build.

## Hosting

Deploy the `dist/` folder to any static host. After you have a public domain, update the canonical and Open Graph URLs in `index.html`, and the sitemap entries in `public/sitemap.xml` and `public/robots.txt`.

The Google Fonts stylesheet is optional at runtime; local sans-serif and monospaced fallbacks are configured. No analytics or visitor tracking is included.

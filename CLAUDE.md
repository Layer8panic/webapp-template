# CLAUDE.md

Template per web app **statiche, solo client-side**, pubblicate su GitHub Pages.

## Hosting
- URL finale: `https://layer8panic.github.io/<nome-repo>/` (sottocartella, non root del dominio).
- Nessun backend, nessun server-side rendering, nessuna API route. Solo HTML/CSS/JS statici.
- Dati persistenti: `localStorage`/`IndexedDB` o API pubbliche esterne chiamate dal browser. Mai segreti o chiavi nel codice.
- Il deploy è automatico: push su `main` → `.github/workflows/deploy.yml`.
  - Se esiste `package.json`: `npm ci` + `npm run build`, pubblica `dist/`.
  - Altrimenti pubblica la root del repo così com'è.

## Percorsi
- Usa **sempre percorsi relativi** `./` (`./style.css`, `./assets/logo.svg`).
- Mai percorsi assoluti `/…`: su Pages puntano a `layer8panic.github.io/` e si rompono.

## Vite
- In `vite.config.*` imposta `base: './'`.
- Output di build in `dist/` (default).

## React Router
- Usa **`HashRouter`**, non `BrowserRouter`: Pages non ha rewrite, quindi le route senza hash danno 404 al refresh.

## Stile del codice
- Codice essenziale per risparmiare token: niente boilerplate, commenti solo dove servono, nessuna dipendenza superflua.
- Preferisci HTML/CSS/JS vanilla per app semplici; usa Vite/React solo se il progetto lo richiede.
- Risposte brevi: mostra solo i file/blocchi modificati.

## Design
- Per ogni decisione di UI/UX (layout, palette, tipografia, componenti, accessibilità) usa le skill in `.claude/skills/`, in particolare `ui-ux-pro-max`.
- Altre skill disponibili: `design-system`, `ui-styling`, `design`, `brand`, `banner-design`, `slides`.

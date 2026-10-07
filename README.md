<p align="center">
  <img src="https://img.shields.io/badge/React-19-61DAFB" alt="React 19">
  <img src="https://img.shields.io/badge/Vite-6-646CFF" alt="Vite">
  <img src="https://img.shields.io/badge/Gemini-API-4285F4" alt="Gemini API">
  <img src="https://img.shields.io/badge/status-private-lightgrey" alt="status: private">
</p>

# Calculo

**An AI math tutor that writes practice problems at the level you ask for, then walks you through the solution one hint at a time.**

Type a topic — "derivatives of trigonometric functions", "conditional probability" — pick a difficulty from review to olympiad, and Calculo (built in Google AI Studio as "Math Architect") asks Gemini to compose a fresh problem with a worked, LaTeX-rendered solution.

- **Hints before answers** — each solution step can be revealed as a nudge, a partial hint, or the full explanation.
- **Practise the same idea again** — generate similar problems, flashcards, or a multiple-choice quiz from any problem.
- **Diagrams** — geometry problems can come with a generated figure.
- **Keep your work** — history is saved locally and any session exports to PDF.

AI Studio app: https://ai.studio/apps/drive/1d8jivbNyLhgDARGDmQJPJGljTIfg2I42

## Quick start

```bash
npm install
echo "GEMINI_API_KEY=..." > .env.local   # your own key
npm run dev
```

`npm run build` and `npm run preview` produce and serve a production build.

## Configuration

| Key | Purpose |
|---|---|
| `GEMINI_API_KEY` | Google Gemini API key; Vite injects it into the client at build time |

## How it works

```
topic + difficulty ──▶ Gemini Flash (analyse the topic)
                   ──▶ Gemini Pro (write problem + steps) ──▶ optional verify pass
                   ──▶ render with KaTeX, cache, save to history
```

Shortcuts: `Ctrl/Cmd + Enter` generate, `Ctrl/Cmd + H` history, `Ctrl/Cmd + .` debug panel.

## Links

- [docs/internals.md](docs/internals.md) — the full previous README: feature list, component map, architecture notes
- [CHANGELOG.md](CHANGELOG.md), [IMPLEMENTATION_SUMMARY.md](IMPLEMENTATION_SUMMARY.md)

# Copilot instructions

## Project structure and runtime

- The project is a single-page space quiz implemented entirely in the root `index.html`: its HTML shell, CSS, question data, and JavaScript behavior live in that file.
- Open `index.html` directly in a modern browser. It runs from a `file://` URL without a server, build step, package manager, external assets, or runtime dependencies.
- The `questions` array is the quiz's source of truth. `renderQuestion`, `selectAnswer`, `advance`, and `showResults` handle display, answer scoring, progression, and completion in the same page.

## Build, test, and lint

- No local build, test, or lint commands or automated test runner are configured. The Pages workflow stages the root `index.html` as its CI check.
- `.github/workflows/deploy-pages.yml` stages the site for pull requests to `main` and deploys after pushes to `main` or a manual dispatch from `main`.
- To run the app, open `index.html` in a browser. There is no single-test command; for a focused manual check, answer one question correctly and one incorrectly, then verify the score, feedback, and progression.

## Quiz and UI conventions

- Each question has a prompt, an ordered `answers` array, a zero-based `correct` answer index, and an explanation. Keep the index aligned when reordering answers; use `questions.length` for quiz totals and progress.
- Keep user-visible question and feedback content rendered as text nodes or with `textContent`, rather than treating quiz data as HTML.
- The light and dark palettes are defined as CSS custom properties in `:root` and `@media (prefers-color-scheme: dark)`. Extend both palettes when adding themed colors.
- Keep animations compatible with `prefers-reduced-motion`. The decorative star field animates only under `prefers-reduced-motion: no-preference` and stays static when reduced motion is requested.
- Preserve the quiz's native button controls and accessibility updates: answer choices have labels, score and feedback are announced, progress uses an updated `aria-valuenow`, and focus moves to the next action or heading as the quiz advances.

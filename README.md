# Space Quiz

A self-contained, single-player space exploration quiz. Enter a display name, answer ten questions, and aim for eight correct answers to unlock the celebration. The name and score stay in the current browser session; there is no shared or live leaderboard.

The interface supports light and dark system themes, keyboard-accessible controls, and reduced-motion preferences.

## Run locally

Open `index.html` directly in a modern browser. No server, package installation, build step, or runtime dependency is needed.

## GitHub Pages

The GitHub Actions workflow in `.github/workflows/deploy-pages.yml` stages the static `index.html` file and deploys it to GitHub Pages when changes are pushed to `main`. Pull requests to `main` run the staging job as a check.

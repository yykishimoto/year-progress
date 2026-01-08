# Repository Guidelines

## Project Structure & Module Organization
All source lives in the repo root for easy static hosting: `index.html` handles layout, `style.css` defines the responsive card UI, and `app.js` encapsulates date math (`calculateProgress`, `render`, helpers). README.md documents the product surface; update it when you add UI sections. Keep new assets inside an `assets/` folder and reference them with relative paths so they work in any static host.

## Build, Test, and Development Commands
This is a zero-dependency static app. Preferred workflows:
- `open index.html` (macOS) — launches the page directly in your default browser.
- `python3 -m http.server 4173` — serves the root for local testing with proper caching headers; stop with Ctrl+C.
- `npx serve .` — optional Node-based server if you already use npm tooling.
No bundler or transpiler is expected; discuss before introducing one.

## Coding Style & Naming Conventions
Use 2-space indentation across HTML, CSS, and JS. Favor `const`/`let`, descriptive camelCase like `daysRemaining` in JS, and CSS class names that describe roles (`.card`, `.info`). Keep functions pure where possible and colocate helpers near their usage. Run prettier or your editor formatter with default settings before pushing; avoid semicolons unless needed for defensive ASI.

## Testing Guidelines
Automated tests are not yet configured, so rely on manual validation: load the page, verify remaining/elapsed days at boundaries (Jan 1, Dec 31, leap years), and confirm the timer refreshes every 60s. When changing layout, test in responsive mode (375px, 768px, desktop) to ensure grid breakpoints hold. Document any new manual test cases in the PR description until a harness is added.

## Commit & Pull Request Guidelines
Follow the existing imperative, sentence-case log style (`Add Year Progress web application`). Each PR should describe motivation, highlight UI changes with before/after screenshots or GIFs, and mention manual test steps. Link tracking issues when available and keep PRs focused on one concern to keep reviews quick.

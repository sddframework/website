# SDDFW website

Spec Driven Development Framework. Build with intent. Ship with evidence.

This repository contains the English landing page for the SDDFW v0.1 source
preview. It introduces the local CLI workflow, links to runnable frontend/API
examples, and separates those checks from the interactive illustrative report.

## Project and community

SDDFW is hosted by the [sddframework organization](https://github.com/sddframework).

- [sddfw](https://github.com/sddframework/sddfw): framework collaboration and
  project direction.
- [Discussions](https://github.com/sddframework/sddfw/discussions): questions,
  workflow examples, and feature ideas.
- [website](https://github.com/sddframework/website): this landing page and its
  specifications. Use this repository's issues for landing problems.
- [.github](https://github.com/sddframework/.github): shared contribution
  guidance, conduct rules, and community templates.

The founder, organization owner, and primary maintainer is
[@alfoncode](https://github.com/alfoncode). The website was transferred from
`alfoncode/sddfw` with its history preserved.

See the shared [contribution guide](https://github.com/sddframework/.github/blob/main/CONTRIBUTING.md)
and the framework's [governance document](https://github.com/sddframework/sddfw/blob/main/GOVERNANCE.md).

## License

[MIT](LICENSE). Contributors retain copyright in their contributions.

## Local development

Requires Node.js 22 or later. There are no package dependencies to install.

```sh
npm run dev
```

Open http://localhost:4173. Set `PORT` to use a different port.

## Build and preview

```sh
npm run check
npm run build
npm run preview
```

Stop the development server before previewing the build on the same port.
`dist/` contains a self-contained static page ready for a static host, including
the MIT license and copyright notice.

## Publication

The production address is [https://sddfw.com](https://sddfw.com).
GitHub Pages publishes only the static `dist/` output from this repository.
The `Publish website` workflow checks and builds pull requests. Successful
changes to `main` are deployed automatically; it can also be run manually from
the Actions tab on `main`.

The custom domain is configured in this repository's Pages settings. DNS stays
with IONOS: the apex uses GitHub Pages A and AAAA records, and `www` is a CNAME
to `sddframework.github.io`. GitHub redirects `www` to the apex domain. A separate
TXT record verifies domain ownership for the organization. Keep that record
and the mail records when changing hosting.

The production page declares its canonical URL and includes public `robots.txt`
and `sitemap.xml` files. The build also includes the MIT license.

To restore a previous website version, revert the relevant source commit on
`main` and let the workflow deploy it. DNS does not need to change for a source
rollback. The pre-publication DNS snapshot is kept locally in
`.artifacts/pages-deployment/` (gitignored).

## Structure

- `index.html`: English content, page sections and baseline sample report.
- `assets/styles.css`: responsive design and reduced-motion support.
- `assets/main.js`: sample criteria, correction preview, Markdown download and mobile navigation.
- `assets/theme.js`: early theme selection, system preference and the persistent light/dark switch.
- `assets/favicon.svg`: local vector brand asset.
- `assets/brand/`: SDDFW logo exports, social previews and ready-to-use brand kit.
- `specs/landing.md`: intent and acceptance criteria for this landing.
- `scripts/`: small local server and static build, using Node.js built-ins.

The page works without remote fonts, CDN assets, analytics or external services.
Core content and the baseline report remain readable without JavaScript.

## Product boundaries

The reservation report on the page does not run application tests or certify a
change. The separate CLI favorites demo runs actual UI/API checks locally. v0.1
is an early source preview installed from the framework repository; its npm
package is not published. OpenSpec/Spec Kit imports and other test runners remain
future work. There is no waitlist backend.

The getting-started, example, and community guide links target the repositories'
`main` branches so deleting a completed work branch does not break them.
The page does not upload reports, execute user code, or perform agent calls.
Agent invocation happens through the installed local CLI and the user's coding
agent. Tests are prepared and checked before implementation; implementation
runs with test files frozen. Correct scenario interpretation and test adequacy
still require review.

## Verified locally — 2026-10-01

Verification used an isolated headless Chrome browser through `agent-browser`.

- `pnpm check` and `pnpm build` passed. The built page was served and its
  interactive correction preview worked from `dist/`.
- All four sample criteria revealed the matching evidence. Keyboard activation
  was checked. The correction changed the count from 2 to 3, kept the boundary
  unverified, and reset restored the failed criterion.
- The Markdown download completed. Its contents retained all four criteria,
  the unverified boundary, and the explicit illustrative-sample notice.
- In-page anchors resolved to existing sections. The roadmap link and return
  to top worked. The FAQ opened with a click and closed with the keyboard.
- Mobile navigation opened, closed with Escape, restored focus, and closed
  after following a section link.
- At 360, 390, 768 and 1440 pixels, document width matched viewport width.
  Desktop, tablet and mobile screenshots were visually inspected.
- Reduced-motion emulation produced automatic scrolling and zero transition
  duration. With the landing's JavaScript request blocked, content and navigation
  remained visible while interactive sample actions were hidden. This checked
  script-unavailable fallback; browser-wide JavaScript disabling was not used.
- The axe-core scan reported zero automated violations at mobile and desktop
  sizes. It flagged decorative overlaps in the closing section for manual contrast
  review; the text/background pairs were checked manually.
- The final normal page load produced no captured browser console or page errors.

Local screenshots and the downloaded sample are in `.artifacts/` (gitignored).
These historical checks cover the previous landing, not the v0.1 CLI or a
hosted deployment. See the current verification section below for this revision.

## Red light and dark themes

Use the sun/moon button in the header to switch themes. The first visit follows
the system appearance. A manual choice is saved under `sddfw-theme` and applied
before the stylesheet paints on later visits. Switching also works when browser
storage is blocked. Theme colors are centralized in `assets/styles.css`.
The current identity uses vivid red (`#E60000`) with neutral white, gray and
charcoal surfaces.
Both themes share the same red buttons and principles section. Red text is
lighter in dark mode to preserve contrast against charcoal surfaces.
The dark FAQ uses neutral gray surfaces for closed, hovered and expanded states.

Verified in isolated Chrome: system preference changes, mouse and keyboard
switching, persistence after reload, blocked storage reads/writes, the existing
correction demo, and both themes at 360, 390, 768 and 1440 pixels. Both palettes
reported zero automated axe violations; decorative-overlap contrast flags in
the closing section were reviewed manually. Blocking both scripts left the page
content and navigation readable, with unavailable interactive controls hidden.

The branding audit includes hidden/generated files and file/directory names.
Package metadata and saved sample reports use SDDFW, and previous screenshots
were regenerated with the corrected brand. Current theme previews use the red palette.


## Verified locally — 2026-10-05, v0.1 landing

The revised source page was checked in isolated headless Chromium with
`agent-browser` 0.38.2. These are local landing checks, not a hosted deployment or
framework release certificate.

- `npm run check` and `npm run build` passed.
- Light and dark themes had no horizontal page overflow at 360, 390, 768, and
  1440 pixels. Desktop and mobile screenshots were inspected, including the new
  quickstart and frontend/backend examples.
- All in-page anchors resolved. The demo correction changed 2 passed criteria
  to 3 and preserved the unverified boundary; resetting restored the baseline.
- The Markdown download retained all four criteria and its explicit
  illustrative-only notice.
- Mobile navigation opened and Escape closed it and restored button focus.
  Native FAQ disclosure opened by click and closed by keyboard.
- Reduced-motion emulation used automatic scrolling. Blocking both JavaScript
  assets kept navigation, the quickstart, examples, and baseline report readable;
  unavailable sample actions were hidden. This is a script-unavailable fallback
  check, not browser-wide JavaScript disabling.
- Axe 4.12.1 reported zero automated violations in light/dark desktop and mobile
  checks. Decorative overlaps in the existing closing panel still require
  manual contrast review. Text backgrounds were made opaque there; reviewed
  heading/accent/body contrast ratios were 14.55/4.75/5.53 in light and
  14.24/4.82/7.83 in dark. No captured errors occurred on the normal page load.
- CLI command syntax was cross-checked with the implemented CLI help and source.
  Source documentation links target `main`. After all three repositories were
  integrated and their work branches deleted, 23 public URLs returned HTTP 200;
  all three linked section fragments were valid.

### Published verification

The [GitHub Pages deployment](https://github.com/sddframework/website/actions/runs/37374956220)
completed successfully on 2026-10-05. The HTML served at
[sddfw.com](https://sddfw.com/) matched the production build byte for byte.
HTTP redirects to HTTPS and `www` redirects to the apex domain. Playwright
checked light/dark layouts at 390 and 1440 pixels with no horizontal overflow,
all nine in-page links, mobile navigation, FAQ disclosure, sample correction,
and the Markdown download. The download retained three passed criteria, one
unverified criterion, and the illustrative-only notice; no JavaScript errors
were observed. The profile image and linked documentation were available.

Temporary browser tooling, screenshots, and the downloaded sample were kept
outside the repository under `/private/tmp/`.

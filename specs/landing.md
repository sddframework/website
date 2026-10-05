# SDDFW v0.1 landing

Status: landing for the v0.1 source preview; no npm registry release.

## Intent

Introduce SDDFW v0.1 in English: a local coding agent drafts a specification,
the user explicitly reviews and approves it, the agent prepares Playwright
checks, and implementation runs against frozen tests before acceptance evidence
is generated. Help a visitor install from source, run the frontend + backend
demo, and adopt the workflow in an existing project. Keep the illustrative
reservation report distinct from executed CLI evidence.

## Scope

- Responsive, accessible, static landing with a distinct visual identity.
- Working in-page navigation, interactive sample report and FAQs.
- Clear distinction between the illustrative landing report, runnable CLI preview,
  and future adapters.
- Source installation guide and a copyable real-demo sequence.
- Frontend and backend examples linked to executable project sources.
- A small roadmap that can be updated as the project develops.

## Acceptance criteria

- LAND-001: All visitor-facing content is in English.
- LAND-002: The page describes v0.1 as an early source preview with no npm
  registry release. Installation links target the framework repository's `main` branch.
  It has no invented repository, customer logos, testimonials, waitlist
  submission, or claim that the illustrative report is live framework evidence.
- LAND-003: Selecting a sample criterion reveals its sample evidence and result.
  Controls support keyboard navigation and expose their state to assistive technology.
- LAND-004: The correction preview changes the failing sample criterion to passed,
  while the unverified boundary scenario remains unverified.
- LAND-005: Resetting the preview restores the original sample report.
- LAND-006: The example summary can be downloaded as an explicitly labeled Markdown sample.
- LAND-007: Navigation reaches existing page sections; mobile navigation opens,
  closes, and supports Escape. FAQs expose their content through native disclosure controls.
- LAND-008: The page has no horizontal overflow at 360, 390, 768, and 1440 pixels.
- LAND-009: The page respects reduced motion and remains readable with JavaScript disabled.
- LAND-010: Build output is self-contained, with local CSS, JavaScript and SVG assets.
- LAND-011: A keyboard-accessible header button switches the entire page between
  light and dark red palettes. The initial theme follows the system preference
  unless a valid saved choice exists. A chosen theme survives reloading; blocked
  browser storage does not prevent switching themes.
- LAND-012: Project content and file or directory names consistently use SDDFW.

- LAND-013: Quickstart includes a working CLI demo sequence with explicit
  specification review and approval, dependency/browser installation scope,
  and HTML/Markdown/JSON report outputs.
- LAND-014: Frontend persistence and backend idempotency/user-separation examples
  link to the runnable fullstack template. Simulated identity and local storage
  limits are visible.
- LAND-015: The workflow explains test preparation before implementation and
  frozen tests during implementation. FAQs preserve human review, local
  evidence, provider usage, missing/flaky checks, mocks, and sharing limits.

## Verification scope

Check the rendered page, report interaction, download, navigation and representative
desktop/mobile sizes in a real browser. Record the actual checks in README.md.
The sample report is illustrative and does not validate an application or the framework.

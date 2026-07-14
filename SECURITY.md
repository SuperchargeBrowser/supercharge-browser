# Security Policy — SuperchargeBrowser

## Overview

SuperchargeBrowser develops Chrome extensions with a strict local-execution model. No user data is collected, transmitted, or stored on external servers. **SuperchargePerformance**, **SuperchargeNavigation**, **SuperchargeAudio**, and **SuperchargeCapture** all run entirely in your browser.

## Architecture Principles

- **Zero telemetry** — no analytics, no crash reporting, no usage tracking
- **No SuperchargeBrowser servers** — extensions make no network requests to our infrastructure (we have no backend). SuperchargeNavigation's opt-in cross-device workspace sync (v1.1.0+) routes through Chrome's own `storage.sync` infrastructure — Google's infra, not ours. SuperchargeCapture's optional Share-to-Drive upload goes to the user's own Google Drive account, never to SuperchargeBrowser.
- **Local-by-default storage** — all settings, snapshots, and session data use `chrome.storage.local`. SuperchargeNavigation v1.1.0+ adds opt-in workspace sync via `chrome.storage.sync` (off by default).
- **Manifest V3** — all four extensions use Chrome's latest extension platform with tighter security defaults
- **Minimal permissions** — each extension requests only the permissions required for its features
- **No `eval()`** — no dynamic code execution anywhere in either extension
- **Content Security Policy** — strict CSP enforced via manifest
- **No backend servers** — there is no server infrastructure to breach

## Supply Chain Security

- Secret scanning with [gitleaks](https://github.com/gitleaks/gitleaks) on every commit (pre-commit hook + CI)
- Dependency vulnerability monitoring via Dependabot
- Automated testing: 1,500+ unit tests (Vitest) and 250+ Playwright E2E tests across both extensions plus a cross-extension test suite
- Google Chrome Web Store review before every published version

## Permissions Justification

### SuperchargePerformance

| Permission | Why it's needed |
|---|---|
| `tabs` | Monitor tab activity to identify inactive tabs for suspension |
| `declarativeNetRequest` | Apply 186,000+ ad/tracker blocking rules at the network layer |
| `storage` | Persist user preferences (whitelists, timers, feature levels) locally |
| `scripting` | Inject font optimization, lazy loading, and autoconsent into pages |
| `alarms` | Schedule periodic tab suspension checks |
| `<all_urls>` | Required by `declarativeNetRequest` and `scripting` to operate across all sites |

### SuperchargeNavigation

| Permission | Why it's needed |
|---|---|
| `tabs` | Read and manage the tab list for the vertical tab side panel |
| `tabGroups` | Create, rename, and collapse tab groups |
| `sidePanel` | Render the vertical tab UI in Chrome's side panel |
| `storage` | Persist workspaces, snapshots, and user preferences locally |
| `unlimitedStorage` | Store up to 50 session snapshots for time travel without hitting quota |
| `alarms` | Trigger automatic session snapshots every 5 minutes |
| `scripting` | Inject content scripts for Glance preview, Super Drag, and tab deduplication |
| `sessions` | Access recently closed tabs for session restoration |
| `bookmarks` | Include bookmarks in Alt+K command palette search results |
| `history` | Include browsing history in Alt+K command palette search results |
| `management` | Detect other extensions for compatibility and diagnostics |
| `declarativeNetRequest` | Modify CSP/X-Frame-Options headers on Glance preview frames only (scoped per-tab via session rules) |
| `<all_urls>` | Required by `scripting` and `declarativeNetRequest` to operate across all sites |

### SuperchargeAudio

| Permission | Why it's needed |
|---|---|
| `storage` | Persist per-site volume, EQ, and channel settings locally |
| `tabs` | Identify audible tabs for Smart Mute and the audible-tabs list |
| `tabCapture` | Route a tab's audio through the processing chain on protected/DRM streams where in-page audio access is blocked — off by default, opt-in per session |
| `offscreen` | Host the audio processing graph used by tab-capture mode |
| `<all_urls>` | Required to insert a Web Audio gain node into a page's own audio graph |

### SuperchargeCapture

SuperchargeCapture requests **no website access by default** and shows no permission warning at install — it only captures the tab you explicitly act on. Recording continuously across page navigations is a separate feature you opt into yourself, and only then does it request the additional access that requires. All capture and processing happens on-device; nothing is sent to SuperchargeBrowser servers. The optional Share-to-Drive export uploads only the file you create, to your own Google Drive account, and never reads the rest of your Drive.

## Reporting a Vulnerability

If you discover a security issue in any SuperchargeBrowser extension, please report it responsibly:

- **Email:** [support@superchargebrowser.com](mailto:support@superchargebrowser.com)
- **Subject line:** Security Report — [Extension Name]
- **What to include:** extension name, Chrome version, steps to reproduce, and potential impact
- **Disclosure:** Please do not disclose publicly until we have investigated and addressed the issue

We will acknowledge receipt within 48 hours and aim to resolve confirmed issues within 7 days.

## Verification

All four extensions are published under a **Verified Publisher** account on the Chrome Web Store. You can verify the publisher identity on each extension's CWS listing page:

- [SuperchargePerformance](https://chromewebstore.google.com/detail/pafkkbjmpnfkdkkhldbbnggnmpbbhkmf)
- [SuperchargeNavigation](https://chromewebstore.google.com/detail/mpkbppjbchjdohbjgeoamdehklmapgnl)
- [SuperchargeAudio](https://chromewebstore.google.com/detail/cbjglaijgolamegjnaiabgdojmghalbe)
- [SuperchargeCapture](https://chromewebstore.google.com/detail/gebkchfkcnjdflkfdimabihllibgcdhp)

## More Information

- [Privacy Policy](https://www.superchargebrowser.com/privacy/)
- [Full Security Architecture](https://www.superchargebrowser.com/security/)
- [Open Source Attributions](https://www.superchargebrowser.com/open-source/)

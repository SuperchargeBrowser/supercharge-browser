# Changelog

All notable changes to SuperchargeBrowser extensions are documented here. For detailed release notes, see [superchargebrowser.com/changelog](https://www.superchargebrowser.com/changelog/).

## SuperchargeNavigation

### v1.3.3 — June 29, 2026
- Web search from the new-tab search box and side-panel command search now uses the browser's default search engine instead of a fixed one
- Keyboard hint badges no longer pop up while typing in a page's own search box

### v1.3.2 — June 25, 2026
- Tabs already open in a window are now saved as a named workspace before a synced workspace restores into it, preventing data loss on first-time setup on a second device
- Keyboard hint mode resumes from the last active hint on re-press of Shift instead of resetting to the first hint
- Only http and https links are stored in workspaces and assigned on the new-tab page

### v1.3.1 — June 19, 2026
- Renaming a workspace or group is now discoverable — a hover affordance (dotted underline + pencil) in the new-tab page and sidebar, plus a Rename item in the group right-click menu
- Command palette adds a Best Matches section and now closes with Esc from any focus, not only the search box
- Type-to-select shows a live pill of the typed query with a match count
- Fixes for hint-mode typing in page inputs, double-click rename timing, workspace matching, and javascript: links

### v1.3.0 — June 2026
- In-page sidebar: the vertical tab sidebar can now run inside any page, and opens a dedicated tab on Chrome-protected pages (chrome://, Web Store, PDF)
- Live on Microsoft Edge Add-ons alongside the Chrome Web Store

### v1.2.2 — May 2026
- Auto-open workspace on launch: optionally open a workspace automatically on each empty new window
- Fixed clicking a workspace with none active (silent no-op) and a blank Peek frame on certain sites in Edge

### v1.2.1 — May 2026
- Microsoft Edge support: every internal URL filter and browser deep-link now handles edge:// alongside chrome://
- Per-site pause shortcut moved to Alt+Shift+P; new tab page gains a persistent restore button; settings help icons open dedicated feature pages

### v1.2.0 — May 2026
- Keyboard layer for the page: hint mode (letter badges over clickable elements), type-to-select, fast text selection, and arrow-key page scroll
- Settings promoted to a full options page; page-keystroke features ship off by default

### v1.1.0 — April 24, 2026
- Cross-device workspace sync through Chrome's built-in account sync — no SuperchargeBrowser server involved
- Full-replacement new tab page with workspace cards, pinned tabs, top sites, fuzzy search, clock, and ambient particles
- Multi-window mode: each Chrome window runs its own workspace, with pairings surviving restarts
- Time-travel redesigned to snapshot all workspaces at once — restore any subset via checkboxes without touching the rest
- URLs menu in the side panel: paste a list of links to open them, or copy every URL in a workspace with one click
- Workspace Transfer menu (renamed from Backup) with per-workspace export and full-backup export
- Right-click context menu additions: Copy URL and Lock/Unlock on tabs; Copy URLs, Lock All, Mute All, Pin All, and Send to Workspace on groups
- Alt+B is now the default shortcut for toggling the side panel

### v1.0.0 — March 13, 2026
- Initial Chrome Web Store release
- Vertical tabs in Chrome's side panel with drag-to-reorder, multi-select, and tab groups
- Persistent workspaces that survive browser restarts
- Session time travel with automatic snapshots every 5 minutes (last 50 states)
- Tab search command palette (Alt+K) across open tabs, bookmarks, and history
- Smart tab grouping by domain (Alt+G)
- Glance/Peek link previews (Shift+Click)
- Super Drag to open links by drag direction
- Tab deduplication
- Zero runtime dependencies, zero telemetry

## SuperchargePerformance

### v1.4.5 — June 25, 2026
- Blocklists refreshed from all upstream sources — 186,728 rules across three tiers
- Redesigned in-popup review prompt: milestone icon ladder from star to trophy, gold medallion above the headline, layout fixes so the card no longer clips
- Popup cross-promo now cycles through the other extensions one at a time, with SuperchargeCapture added to the lineup

### v1.4.4 — June 19, 2026
- Cookie banner auto-rejection split out of the default-off Smart Page Cleanup toggle into its own feature, Auto-Reject Cookie Banners, on by default
- Cosmetic element hiding stays a separate, opt-in part of Smart Page Cleanup
- Fixed a SecurityError on sandboxed iframes that could silently stop cookie auto-rejection on some pages

### v1.4.3 — June 15, 2026
- Fixed a whitelist bug where a wildcard entry like `*.example.com` silently matched nothing and could corrupt per-site exclusions for every other entry; existing entries migrated automatically on update
- Manual whitelist adds now bypass all features by default, matching the popup's per-site toggle
- Popup's per-site toggle is now subdomain-aware
- Popup footer version now reads from the manifest instead of a hardcoded string
- Blocklists refreshed to 186,674 rules across three tiers

### v1.4.2 — June 11, 2026
- Disabling the extension on a site now takes effect instantly — cosmetic hides reappear with no reload, and a whitelist matches both the apex domain and its www version
- Fewer false hides — live tickers, share buttons, and legitimate alert banners stay visible; scroll-unlock fix leaves real modals alone
- Stop Autoplay rebuilt for reliability, with three levels: Off, Allow common video sites, Block everywhere
- New one-click "Disable on this site" prompt when a page genuinely renders broken
- Cookie banner rejection engine (DuckDuckGo AutoConsent) updated; blocklists refreshed to 186,648 rules across three tiers

### v1.4.1 — June 2026
- Suspended tabs restore scroll position on reload
- Tabs paused on YouTube and other Media Session API sites no longer get stuck open — the engine now checks for a genuinely playing media element
- Overlay scroll-locks handled alongside cookie-consent banners; alarm reliability and safe-mode cleanup tightened

### v1.4.0 — June 2026
- Adaptive suspension: tabs scored by memory used × idle time instead of oldest-idle-first, skipping tabs with unsaved form data
- Memory fast-path mode can suspend heavy tabs before the idle timer fires
- Redesigned popup with a live status line and a Silent toggle; AutoConsent upgraded to 14.84.0; blocklists refreshed across all 22 sources

### v1.3.2 — April 30, 2026
- 59 locales total (up from 28) — 31 new languages including Norwegian Bokmål, Arabic, Hebrew, Persian, Filipino, Bengali, Tamil, and more
- English listing title rewritten to "Tab Suspender, Memory Saver & Ad Blocker"
- Extension code unchanged from v1.3.1 — no behavioral differences in this release

### v1.3.1 — April 17, 2026
- YouTube ad blocking strengthened — Shorts ads, midroll gaps, and new ad delivery paths caught
- Faster startup by loading blocking systems in parallel; popup panel is more responsive
- Smart recovery no longer incorrectly triggers on PDFs, direct image links, and standalone video files
- Cookie banner rejection now covers Fides-based consent systems (New York Times, Washington Post)
- Tab suspension handles browser restarts more gracefully — suspended tabs and metrics survive Chrome reloads
- 19 bug fixes across tab suspension, whitelisting, Twitch and YouTube content scripts, and LinkedIn compatibility
- Blocklists refreshed to 186,655 rules across 22 sources

### v1.3.0 — April 16, 2026
- YouTube video ad blocking — pre-rolls, mid-rolls, overlay ads, and anti-adblock popups handled
- Twitch ad blocking — stream continues uninterrupted during ad breaks with no black screens
- Popup and popup-under blocker with smart exceptions for same-domain popups, OAuth windows, and intentional clicks
- AutoConsent upgraded from 14.56.0 to 14.67.0 — more consent platforms detected, scroll-lock removal improved
- Cosmetic filtering smarter about stopping unnecessary DOM checks; site-specific rules refreshed for YouTube, Facebook, Twitter, and Reddit
- Blocklists refreshed to 186,573 rules across 22 sources

### v1.2.2 — March 17, 2026
- Theme-aware toolbar icon — blue bird in light mode, amber in dark mode; popup logo follows the same logic
- Canvas-rendered RAM counter badge on the toolbar showing cumulative RAM saved (e.g. "4.2 GB")
- Cross-promotion banner for SuperchargeNavigation shown to users with 7+ days of install, permanently dismissible
- Timed pause: disable all optimizations temporarily with automatic re-enable after the chosen duration
- Arabic locale added; German and Turkish CWS listing titles and descriptions optimized
- Blocklists refreshed to 186,567 rules across three tiers

### v1.2.1 — March 12, 2026
- Rebranded to "SuperchargePerformance" across all UI
- Updated blocklists to 186,000+ rules
- RAM saved badge on toolbar icon (cumulative, persists across restarts)
- 1-hour pause toggle replaces global on/off
- Fixed Turkish locale description truncation
- Dark mode badge fallback fix

### v1.2.0 — February 2026
- In-extension review prompt
- Site access check with warning banner
- Welcome page with onboarding
- CWS screenshots and promo tiles updated

### v1.1.0 — January 2026
- Ad and tracker blocking via declarativeNetRequest
- Script control at three coverage levels
- Font optimization (system font substitution)
- Lazy loading for off-screen resources
- Link preloading (predictive navigation)
- Autoplay blocking
- Cookie consent auto-handling via @duckduckgo/autoconsent
- Safe Mode auto-recovery

### v1.0.0 — November 2025
- Initial Chrome Web Store release
- Intelligent tab suspension using chrome.tabs.discard
- Basic performance dashboard in popup

## SuperchargeAudio

### v1.0.4 — June 25, 2026
- Fixed a click during rapid EQ slider drags — a new adjustment now ramps from the current gain instead of snapping back
- Redesigned the occasional in-extension review prompt so its buttons can't get clipped in the popup
- "You might also like" card now shows each suggestion's own product icon; SuperchargeCapture suggestion gained its Edge store link

### v1.0.3 — June 22, 2026
- Switching between Stereo, Mono, and Wide channel modes no longer produces an audible click — gains now ramp smoothly
- 8D spatial effect is now deterministic — no more drift between clips or after a page reload

### v1.0.2 — June 10, 2026
- Live on the Chrome Web Store, alongside the existing Microsoft Edge Add-ons listing
- In-extension review prompt on Chrome now opens the live Chrome Web Store listing instead of a placeholder

### v1.0.1 — June 8, 2026
- Soft limiter added — volume and stacked EQ no longer distort, even up to 600%
- Volume and EQ changes now ramp smoothly instead of jumping
- One-tap capture banner for protected streams (Netflix, Spotify-style DRM) where in-page boosting can't reach
- Click a tab anywhere in the audible-tabs list to jump to it

### v1.0.0 — May 28, 2026
- Initial release — volume boost up to 600%, 10-band equalizer (±12dB per band) with named presets and a custom mode
- Bass boost, mono downmix, stereo width, and 8D rotating-pan effect
- Headphone crossfeed, smart mute, per-site memory, audible-tabs list
- Optional tab-audio-capture mode for DRM-protected streaming sites
- 100% local, no account, no telemetry

## SuperchargeCapture

### v1.0.2 — June 25, 2026
- Auto-zoom now holds the frame steady and glides only for deliberate cursor moves, instead of tightly chasing every wiggle
- Camera and microphone permission prompts redesigned as calm, clear invitations instead of red error-style banners
- New "Open editor" button in the popup opens past recordings for review or editing without starting a fresh capture
- Polished cursor is now off by default

### v1.0.1 — June 22, 2026
- Fixed recordings that stalled at "Uploading 0%" when sharing or exporting to Google Drive — a render step could hang before upload started
- Editor toolbar buttons (Export, Share to Drive, Save) now hold a steady size instead of resizing when a Drive status message appears

### v1.0.0 — June 22, 2026
- Initial release — screenshots (visible area, full page, region) and tab/window/screen recording, with no screen-picker dialog for tab capture
- Optional webcam bubble with on-device background blur, plus microphone and system audio
- Built-in editor — annotation, automatic zoom that follows clicks, smoothed cursor, trim
- Export a recording as GIF, MP4, or WebM; export a screenshot or full page as PDF
- Save as a file download, or upload to your own Google Drive
- Requests no website access by default; 100% local, no account, no watermark

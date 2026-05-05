# Changelog

All notable changes to SuperchargeBrowser extensions are documented here. For detailed release notes, see [superchargebrowser.com/changelog](https://www.superchargebrowser.com/changelog/).

## SuperchargeNavigation

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

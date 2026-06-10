# Frequently Asked Questions — SuperchargeBrowser

## General

### What is SuperchargeBrowser?
SuperchargeBrowser makes Chrome and Edge extensions for browser performance, tab navigation, and audio control. We currently publish three extensions: **SuperchargePerformance** (tab suspender + ad blocker + memory optimizer), **SuperchargeNavigation** (vertical tabs + workspaces + session management), and **SuperchargeAudio** (per-tab volume boost + 10-band EQ + Smart Mute). All are free and collect zero data. SuperchargePerformance and SuperchargeAudio run 100% locally; SuperchargeNavigation runs locally by default with opt-in cross-device workspace sync via Chrome's own infrastructure. All three extensions are live on both the Chrome Web Store and Microsoft Edge Add-ons.

### Is SuperchargeBrowser safe to install?
Yes. Both extensions are Manifest V3, reviewed by the Chrome Web Store team, and published under a Verified Publisher account. There is no telemetry, no analytics, no remote code loading, and no `eval()`. We have no SuperchargeBrowser servers — there is no backend infrastructure to breach. SuperchargeNavigation v1.1.0+ adds opt-in workspace sync through Chrome's own `storage.sync` (off by default, no SuperchargeBrowser involvement). See [SECURITY.md](./SECURITY.md) for the full security architecture.

### Does SuperchargeBrowser collect any data?
No. Zero telemetry, zero tracking, zero analytics. No SuperchargeBrowser accounts, no SuperchargeBrowser servers, no external API calls to our infrastructure. In default configuration, all data stays on your device. SuperchargeNavigation v1.1.0+ has opt-in workspace sync (off by default) routing through Chrome's own `storage.sync` infrastructure — Google's infra, not ours. See our [Privacy Policy](https://www.superchargebrowser.com/privacy/).

### Where is SuperchargeBrowser based?
Finland. SuperchargeBrowser is an independent software company, not backed by an advertising business.

---

## SuperchargePerformance

### How does the tab suspender work?
SuperchargePerformance uses Chrome's native `chrome.tabs.discard` API to suspend inactive tabs after a configurable timeout. Discarded tabs remain visible in your tab strip but release 90%+ of their RAM. Audio tabs, pinned tabs, and tabs with active forms are protected automatically. This is the same mechanism Chrome's built-in Memory Saver uses, but with a timer instead of waiting for memory pressure.

### Is this a safe alternative to The Great Suspender?
Yes. The Great Suspender was removed from the Chrome Web Store in 2021 due to malware. SuperchargePerformance uses Chrome's built-in `tabs.discard` API (not a custom suspension page), runs on Manifest V3, and contains no remote code loading. See our [detailed comparison](https://www.superchargebrowser.com/library/great-suspender-alternative/).

### How is this different from Chrome Memory Saver?
Chrome Memory Saver only activates under system memory pressure — it has no timer, no dashboard, and no ad blocking. SuperchargePerformance suspends tabs on a configurable timer, shows cumulative RAM saved on the toolbar badge, and includes an MV3 ad/tracker blocker with 186,000+ filter rules. See our [full comparison](https://www.superchargebrowser.com/library/tab-suspender-vs-chrome-memory-saver/).

### Does the ad blocker still work after Chrome disabled MV2?
Yes. SuperchargePerformance uses `declarativeNetRequest` (Manifest V3), which is Chrome's current extension API. Extensions like the original uBlock Origin used MV2's `webRequest` API, which Chrome disabled in version 138. Our ad blocker is fully MV3-compliant and unaffected. See [uBlock Origin alternatives](https://www.superchargebrowser.com/library/ublock-origin-chrome-alternative/).

### Can SuperchargePerformance fix Chrome freezing and high CPU usage?
In many cases, yes. Chrome freezes are often caused by too many active tabs consuming RAM and CPU. Tab suspension frees that RAM, and script control reduces CPU usage from background JavaScript. If Chrome is draining your laptop battery, blocking third-party scripts and suspending inactive tabs can significantly reduce power consumption.

### How much RAM does tab suspension actually save?
It depends on how many tabs you have open and what sites they are. On average, each suspended tab frees 50–300 MB of RAM. With 20+ tabs, users typically see 1–4 GB freed. The toolbar badge shows your cumulative savings in real time.

---

## SuperchargeNavigation

### What are vertical tabs?
Vertical tabs display your open tabs in a vertical list on the side of your browser instead of the horizontal tab strip at the top. This lets you see full tab titles (instead of tiny favicons), scroll through many tabs easily, and use drag-and-drop to organize them. SuperchargeNavigation renders vertical tabs in Chrome's native side panel.

### How is this different from Chrome 146 native vertical tabs?
Chrome 146 added a basic vertical tab list, but it lacks workspaces, session time travel, tab search (Alt+K), smart grouping (Alt+G), Glance/Peek, Super Drag, and tab deduplication. SuperchargeNavigation's side panel coexists with Chrome's native vertical tabs — you can use either or both. See our [detailed comparison](https://www.superchargebrowser.com/library/chrome-146-vertical-tabs-vs-extensions/).

### Is this a replacement for Arc Browser?
SuperchargeNavigation brings Arc's most-loved features — vertical tabs, workspaces, command palette, and link previews — to Chrome without switching browsers. Arc stopped active development after being acquired by Atlassian in September 2025. See [Arc Browser alternatives in Chrome](https://www.superchargebrowser.com/library/arc-browser-dead-get-features-in-chrome/).

### Can I sync my workspaces across devices?
Yes. SuperchargeNavigation syncs workspaces across your signed-in Chrome devices using `chrome.storage.sync`. Sync is opt-in and configured during onboarding — no account or external server required. All data passes through Chrome's own sync infrastructure and never touches SuperchargeBrowser servers.

### How do workspaces work?
Workspaces let you save a named set of tabs and restore them later. Each workspace preserves tab groups, pinned tabs, mute states, and group colors. You can create unlimited workspaces (e.g., "Work", "Personal", "Research") and switch between them instantly. All data is stored locally by default, with optional cross-device sync via Chrome's built-in sync. This is a free alternative to Workona's workspace feature.

### What is session time travel?
SuperchargeNavigation takes automatic snapshots of your open tabs every 5 minutes, keeping the last 50 states. If Chrome crashes, you accidentally close tabs, or you want to go back to an earlier browsing session, you can rewind to any snapshot and restore it as a new workspace. No other Chrome extension offers this feature.

### Does SuperchargeNavigation work with Chrome tab groups?
Yes. Vertical tabs display Chrome's native tab groups with their colors and labels. Smart Grouping (Alt+G) creates new groups by domain. Workspaces preserve tab group structure when saving and restoring.

---

## Compatibility

### Can I use both extensions together?
Yes. SuperchargePerformance and SuperchargeNavigation are designed to work together. Performance handles memory and speed optimization; Navigation handles tab organization and workspaces. There are no conflicts.

### Does SuperchargePerformance work on Chromebooks?
Yes. ChromeOS accounts for about 11% of installs. Tab suspension and ad blocking work the same way on Chromebooks, and the RAM savings are proportionally larger on devices with 4–8 GB of memory. See our [Chromebook optimization guide](https://www.superchargebrowser.com/library/speed-up-4gb-chromebook/).

### What Chrome version is required?
SuperchargePerformance requires Chrome 120+. SuperchargeNavigation requires Chrome 130+ (for side panel API features). Both extensions are tested on the latest stable Chrome release.

---

## More Resources

- [95 Chrome guides](https://www.superchargebrowser.com/library/) covering memory management, performance optimization, and tab organization
- [Feature documentation](https://www.superchargebrowser.com/features/) for both extensions
- [Changelog](https://www.superchargebrowser.com/changelog/) for version history

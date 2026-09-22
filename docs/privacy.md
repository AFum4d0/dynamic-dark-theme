---
title: Dynamic Dark Theme — Privacy Policy
---

# Privacy Policy — Dynamic Dark Theme

[日本語版はこちら](privacy-ja.md)

Last updated: 2026-09-22 (website content disclosure clarified)

Dynamic Dark Theme **does not send any data to external servers**. There is no mechanism that sends browsing content, settings, or statistics to the developer or to third parties. There is no telemetry, no analytics, no crash reporting, no account linking, and no remote code.

## What is stored on your device (`chrome.storage.local`, not synced)

| Item | Details |
|---|---|
| Settings | Palette, surface style, image handling (including SVG logos), apply mode, blocklist / allowlist, and sites where you turned off individual correction mechanisms |
| Sites visited | Host names where the extension was applied (or decided not to apply), with per-site on/off state. **This counts as "web browsing activity".** It is stored only on your device and never leaves it. You can erase it from the popup with "Forget visited sites" (sites you configured manually are kept) |
| Repair rules | Rules you created with the "magic wand" (host name, CSS selector, color declarations) |
| Stylesheet cache | Copies of external CSS loaded by pages (up to 4 MB). Together with the image and SVG analysis below, this counts as "website content" in the Chrome Web Store disclosure. It stays on your device |
| Internal error log | Registration failures and similar (up to 30 entries) |

All of this is deleted when you remove the extension.

## Network access

The extension makes only the following three kinds of requests by itself. Each one **re-fetches, once and without cookies, a resource that the page has already loaded**.

1. **External stylesheets:** Cross-origin CSS cannot be read from page scripts, so it is fetched from the background with GET (`credentials: omit`).
2. **Image analysis:** To tell white-background photos, maps, and logos apart, images on the page are fetched, scaled down, and only statistics such as brightness are computed. Pixels are never passed back to the page.
3. **SVG logos:** To fix SVG logos (shown with `<img>`) that are hard to see on a dark surface, the SVG text is fetched (up to 256 KB). Anything that is not SVG is discarded. Setting "SVG logos" to "Leave as is" in the popup stops these requests.

Requests are handled only for sites where the extension is enabled. Requests to LAN, loopback, link-local, and cloud metadata addresses are refused.

## "Save snapshot"

This runs only when you press "Save diagnosis" or "Save for reproduction" in the popup. It writes a file to your device and sends nothing.

- **By default, all page text is masked** (length and character classes are kept). If you uncheck the option, only areas such as account, address, and navigation are masked.
- URL query strings and fragments (`#...`) are not included.
- Scripts, iframes, form field values, and cookies are not included.
- "For reproduction" contains the page structure and CSS. Please review it before sharing.

## What is read from pages

Computed styles, element sizes, class names, IDs, and stylesheet text. Page text is read temporarily, on the spot, for contrast decisions. It is neither stored nor sent.

## Contact

For support, bug reports, and privacy questions, email `aswdf2b7+ddt-support@gmail.com` (including "[DDT Support]" in the subject helps). The support page opened from "Feedback / Support" in the popup lets you copy the address, subject, and a message template. The template contains only the extension version, the Chrome major version, and the OS name.

## Support link

The popup and the support page contain an optional link to Buy Me a Coffee. It opens that page in a new tab only when you click it. The extension sends no data to that service.

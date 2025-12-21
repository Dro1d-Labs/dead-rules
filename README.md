![iOS](https://img.shields.io/badge/iOS-18+-lightgrey.svg)
![Privacy](https://img.shields.io/badge/Privacy-100%25%20Local-green.svg)
![Rules](https://img.shields.io/badge/Rules-48k%20Active-brightgreen.svg)
![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)

# De-Ad Blocking Rules

Open, auditable content blocking rules used by **[De-Ad](https://dro1d.org/dead.html)** — a minimal Safari ad blocker for iOS.

## Philosophy

De-Ad blocks ads without ever looking at what you browse.
- 100% offline, on-device processing
- No tracking, telemetry, or analytics
- No remote rule execution
- Fully auditable and transparent
- Free forever (app has optional Pro themes)

## How It Works
De-Ad provides Safari with a curated blocklist (`blockerList.json`) that:
1. Safari's WebKit engine compiles into optimized rules
2. Blocks ads, trackers, and analytics **before** they load
3. Runs entirely on your device
4. Never sees your browsing history (by design of Apple's Content Blocker API)

## What's Included
- ✅ 48 000 precision-trimmed rules (Safari’s safe limit)
- ✅ Curated third-party blocklists (see [RULES.md](RULES.md))
- ✅ dro1d labs custom extras (cookie banners, social pixels)
- ✅ 100 % on-device operation — no telemetry
- ✅ Human-readable JSON for full transparency

## What's NOT Included
- ❌ App source code (app is proprietary, rules are open)
- ❌ User data (we don't collect any)
- ❌ Telemetry or analytics
- ❌ Remote update infrastructure

## File Structure

dead-rules/
├── blockerList.json        # The actual Safari Content Blocker rules
├── RULES.md                # Detailed source attribution
├── CHANGELOG.md            # Version history
└── LICENSE                 # MIT License

## Updates
Rules regenerate **weekly** (or sooner for urgent fixes) and ship with every App-Store update.

Check [CHANGELOG.md](CHANGELOG.md) for recent additions.

## Using These Rules
These rules are automatically bundled with the **De-Ad iOS app**. They update when you update the app from the App Store.

**Want to use them elsewhere?**  
The rules are Safari Content Blocker format. You can use them in any compatible iOS/macOS app, but De-Ad is built specifically for these rules. Note: Rules are intentionally conservative to avoid site breakage. De-Ad prioritizes privacy without harming usability.

## Transparency Promise
Every domain blocked by De-Ad is visible in `blockerList.json`.  
No hidden rules. No secret exceptions. No paid whitelists.

## Download De-Ad
- **App Store:** [Coming soon]
- **Website:** [dro1d.org/dead.html](https://dro1d.org/dead.html)
- **Privacy Policy:** [dro1d.org/dead-privacy.html](https://dro1d.org/dead-privacy.html)

## License
MIT License - See [LICENSE](LICENSE) for details.

## Support
Questions? Email: [dead@dro1d.org](mailto:dead@dro1d.org)

---

**Made by [dro1d labs](https://dro1d.org)**  
Privacy-first software for iOS & macOS
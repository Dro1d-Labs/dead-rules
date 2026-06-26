![iOS](https://img.shields.io/badge/iOS-16+-lightgrey.svg)
![Privacy](https://img.shields.io/badge/Privacy-100%25%20Local-green.svg)
![Rules](https://img.shields.io/badge/Rules-148k%20Across%204%20Blockers-brightgreen.svg)
![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)

# De-Ad Blocking Rules

Open, auditable content blocking rules used by **[De-Ad](https://dro1d.org/dead.html)** — a minimal, anti-surveillance Safari ad blocker for iOS.

---

## Philosophy

**De-Ad blocks ads without ever looking at what you browse.**

Most ad blockers inspect the active page to apply complex cosmetic fixes. De-Ad refuses to do this.

- **No Safari App Extension:** We do not have permission to read your URL or page content.
- **No Automatic Reloads:** We do not perform background actions.
- **Zero-Knowledge Architecture:** If a site breaks, *you* decide to whitelist it using manual tools. The app never makes decisions for you.

---

## How It Works

Safari caps each content blocker at 50,000 rules, but loads every enabled blocker at once. De-Ad ships **four** categorized blockers (ads, trackers, annoyances, extra) so the budgets stack — ~148,000 rules total instead of one capped list.

1. Each blocker is generated as its own list (`blockerList_<category>.json`).
2. Safari's WebKit engine compiles these rules into bytecode.
3. Ads and trackers are blocked at the network level **before** they load.
4. Whitelisted domains are injected per-blocker via local App Groups on your device, keeping the bundled lists intact.

---

## What's Included

- ✅ **~148,000 Rules Across 4 Blockers:** ads, trackers, annoyances and an extended domain list, each under Safari's per-blocker cap.
- ✅ **Domain + Path Blocking:** whole-domain rules plus converted path/URL rules (e.g. `/pagead/`) and fetch/XHR beacon blocking.
- ✅ **Smart Consolidation:** Blocks ad networks (e.g., `doubleclick.net`) while protecting shared content hosts.
- ✅ **Curated Sources:** Peter Lowe, AdAway, EasyList, EasyPrivacy, Fanboy and HaGeZi Pro (see [RULES.md](RULES.md)).
- ✅ **100% Offline:** No telemetry, no "cloud" lookups.

---

## What's NOT Included

- ❌ App source code (app is proprietary, rules are open)
- ❌ User data collection
- ❌ "Acceptable Ads" (we don't take money to let ads through)
- ❌ Remote execution

---

## File Structure
```
dead-rules/
├── blockerList.json              # Ads list (alias, for the primary extension)
├── blockerList_ads.json          # Ads blocker
├── blockerList_trackers.json     # Trackers blocker
├── blockerList_annoyances.json   # Annoyances blocker (incl. cosmetic rules)
├── blockerList_extra.json        # Extended domain blocker
├── RuleMeta.json                 # Aggregate + per-blocker rule counts
├── RULES.md                      # Detailed source attribution
├── SOURCES.md                    # Full upstream attribution
├── CHANGELOG.md                  # Version history
└── LICENSE                       # MIT License
```

---

## Updates

Rules are regenerated weekly and shipped with every App Store update.

---

## Transparency Promise

Every domain blocked by De-Ad is visible in the `blockerList_*.json` files.  
No hidden rules. No secret exceptions. No paid whitelists.

---

## Download De-Ad

- **App Store:** [apps.apple.com/us/app/de-ad/id6756549794](https://apps.apple.com/us/app/de-ad/id6756549794)
- **Website:** [dro1d.org/dead.html](https://dro1d.org/dead.html)
- **Privacy Policy:** [dro1d.org/dead-privacy.html](https://dro1d.org/dead-privacy.html)

---

## License

MIT License - See [LICENSE](LICENSE) for details.

---

## Support

Questions? Email: [dead@dro1d.org](mailto:dead@dro1d.org)

---

**Made by [dro1d labs](https://dro1d.org)**  
Privacy-first software for iOS & macOS
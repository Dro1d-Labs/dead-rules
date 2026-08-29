![iOS](https://img.shields.io/badge/iOS-16+-lightgrey.svg)
![Privacy](https://img.shields.io/badge/Privacy-100%25%20Local-green.svg)
![Rules](https://img.shields.io/badge/Rules-163k%20Across%204%20Blockers-brightgreen.svg)
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

Safari caps each content blocker at 50,000 rules, but loads every enabled blocker at once. De-Ad ships **four** categorized blockers (ads, trackers, annoyances, extra) so the budgets stack — ~196,000 rules total instead of one capped list. As of v1.4.9 all four sit at their 49,000-rule budget.

1. Each blocker is generated as its own list (`blockerList_<category>.json`).
2. Safari's WebKit engine compiles these rules into bytecode.
3. Ads and trackers are blocked at the network level **before** they load.
4. Whitelisted domains are injected per-blocker via local App Groups on your device, keeping the bundled lists intact.

Since the cap is per blocker, a category with more candidates than budget (ads, trackers) would otherwise throw domains away while another list sits under its own budget. As of v1.4.8 those overflow domains are **re-homed into whichever list still has room**, which is why `annoyances` holds more rules than its own sources produce — `CHANGELOG.md` records how many moved and where from. A re-homed rule is identical to what it would have been in its original list, so nothing about matching behaviour changes.

Upstream lists ship `@@` exception rules — the rules that keep their own generic patterns from breaking sign-ins, video players and checkouts. Safari applies an exception only to rules earlier in the **same** list, so every blocker needs its own copy. As of v1.5.1 each blocker keeps only the exceptions its own rules can actually trigger: an exception about a video player on one site has nothing to act on in a list holding no rule that matches that site, so those slots go to blocking instead. An exception is dropped only when no rule in that list can reach it. Because Safari matches `url-filter` as a search rather than a full match, an exception like `@@||example.com^` covers *every* URL on that host, so it is kept whenever the list holds rules that can match on any host — in practice that means the reclaim comes almost entirely from `extra`, which holds only whole-domain rules. An unanchored pattern or a wildcard path keeps its exception too. The freed slots go to domains that were over budget. Nothing that could protect a site is removed: a rule that cannot match cannot protect anything.

Every release is checked before it ships: `validate_lists.py` proves each list is schema-valid and under cap with its exception rules correctly trailing, `spotcheck.py` simulates WebKit's matcher to confirm that sign-in, payment and CDN hosts stay reachable while known ad and tracker hosts stay blocked, and `check_exceptions.py` takes every exception a list no longer carries and proves that list has nothing left for it to cancel.

---

## What's Included

- ✅ **~196,000 Rules Across 4 Blockers:** ads, trackers, annoyances and an extended domain list, each under Safari's per-blocker cap.
- ✅ **Domain + Path Blocking:** whole-domain rules plus converted path/URL rules (e.g. `/pagead/`) and fetch/XHR beacon blocking.
- ✅ **Smart Consolidation:** Blocks ad networks (e.g., `doubleclick.net`) while protecting shared content hosts.
- ✅ **Curated Sources:** Peter Lowe, AdAway, EasyList, EasyPrivacy, Fanboy, HaGeZi Light and AdGuard Tracking Protection (see [RULES.md](RULES.md)).
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
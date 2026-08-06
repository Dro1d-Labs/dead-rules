# Rule Sources & Attribution

De-Ad uses a curated combination of well-maintained public blocklists and custom refinements optimized for Safari on iOS.

## Upstream Sources

### 1. Peter Lowe's Ad & Tracking Server List
**Source:** [https://pgl.yoyo.org/adservers/](https://pgl.yoyo.org/adservers/)  
**License:** Public Domain  
**Coverage:** ~3 500 well-known ad servers  
**Why we use it:** Conservative, stable, minimal false positives

### 2. AdAway Hosts
**Source:** [https://adaway.org/](https://adaway.org/)  
**License:** CC BY 3.0  
**Coverage:** ~6 500 mobile-focused ad domains  
**Why we use it:** Mobile-first approach, good regional coverage

### 3. EasyList
**Source:** [https://easylist.to/](https://easylist.to/)  
**License:** GPL v3 / CC BY-SA 3.0  
**Coverage:** Core ad filter list — domains **and** path/URL rules  
**Why we use it:** The backbone of the ads blocker; we convert its network rules to Safari format

### 4. EasyPrivacy
**Source:** [https://easylist.to/](https://easylist.to/)  
**License:** GPL v3 / CC BY-SA 3.0  
**Coverage:** ~53 000 tracking/analytics hosts  
**Why we use it:** Industry-standard privacy list — powers the trackers blocker

### 5. Fanboy's Annoyance & Cookiemonster
**Source:** [https://secure.fanboy.co.nz/](https://secure.fanboy.co.nz/)  
**License:** GPL v3 / CC BY-SA 3.0  
**Coverage:** Cookie notices, social widgets, in-page annoyances  
**Why we use it:** Powers the annoyances blocker (incl. cosmetic `css-display-none` rules)

### 6. HaGeZi Light
**Source:** [https://github.com/hagezi/dns-blocklists](https://github.com/hagezi/dns-blocklists)  
**License:** GPL v3  
**Coverage:** Curated, low-false-positive modern ad/tracker domain list  
**Why we use it:** Fills the extended blocker. Sized to fit the per-blocker budget. Read from upstream's `adblock/` build.

### 7. AdGuard Tracking Protection
**Source:** [https://github.com/AdguardTeam/AdguardFilters](https://github.com/AdguardTeam/AdguardFilters)  
**License:** GPL v3  
**Coverage:** Tracking, analytics and telemetry endpoints  
**Why we use it:** Added in v1.4.9 to broaden tracker coverage across the trackers blocker and the lists it spills into. Its upstream exception rules come with it.

### 8. dro1d labs Custom Rules
**Source:** Curated internally  
**License:** MIT (this repository)  
**Coverage:** 
- Cookie consent banners & GDPR popups
- Social media tracking pixels
- Analytics scripts not covered by upstream
- Regional ad networks (IE, UK, EU focus)

## Processing Pipeline
1. **Download** upstream sources  
2. **Categorize** into four blockers: ads, trackers, annoyances, extra  
3. **Merge** & deduplicate using public-suffix consolidation (cross-blocker dedup)  
4. **Convert** domain rules **and** EasyList path/URL rules to Safari Content-Blocker JSON (each generated `url-filter` is validated)  
5. **Score & rank** by source corroboration and coverage  
6. **Enforce** a ~49 000-rule ceiling **per blocker** (Safari's 50k hard-limit minus whitelist headroom)  
7. **Bundle** one list per content-blocker extension with the De-Ad iOS app

## Rule Format
Safari Content Blocker JSON with these action types:
- `block` – Prevent a resource from loading (domain and path/URL rules)
- `css-display-none` – Hide elements (cookie banners, etc.)
- `ignore-previous-rules` – Per-site whitelist, injected on-device at runtime

## Update Schedule
Rules are updated monthly and ship with De-Ad app updates via the App Store.

## Contributing
Found a false positive? Site not working?  
Email: [support@dro1d.org](mailto:support@dro1d.org)

## No Paid Exceptions
De-Ad has zero "acceptable ads" programs.  
No paid whitelists. No secret exceptions.  
If it's in the blocklist, it's blocked.
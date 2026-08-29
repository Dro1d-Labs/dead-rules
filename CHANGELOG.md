# Changelog

## v1.5.1 – August 2026

- 196,000 rules across 4 content blockers
  - `ads`: 49,000 (41,724 domain, 3,248 network, 0 cosmetic, 4,020 exception) + 8 re-homed from trackers 8
  - `trackers`: 49,000 (36,979 domain, 8,000 network, 0 cosmetic, 4,021 exception)
  - `annoyances`: 49,000 (781 domain, 2,633 network, 3 cosmetic, 4,016 exception) + 41,567 re-homed from trackers 41,567
  - `extra`: 49,000 (27,314 domain, 0 network, 0 cosmetic, 786 exception) + 20,900 re-homed from ads 10,583, trackers 10,317
- 59,213 domains re-homed from a blocker that hit the 50,000-rule cap into one with spare budget
- 4,028 upstream exception rules honoured (ads 4,020, trackers 4,021, annoyances 4,016, extra 786)
- 3,269 exception rules dropped from lists that held nothing for them to cancel, and the freed slots spent on 3,269 more blocked domains. Almost all of it is `extra`, which holds only whole-domain rules; a list containing rules that can match on any host keeps essentially all of its exceptions
- 7,622 redundant subdomain rules collapsed under a listed apex

## v1.4.9 – August 2026

- 196,000 rules across 4 content blockers
  - `ads`: 49,000 (41,742 domain, 3,239 network, 0 cosmetic, 4,019 exception)
  - `trackers`: 49,000 (36,981 domain, 8,000 network, 0 cosmetic, 4,019 exception)
  - `annoyances`: 49,000 (770 domain, 2,625 network, 3 cosmetic, 4,019 exception) + 41,583 re-homed from trackers 41,583
  - `extra`: 49,000 (27,599 domain, 0 network, 0 cosmetic, 4,019 exception) + 17,382 re-homed from ads 16,336, trackers 1,046
- 58,965 domains re-homed from a blocker that hit the 50,000-rule cap into one with spare budget
- 4,019 upstream exception rules honoured per blocker
- 7,608 redundant subdomain rules collapsed under a listed apex

## v1.4.8 – July 2026

- 163,368 rules across 4 content blockers
  - `ads`: 49,000 (43,876 domain, 3,227 network, 0 cosmetic, 1,897 exception)
  - `trackers`: 49,000 (39,103 domain, 8,000 network, 0 cosmetic, 1,897 exception)
  - `annoyances`: 16,368 (772 domain, 2,609 network, 3 cosmetic, 1,897 exception) + 11,087 re-homed from ads 5,043, trackers 6,044
  - `extra`: 49,000 (41,228 domain, 0 network, 0 cosmetic, 1,897 exception) + 5,875 re-homed from ads 5,875
- 16,962 domains re-homed from a blocker that hit the 50,000-rule cap into one with spare budget
- 1,897 upstream exception rules honoured per blocker
- 36,577 redundant subdomain rules collapsed under a listed apex
- 0 domains dropped for lack of space (was 19,597 in v1.4.7)

## v1.4.7 – July 2026

- 146,733 rules across 4 content blockers
  - `ads`: 49,000 (43,882 domain, 3,221 network, 0 cosmetic, 1,897 exception)
  - `trackers`: 49,000 (39,103 domain, 8,000 network, 0 cosmetic, 1,897 exception)
  - `annoyances`: 5,276 (770 domain, 2,606 network, 3 cosmetic, 1,897 exception)
  - `extra`: 43,457 (41,560 domain, 0 network, 0 cosmetic, 1,897 exception)
- 1,897 upstream exception rules honoured per blocker
- 37,100 redundant subdomain rules collapsed under a listed apex

## v1.4.6 – June 2026
- Blocklist updated

## v1.4.5 – June 2026
- Blocklist updated

## v1.4.4 – May 2026
- Blocklist updated
- Whitelist search & export added
- New premium theme

## v1.4.3 – May 2026
- Blocklist enhanced & updated

## v1.4.2 – May 2026
- Fixed Site Rescue feature
- Improved Site Rescue UI with clearer usage instructions  
- Updated protection test page for better accuracy

## v1.4.1 – May 2026
- Blocklist enhanced & updated
- De-Ad theme: custom geometric text + logo integration [Premium]
- Redesigned Home & Protection Scope card [Premium]
- Added FAQ section
- Cookie Monster & Annoyance blocklists added
- 6 blocklist sources, ~40k optimized rules
- Test at dro1d.org/dead

## v1.3.6 – April 2026
- Blocklist update

## v1.3.5 – April 2026
- Blocklist update

## v1.3.4 – April 2026
- Blocklist update
- Rule MetaData enhancements

## v1.3.3 – March 2026
- Blocklist update

## v1.3.2 – March 2026
- Blocklist update

## v1.3.1 – March 2026
- Blocklist update
- iOS extension compatibility fix

## v1.2.8 – February 2026
- Blocklist update
- Performance enhancements

## v1.2.7 – February 2026
- Blocklist update

## v1.2.6 – January 2026
- Blocklist update

## v1.2.5 – January 2026
- Blocklist update

## v1.2.4 – January 2026
- Blocklist update
- Blocklist update

## v1.2.3 – January 2026
- Blocklist update
- Blocklist update

## v1.2.2 – January 2026
- Blocklist update
- Blocklist update
- Blocklist update

## v1.2.1 – December 2025
- Blocklist update
- Performance enhancements

## v1.1 – December 2025
- Consolidated duplicate domains via public-suffix logic
- Trimmed list to Safari-safe 48 000 rule ceiling
- Replaced vanity analytics with higher-value entries
- Added EU media telemetry endpoints

## v1.0 – December 2025
Initial public release of De-Ad blocking rules

## Updates
Rules are updated weekly and bundled with app updates

## v0.1 – Initial Publication
- Repository created
- Privacy-first philosophy documented
- Initial structure established
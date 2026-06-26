# Detailed Source Attribution

This document provides complete attribution for all upstream blocklists used in De-Ad.

## Public Blocklists

### Peter Lowe's Ad & Tracking Server List
- **URL:** https://pgl.yoyo.org/adservers/
- **Maintainer:** Peter Lowe
- **License:** Public Domain
- **Format:** Hosts file
- **Last Retrieved:** June 2026
- **Approximate Rules:** ~3 500

### AdAway Default Blocklist
- **URL:** https://adaway.org/hosts.txt
- **Maintainer:** AdAway Project
- **License:** CC BY 3.0
- **Format:** Hosts file
- **Last Retrieved:** June 2026
- **Approximate Rules:** ~6 500

### EasyList
- **URL:** https://easylist.to/easylist/easylist.txt
- **Maintainer:** EasyList Community
- **License:** GPL v3 / CC BY-SA 3.0
- **Format:** ABP/uBlock filter syntax (domains + path/URL rules, converted)
- **Last Retrieved:** June 2026
- **Used by:** ads blocker

### EasyPrivacy
- **URL:** https://easylist.to/easylist/easyprivacy.txt
- **Maintainer:** EasyList Community
- **License:** GPL v3 / CC BY-SA 3.0
- **Format:** ABP/uBlock filter syntax (converted)
- **Last Retrieved:** June 2026
- **Used by:** trackers blocker

### Fanboy's Annoyance & Cookiemonster
- **URL:** https://secure.fanboy.co.nz/fanboy-annoyance.txt , https://secure.fanboy.co.nz/fanboy-cookiemonster.txt
- **Maintainer:** Fanboy / EasyList Community
- **License:** GPL v3 / CC BY-SA 3.0
- **Format:** ABP/uBlock filter syntax (converted)
- **Last Retrieved:** June 2026
- **Used by:** annoyances blocker

### HaGeZi Pro
- **URL:** https://raw.githubusercontent.com/hagezi/dns-blocklists/main/hosts/pro.txt
- **Maintainer:** HaGeZi
- **License:** GPL v3
- **Format:** Hosts file
- **Last Retrieved:** June 2026
- **Used by:** extended blocker

## Custom Rules

### dro1d labs Ruleset
- **Maintainer:** dro1d labs Limited
- **License:** MIT (this repository)
- **Format:** Safari Content Blocker JSON
- **Categories:**
  - Cookie consent banners (GDPR, cookie notices)
  - Social media tracking pixels (Facebook Pixel, Twitter, etc.)
  - Analytics providers not covered upstream
  - Regional ad networks (Ireland, UK, EU)

## Rule Conversion Notes

Upstream lists are in various formats (hosts files, ABP syntax). De-Ad converts all to Safari's Content Blocker JSON format:

json
{
  "trigger": {
	"url-filter": ".*example\\.com.*",
	"resource-type": ["script", "image"]
  },
  "action": {
	"type": "block"
  }
}


## Acknowledgments

De-Ad wouldn't exist without the tireless work of open-source blocklist maintainers. Huge thanks to:
- Peter Lowe
- The AdAway team
- The EasyList community
- All contributors to public blocklists
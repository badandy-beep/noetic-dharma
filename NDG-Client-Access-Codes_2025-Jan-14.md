# NDG Client Access Codes Reference
**Source:** Extracted from ndg-website-v2/lib/access-map.ts  
**Date:** 14-Jan-2025  
**Status:** Active codes for client-access.html implementation

---

## Access Code Format
`PROJECT-XXXXXX` (Project name + 6-digit code)

---

## Active Project Codes

| Access Code | Project Slug | Display Name | Status |
|-------------|--------------|--------------|--------|
| `MAHA-972028` | project-maha | Project MAHA | Has modules defined |
| `USAX-687173` | project-usax | Project USAX | Placeholder |
| `WEBUILT-398960` | project-webuilt | Project WEBUILT | Placeholder |
| `WARROOM-482177` | project-warroom | Project WARROOM | Placeholder |
| `GARY-535231` | project-gary | Project GARY | Placeholder |
| `EMBLEM-146236` | project-emblem | Project EMBLEM | Placeholder |
| `NIKOLAELECTRIC-411400` | project-nikolaelectric | Project NIKOLA ELECTRIC | Placeholder |

---

## Project MAHA Modules (Example Structure)

| Module Title | File Type | URL |
|--------------|-----------|-----|
| Executive Brief | PDF | # (placeholder) |
| Strategic Thesis | PDF | # (placeholder) |
| Operating Plan | PDF | # (placeholder) |
| Financial Model | XLSX | # (placeholder) |
| Projections & Scenarios | PDF | # (placeholder) |
| Board Materials | PDF | # (placeholder) |

---

## Implementation Notes

1. **Code validation:** Case-insensitive, trim whitespace
2. **Logo paths:** `/client-logos/project-{slug}.png` (need to create these)
3. **Security:** Codes should be stored server-side or in environment variables for production
4. **noindex:** Client access pages should have `<meta name="robots" content="noindex">` for privacy

---

## TODO Before Launch

- [ ] Create client logo images for each project
- [ ] Upload actual PDFs/XLSX files for each module
- [ ] Update URLs from `#` to actual file paths
- [ ] Consider moving codes to environment variables or backend API
- [ ] Test all access flows on mobile

---

© 2025 Noetic Dharma Group, LLC | CONFIDENTIAL & PROPRIETARY

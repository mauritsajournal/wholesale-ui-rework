# Wholesale UI Rework — wholesale.a-journal.nl

CSS-only UI retouch for the B2B wholesale site. All changes go in the Kalium child theme `style.css`.

## Current status: v4 on staging

Staging URL: `wholesaledwdawd-suxs.wp1.sh`

## Files

| File | Description |
|------|-------------|
| `style-original.css` | Original child theme (empty, just theme header) |
| `style-v1.css` | First attempt — header + buttons + cards |
| `style-v3.css` | Header fix with Kalium CSS vars, card borders, filter cleanup |
| `style-v4-current.css` | **Current on staging** — bigger logo, thinner header, larger titles, card padding, narrower sidebar |

## How to deploy to production

Copy `style-v4-current.css` (or whichever version you approve) to the child theme:
```
/wp-content/themes/kalium-child/style.css
```

Then flush LiteSpeed Cache + object cache.

## How to rollback

Copy `style-original.css` to the child theme `style.css`. Flush cache.

## Changes in v4 (current)

### Header
- Logo: 150px → 90px default, 40px when sticky scrolled
- Row padding: reduced to 2px (header is essentially just the logo height)
- Subtle shadow on sticky
- Uses Kalium's own `--k-logo-height` CSS variable so sticky JS animation works

### Product Cards
- Light border (#eaeaea), 10px rounded corners
- Hover: border darkens, shadow appears, 2px lift, image zooms 1.03x
- 6px padding-top on image area (prevents clipping on hover zoom)
- Titles: 15px, weight 500, dark (#1a1a1a)
- Price: 14.5px, weight 600

### Buttons
- 8px rounded, no uppercase, hover lift + teal glow shadow
- Grid add-to-cart: 6px rounded, 12.5px font

### Sidebar / Filters
- Sidebar width: 200px on desktop (was default ~25%)
- Off-canvas drawer: 260px max
- Filter titles: 11.5px uppercase, muted gray
- Filter items: 13px, compact spacing

### Small touches
- Body text: #444 (softer than black)
- Form inputs: 6px rounded corners
- WooCommerce notices: left border accent instead of top

## What's NOT changed
- Colors (teal #247c74 kept as-is)
- Font (Museo Sans via Typekit)
- Layout structure (Kalium theme)
- Database CSS (kalium_skin_custom_css option)
- No plugins added/removed/deactivated
- No PHP changes

## Open items for next iteration
- [ ] Sidebar still possibly too wide — user feedback pending
- [ ] Consider color update (teal → brand blue #4361ee) in future
- [ ] Product card titles — size confirmed at 15px but may need further review
- [ ] Header padding — currently 2px, logo 90px. Balance TBD

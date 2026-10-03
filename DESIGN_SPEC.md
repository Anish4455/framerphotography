# Photography Template — Design Spec

Working name: **Noir** (alternatives: Umbra, Aperture, Lumen, Grain)
Category: Photography / Portfolio
Audience: Solo photographer (portrait, editorial, wedding, travel)
Direction: Dark cinematic — full-bleed imagery, film-like motion, restrained type.

---

## 1. Design tokens

### Color
| Token            | Value     | Use                                   |
|------------------|-----------|---------------------------------------|
| `bg/base`        | `#0B0B0C` | Page background                       |
| `bg/raised`      | `#141416` | Cards, nav on scroll, footer          |
| `bg/overlay`     | `rgba(11,11,12,0.6)` | Image scrims, lightbox     |
| `text/primary`   | `#EDEAE4` | Headlines, body (warm off-white)      |
| `text/secondary` | `#8A8780` | Captions, meta, labels                |
| `line`           | `#26262A` | Dividers, borders                     |
| `accent`         | `#C8A46A` | Links on hover, active states (brass) |

### Typography
- **Display:** a high-contrast serif, e.g. *Instrument Serif* or *Fraunces*. Use italic for emphasis.
- **Text / UI:** *Inter* or *Geist*, with tight tracking for headings and +4% uppercase for labels.

| Style      | Desktop       | Tablet | Mobile | Notes                     |
|------------|---------------|--------|--------|---------------------------|
| Display XL | 160 / 0.9     | 112    | 64     | Serif, -2% tracking       |
| Display L  | 96 / 1.0      | 72     | 44     | Serif                     |
| H2         | 48 / 1.1      | 40     | 32     | Serif                     |
| H3         | 24 / 1.3      | 22     | 20     | Sans, medium              |
| Body       | 17 / 1.6      | 17     | 16     | Sans                      |
| Label      | 12 / 1.2      | 12     | 11     | Sans, uppercase, +8%      |

### Layout
- Breakpoints: Desktop 1440, Tablet 810, Mobile 390 (Framer defaults).
- 12-column grid, 24px gutter, 40px side margin on desktop, 20px on mobile.
- Spacing scale: 4, 8, 12, 16, 24, 32, 48, 64, 96, 160.
- Radius: 0 on images (cinematic, sharp edges) and 999 on pills/buttons.

### Motion
- Ease: `cubic-bezier(0.22, 1, 0.36, 1)`, 700–900ms on reveals.
- Image reveal: clip-path from bottom plus a scale from 1.08 to 1.
- Text reveal: line-by-line slide-up with a 60ms stagger.
- Subtle film-grain overlay (fixed, 4–6% opacity).
- Custom cursor: a small dot that grows into a "View" disc over projects.

---

## 2. Sitemap

1. **Home** `/`
2. **Work** `/work` (CMS: Projects)
3. **Project detail** `/work/:slug`
4. **About** `/about`
5. **Journal** `/journal` and `/journal/:slug` (CMS: Posts)
6. **Contact / Booking** `/contact`
7. **404**

---

## 3. Page sections

### Home
1. **Nav**: logo wordmark on the left, with Work · About · Journal · Contact and a "Book a session" pill on the right. Transparent at first, then `bg/raised` with blur once the page scrolls.
2. **Hero**: full-viewport image or video loop. A Display XL name sits bottom-left, with discipline and location labels bottom-right and a scroll cue.
3. **Intro statement**: a two-line serif statement with italic emphasis and a small portrait inset.
4. **Selected work**: a staggered asymmetric grid of six projects. Each shows the title, year and category, and the image scales on hover.
5. **Horizontal reel**: a pinned horizontal scroll strip of film frames, with frame numbers as captions.
6. **Services**: an accordion list of Portraits, Editorial, Weddings and Commercial, with a hover image preview that follows the cursor.
7. **Clients / Publications**: a monochrome logo marquee.
8. **Testimonial**: one large quote with a client name.
9. **CTA**: Display L "Let's make something timeless" with a booking button.
10. **Footer**: email, socials, location, local time, a back-to-top link and a large wordmark.

### Work
- A filter bar (All / Portrait / Editorial / Wedding / Travel) with a grid/list view toggle.
- The list view shows rows with title, client and year, plus a hover image preview.

### Project detail
- Full-bleed cover with the title, plus meta (Client, Year, Location, Camera).
- A short story paragraph.
- A mixed gallery: full-width, 2-up and 3-up rows that open in a lightbox.
- A "Next project" footer with a full-bleed teaser.

### About
- Portrait with a bio, a "Gear" list, an awards/press timeline and a process in three steps.

### Journal
- An editorial list with a featured post and a post template with large images.

### Contact / Booking
- A form with name, email, session type (select), date, budget range and message.
- An FAQ accordion and availability text.

---

## 4. CMS collections

**Projects**: title, slug, category (option), client, year, location, camera, cover image, cover video (optional), summary, story (rich text), gallery (image array), featured (toggle), order.

**Posts**: title, slug, date, cover, excerpt, body (rich text), tags.

---

## 5. Components (with variants)

- `Nav` — desktop / tablet / mobile (open & closed)
- `Button` — primary pill / ghost / text link with arrow
- `ProjectCard` — large / medium / small, plus a hover state
- `ProjectRow` — default / hover
- `ServiceItem` — closed / open
- `Lightbox`
- `Marquee`
- `Footer` — desktop / mobile
- `Cursor` — default / view / drag

---

## 6. Marketplace listing (draft)

- **Title:** Noir — Cinematic Photography Portfolio
- **Tagline:** A dark, film-inspired portfolio template for photographers who let the image speak.
- **Categories:** Photography, Portfolio, Personal
- **Highlights:** CMS-powered projects & journal, cinematic scroll animations, lightbox gallery, booking form, fully responsive, easy-to-edit styles.
- **Pages:** Home, Work, Project, About, Journal, Post, Contact, 404.

---

## 7. Build checklist

- [ ] Set up color and text styles in Framer
- [ ] Build components and variants
- [ ] Set up CMS collections with 8 sample projects and 4 posts
- [ ] Build pages at all three breakpoints
- [ ] Add interactions (reveals, cursor, horizontal scroll, lightbox)
- [ ] Use licensed / royalty-free imagery only (e.g. Unsplash), with credits kept
- [ ] SEO: page titles, descriptions, OG images
- [ ] Performance pass (image sizes, lazy loading)
- [ ] Preview thumbnails and screenshots for the marketplace submission

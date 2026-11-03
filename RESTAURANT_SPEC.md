# Restaurant Template — Design Spec

Working name: **Hearth** (alternatives: Saffron, Ember, Larder, Table & Tide)
Category: Restaurant / Hospitality
Audience: Independent restaurants, bistros, wine bars and cafés with one or two locations.
Direction: Warm editorial. It reads like a printed menu, with cream paper tones, a terracotta accent, large serif type, generous food photography and quiet motion. It is deliberately the opposite of Emulsion's dark cinematic look, so the two templates feel distinct in your marketplace profile.

---

## 1. Design tokens

### Color
| Token            | Value     | Use                                         |
|------------------|-----------|---------------------------------------------|
| `bg/base`        | `#F4EEE3` | Page background (menu-paper cream)          |
| `bg/raised`      | `#EBE2D2` | Cards, menu panels, footer                  |
| `bg/inverse`     | `#1F1A16` | Dark bands (reservation CTA, night menu)    |
| `text/primary`   | `#1F1A16` | Headlines, body (warm espresso)             |
| `text/secondary` | `#6E6358` | Descriptions, meta, prices                  |
| `text/inverse`   | `#F4EEE3` | Text on dark bands                          |
| `line`           | `#D6CBB8` | Menu dividers, dotted leaders               |
| `accent`         | `#B4532A` | Buttons, links, active tab (terracotta)     |
| `accent/soft`    | `#E7C9B4` | Tags (V, VG, GF), hover fills               |
| `herb`           | `#5C6B47` | Secondary accent: seasonal and special badges |

Check contrast: `text/secondary` on `bg/base` and `accent` on `bg/base` must both pass WCAG AA for body text. Darken them slightly if they fail in Framer's checker.

### Typography
- **Display:** a warm serif with personality, e.g. *Fraunces* (soft, high optical size) or *Instrument Serif*. Use italic for dish names and emphasis.
- **Text / UI:** *Inter* or *DM Sans*.
- **Menu prices:** tabular numbers (`font-variant-numeric: tabular-nums`) so prices line up.

| Style        | Desktop   | Tablet | Mobile | Notes                         |
|--------------|-----------|--------|--------|-------------------------------|
| Display XL   | 144 / 0.95| 104    | 60     | Serif, -2% tracking           |
| Display L    | 88 / 1.0  | 64     | 42     | Serif                         |
| H2           | 48 / 1.1  | 40     | 32     | Serif                         |
| H3 / Dish    | 24 / 1.25 | 22     | 20     | Serif italic                  |
| Body         | 17 / 1.6  | 17     | 16     | Sans                          |
| Small        | 14 / 1.5  | 14     | 14     | Sans, dish descriptions       |
| Label        | 12 / 1.2  | 12     | 11     | Sans, uppercase, +10% tracking|

### Layout
- Breakpoints: Desktop 1440, Tablet 810, Mobile 390.
- 12-column grid, 24px gutter, 48px side margin on desktop, 20px on mobile.
- Spacing scale: 4, 8, 12, 16, 24, 32, 48, 64, 96, 144.
- Radius: 4 on images and cards (soft, printed feel), 999 on buttons and tags.
- Arched image masks (`border-radius: 999px 999px 0 0`) as the signature shape for the hero and chef portrait.

### Motion
- Ease: `cubic-bezier(0.22, 1, 0.36, 1)`, 600–800ms.
- Images fade up and unmask from the arch. Text reveals line by line.
- Menu tabs cross-fade (200ms). Dish rows show a small photo preview on hover (desktop only).
- A sticky "Reserve" pill appears after the hero on mobile.
- Respect reduced motion: turn reveals into simple fades.

---

## 2. Sitemap

1. **Home** `/`
2. **Menu** `/menu` (CMS: Menu Items, grouped by Menu)
3. **About / Story** `/about`
4. **Reservations** `/reservations`
5. **Private Dining & Events** `/private-dining`
6. **Events / What's On** `/events` and `/events/:slug` (CMS: Events)
7. **Gallery** `/gallery`
8. **Contact & Location** `/contact`
9. **Journal** `/journal` and `/journal/:slug` (CMS: Posts). Optional, but buyers value it for SEO.
10. **404**

---

## 3. Page sections

### Home
1. **Announcement bar**: a dismissible strip for "New autumn menu — now serving" or holiday hours.
2. **Nav**: centered wordmark with Menu · About · Events · Private Dining on the left and Contact plus a "Book a table" pill on the right. Mobile nav is a full-screen overlay with large serif links, plus the address and hours.
3. **Hero**: an arched full-height food or interior image. Display XL "Seasonal cooking, open fire" sits beside it, with an opening-hours line and two buttons: Book a table and View menu.
4. **Intro**: a short philosophy paragraph, a chef's signature image and a small "Since 2014" label.
5. **Menu preview**: tabs for Lunch / Dinner / Drinks, each with 5–6 dishes. Each row shows the dish name, a dotted leader and the price, with the description and dietary tags below, plus a "Full menu" link.
6. **Signature dishes**: a horizontal carousel of 4–6 dish cards (photo, name, one-line note).
7. **Chef / Story teaser**: a portrait in an arch with a pull-quote and a "Our story" link.
8. **Reservation band**: a dark (`bg/inverse`) section with a date, time and party-size picker or an embedded booking widget, and a phone number as a fallback.
9. **Events**: the next 3 events from the CMS (wine dinner, live music, supper club).
10. **Press & reviews**: a quote carousel from press, a marquee of publication logos and a star rating.
11. **Instagram-style gallery strip**: 6 square images linking to the Gallery page.
12. **Visit us**: an embedded map, the address, a weekly hours table, transport/parking notes and a Directions button.
13. **Footer**: newsletter sign-up, hours, address, socials, a gift-card link and a large wordmark.

### Menu
- A sticky sub-nav for Breakfast / Lunch / Dinner / Desserts / Wine / Cocktails that scrolls to each section.
- A two-column printed-menu layout on desktop and a single column on mobile.
- Each dish shows name, description, price, dietary tags (V, VG, GF, DF, N), a "Chef's pick" badge and an optional image.
- An allergen note and a "Download PDF menu" button.

### About / Story
- Hero quote, a founding-story timeline (3–4 milestones) and a team grid with chef, sommelier and front-of-house.
- Sourcing: a "Our producers" list with farm names and map pins.
- Values: seasonal, local, zero-waste, each with an icon and a short line.

### Reservations
- A booking form or third-party widget embed (OpenTable, Resy, SevenRooms or Tock; give buyers a slot with instructions).
- A fallback form with name, email, phone, date, time, guests, occasion and notes.
- Policies in an accordion: cancellations, large groups, dietary needs, dress code, children.

### Private Dining & Events
- Spaces as cards: Main room, Chef's table, Terrace, Full buyout. Each shows capacity, an image and a "Enquire" button.
- Sample set menus with per-person price ranges.
- An enquiry form with event type, date, guest count, budget and message.

### Events
- Upcoming / Past filter and event cards with date, title, price and "Book" link.
- The event detail page has a hero, description, menu, time and a booking button.

### Gallery
- A masonry grid filtered by Food / Space / People, opening in a lightbox.

### Contact & Location
- Map, address, phone, email, hours, a contact form, and press and careers emails.
- **Multi-location option:** a Locations collection with a location switcher, for buyers with two sites.

---

## 4. CMS collections

**Menu Items**: name, slug, description, price, menu (option: Breakfast, Lunch, Dinner, Desserts, Wine, Cocktails), section (e.g. Small plates, Mains), dietary tags (multi-option), chef's pick (toggle), image (optional), available (toggle), order.

**Events**: title, slug, date, start time, end time, price, cover image, summary, body (rich text), booking link, featured (toggle).

**Posts**: title, slug, date, cover, excerpt, body (rich text), category (Recipes, News, Producers).

**Team**: name, role, photo, short bio, order.

**Locations** (optional): name, address, map link, phone, email, hours (rich text), booking link, image.

**Sample content:** about 30 menu items across all menus, 4 events, 3 posts, 4 team members and 2 locations.

---

## 5. Components (with variants)

- `Nav`: desktop / tablet / mobile (open and closed), light / on-dark
- `AnnouncementBar`: default / dismissed
- `Button`: primary pill / secondary outline / text link with arrow / on-dark
- `MenuTabs`: one variant per menu, active / inactive
- `DishRow`: default / with image / chef's pick / sold out
- `DietaryTag`: V / VG / GF / DF / N
- `DishCard`: for the signature carousel
- `EventCard`: upcoming / past
- `SpaceCard`: for private dining
- `HoursTable`: full week / compact (today's hours only)
- `ReviewQuote`
- `ReservationForm`: inline / full page
- `NewsletterForm`
- `Footer`: desktop / mobile
- `StickyReserve`: mobile only

---

## 6. Buyer-friendly details (these sell restaurant templates)

- **One place to edit hours, address and phone.** Use Framer variables or one Settings/Locations CMS item, so buyers change them once and they update everywhere.
- **Booking-widget slot** with clear instructions for OpenTable, Resy, SevenRooms and Tock embeds.
- **Downloadable PDF menu** link field.
- **Holiday hours** via the announcement bar.
- **SEO and local search:** a page title and description per page, plus notes in the template guide on adding Restaurant schema (opening hours, address, cuisine, price range) through custom code.
- **Multi-language ready:** keep layouts tolerant of longer strings for Framer Localization (tourist areas).
- **Accessibility:** menu prices are read clearly by screen readers, dietary tags have text labels and not just icons, and focus states are visible.

---

## 7. Marketplace listing (draft)

- **Title:** Hearth — Restaurant & Bistro Template
- **Tagline:** A warm, editorial website for restaurants, bistros and wine bars, with a CMS menu, reservations and events built in.
- **Categories:** Restaurant, Food & Drink, Hospitality, Business
- **Highlights:**
  - CMS-powered menus with prices, dietary tags and chef's picks
  - Reservation section ready for OpenTable, Resy, SevenRooms or Tock
  - Events and private-dining pages with enquiry forms
  - Hours, address and phone edited in one place
  - Optional multi-location support
  - Gallery with lightbox, journal and newsletter sign-up
  - Fully responsive, with smooth, accessible animations
- **Pages:** Home, Menu, About, Reservations, Private Dining, Events, Event, Gallery, Contact, Journal, Post, 404.
- **Suggested price:** in line with other multi-page CMS templates in the category. Check current comparable listings before setting it.

---

## 8. Build checklist

- [ ] Color and text styles, plus variables for hours, phone and address
- [ ] Components and variants (section 5)
- [ ] CMS collections with sample content (section 4)
- [ ] Home page at all three breakpoints, then review
- [ ] Menu, About, Reservations, Private Dining, Events, Gallery, Contact, Journal and 404 pages
- [ ] Interactions: reveals, menu tabs, carousel, lightbox, sticky reserve pill, reduced-motion fallback
- [ ] Licensed / royalty-free food and interior imagery only (e.g. Unsplash), with credits kept
- [ ] SEO titles, descriptions and OG images for every page
- [ ] Accessibility pass: contrast, focus states, form labels
- [ ] Performance pass: image sizes and lazy loading
- [ ] Template guide page for buyers on how to edit the menu, hours and booking widget
- [ ] Marketplace thumbnails, screenshots and preview link

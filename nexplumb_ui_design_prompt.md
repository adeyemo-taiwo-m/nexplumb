# Nexplumb — UI Design Agent Master Prompt
> **Version:** 1.0 | **Type:** Complete UI Design Brief for All Portals  
> **Use this file as your single source of truth when designing every screen of the Nexplumb web application.**

---

## TABLE OF CONTENTS

1. [Project Overview](#1-project-overview)
2. [Design System (Mandatory — Read First)](#2-design-system)
3. [Portal Architecture](#3-portal-architecture)
4. [Phase 1 — Customer Web Portal](#4-phase-1--customer-web-portal)
   - CW-1: Public Homepage
   - CW-S: Customer Sign Up
   - CW-L: Customer Login
   - CW-2: Search Results
   - CW-3: Artisan Public Profile
   - CW-4: Booking Flow (Steps A–D)
   - CW-5: Live Job Tracking
   - CW-6: Customer Dashboard
5. [Phase 1 — Artisan Web Portal](#5-phase-1--artisan-web-portal)
   - AW-1: Artisan Registration
   - AW-2: Artisan Dashboard
   - AW-3: My Jobs
   - AW-4: Earnings & Payouts
   - AW-5: Profile Editor
   - AW-6: Reviews Tab
6. [Phase 1 — Admin Dashboard](#6-phase-1--admin-dashboard)
   - AD-1: Admin Overview
   - AD-2: Jobs Management
   - AD-3: Dispute Resolution
   - AD-4: Verification Queue
   - AD-5: Analytics
   - AD-6: User Management
7. [Phase 2 — Supplier Portal](#7-phase-2--supplier-portal)
   - SP-1: Supplier Registration
   - SP-2: Supplier Dashboard
   - SP-3: Products Catalogue
   - SP-4: Orders Management
8. [Phase 2 — Enhanced Features](#8-phase-2--enhanced-features)
   - CW-E1: Price Estimator
   - CW-E2: Emergency Booking
   - WhatsApp Bot Flow (Reference)
9. [Phase 3 — Ecosystem Portals](#9-phase-3--ecosystem-portals)
   - EP-1: Enterprise B2B Portal
   - FP-1: Artisan Finance Portal
10. [Universal Design Standards](#10-universal-design-standards)
    - Five Required Screen States
    - Accessibility Requirements
    - SEO Standards
    - Design Handoff Standards

---

## 1. PROJECT OVERVIEW

**What is Nexplumb?**  
Nexplumb is a two-sided online marketplace connecting customers in Nigeria (starting in Lagos) with verified, trusted artisans — plumbers, electricians, carpenters, painters, and other tradespeople. Think of it as the Nigerian equivalent of Uber, but for skilled home services.

**The Core Flow:**
1. Customer opens the site → searches for a tradesperson
2. Finds a verified artisan → books and pays safely via escrow
3. Watches the artisan travel to them on a live map
4. Confirms the job is done → payment is released to the artisan
5. Both parties leave reviews

**Who Uses This:**
- **Customers** — homeowners, tenants, and property managers across Lagos
- **Artisans** — plumbers, electricians, carpenters, painters, tilers, and other tradespeople
- **Admins** — Nexplumb's internal operations and support team
- **Suppliers** — companies selling trade materials (pipes, fittings, electrical components, etc.)

**Primary Market:** Lagos, Nigeria. The product must feel culturally relevant and locally authentic — not like a generic Western tech product.

**Key Trust Pillars:**
- Escrow-protected payments (money is held safely until the job is confirmed complete)
- NIN (National Identification Number) verified artisans
- Real-time GPS tracking during jobs
- WhatsApp-native communication (critical for Nigerian users)

---

## 2. DESIGN SYSTEM

> **CRITICAL:** Apply this design system consistently across every single screen. Do not deviate. Consistency is a core trust signal for users.

### 2.1 Colour Palette

| Colour Name | Hex Code | Usage |
|---|---|---|
| **Nexplumb Navy** | `#0D2137` | Navigation bars, page headers, admin sidebar, important headings, dark section backgrounds |
| **Nexplumb Blue** | `#2E86AB` | Clickable links, active sidebar items, verified badges, info icons, secondary accents |
| **Nexplumb Teal** | `#2A9D8F` | "Available" badges, booking confirmed states, success indicators, progress bars, focus rings |
| **Nexplumb Orange** | `#E76F51` | ALL primary CTA buttons ("Book Now", "Pay Now", "Get Started"), urgent flags, notification dots, primary actions |
| **Nexplumb Amber** | `#E9C46A` | Warning messages, pending status badges, Phase 2 labels, caution states |
| **Light Gray** | `#F2F4F6` | Page background, alternating table row colour, card section backgrounds |
| **Mid Gray** | `#D5D8DC` | Divider lines, card borders, input borders |
| **Body Text** | `#1C2833` | All standard paragraph text on the page |
| **Secondary Text** | `#717D7E` | Captions, timestamps, placeholder text, helper text |
| **White** | `#FFFFFF` | Card backgrounds, modal backgrounds, form surfaces |

**Colour Rules:**
- Orange (`#E76F51`) is ONLY used for primary action buttons and urgent indicators. Do not use it decoratively.
- Teal (`#2A9D8F`) indicates success, availability, and positive states. Also used for focus rings.
- Amber (`#E9C46A`) indicates pending/warning states. Never use it for success.
- Navy (`#0D2137`) is the dominant brand colour. It dominates all header and navigation surfaces.

### 2.2 Typography

**Font Family:** `Sora` (headings, labels, navigation) + `Lora` (body text, descriptions) + `IBM Plex Mono` (code, IDs, statistics, monospace labels)

**Type Scale:**
| Role | Font | Size | Weight |
|---|---|---|---|
| Hero H1 | Sora | 44px | 800 |
| Page H2 | Sora | 28–32px | 700 |
| Section H3 | Sora | 20–22px | 700 |
| Card Title | Sora | 16–18px | 600 |
| Body text | Lora | 15–16px | 400 |
| Labels / Nav | Sora | 12–13px | 400–600 |
| Captions | Lora | 12–13px | 400, italic |
| Monospace IDs | IBM Plex Mono | 11–13px | 400–600 |

**Rules:**
- Body text minimum: 14px. Never go smaller.
- Button labels: sentence case ("Book now", NOT "BOOK NOW")
- All money values displayed in Nigerian Naira: `₦12,000` format

### 2.3 Buttons

**Primary Button (Orange):**
- Background: `#E76F51`
- Text: White, Sora, 14–15px, weight 600
- Height: 48px
- Border radius: 8px
- Hover state: Darken background by 8% + slight translateY(-1px) shadow effect
- Disabled state: 40% opacity, no hover effects

**Secondary Button (Outlined Navy):**
- Background: Transparent
- Border: 2px solid `#0D2137`
- Text: `#0D2137`, Sora, 14px, weight 600
- Height: 48px
- Border radius: 8px
- Hover state: Fill with `#0D2137` background, text turns white

**Destructive Button (Red actions like Ban/Reject):**
- Background: `#C0392B`
- Text: White
- Same size as primary

**Ghost/Text Button:**
- No background, no border
- Text: `#2E86AB` (blue), underline on hover

### 2.4 Status Badge Colours (Pills/Chips)

| Status | Background | Text Colour |
|---|---|---|
| Active / Available / Success | `rgba(42,157,143,0.15)` | `#1A7A6E` (dark teal) |
| Pending / Warning | `rgba(233,196,106,0.2)` | `#7A5C00` |
| Urgent / Error / Disputed | `rgba(231,111,81,0.15)` | `#C0401A` |
| Verified / Trusted | `rgba(46,134,171,0.15)` | `#1E6A8A` |
| Completed | `rgba(13,33,55,0.08)` | `#0D2137` |

All status badges: `IBM Plex Mono` font, 10–11px, uppercase, `border-radius: 3px`, `padding: 3px 8px`.

### 2.5 Card Design

**Standard Card:**
- Background: White
- Border: 1px solid `#D5D8DC`
- Border radius: 8px
- Box shadow: `0 1px 3px rgba(0,0,0,0.06), 0 4px 16px rgba(0,0,0,0.04)`
- Internal padding: 24–36px

**Hover Card (interactive, e.g. artisan search card):**
- On hover: shadow deepens to `0 4px 20px rgba(0,0,0,0.1)`, border becomes teal `#2A9D8F`

### 2.6 Form Elements

- Input height: 48px
- Border: 1px solid `#D5D8DC`
- Border radius: 6px
- Focus state: Border becomes `#2A9D8F` (teal), 2px, with a subtle outer glow
- Label: Always placed ABOVE the input field, never inside as placeholder-only
- Placeholder text: Secondary text colour `#717D7E`
- Error state: Border turns `#C0392B` (red), red error message text appears below the field
- Valid state: Green checkmark icon appears inside the right side of the field

### 2.7 Responsive Breakpoints

Design **Desktop First**, then adapt for smaller sizes.

| Breakpoint | Width | Notes |
|---|---|---|
| Desktop | 1280px | Full layouts, sidebars visible, multi-column |
| Tablet | 768px | Sidebars collapse to drawers, some columns stack |
| Mobile Web | 375px | Single column, simplified navigation, bottom nav bar |

**Responsiveness Rules:**
- The Admin Dashboard (`admin.nexplumb.com`) is desktop-only. No mobile optimisation needed.
- All other portals must work at all three breakpoints.
- On mobile, sticky sidebars become a hamburger menu or bottom navigation bar.
- Minimum tap target size: 48×48px on all interactive elements.

### 2.8 Iconography

Use a consistent icon library (e.g. Lucide, Feather, or Phosphor icons). Never mix icon styles.  
Key icons to define:
- Shield (verified/escrow protection)
- Star (ratings)
- Map pin / location (artisan location)
- Wrench (artisan/trade)
- Clock (time/availability)
- Wallet / Naira sign (payments)
- Bell (notifications)
- WhatsApp logo (WhatsApp actions)

### 2.9 Spacing Scale

Use an 8px base unit system: `8 / 16 / 24 / 32 / 48 / 64 / 80px`

---

## 3. PORTAL ARCHITECTURE

The application is split into four distinct portals, each at a different subdomain:

| Portal | URL | Audience | Phase |
|---|---|---|---|
| Customer Web Portal | `nexplumb.com` | Homeowners / customers | Phase 1 |
| Artisan Web Portal | `app.nexplumb.com/artisan` | Tradespeople | Phase 1 |
| Admin Dashboard | `admin.nexplumb.com` | Nexplumb internal team | Phase 1 |
| Supplier Portal | `supplier.nexplumb.com` | Material suppliers | Phase 2 |
| Enterprise Portal | `enterprise.nexplumb.com` | B2B clients | Phase 3 |
| Finance Portal | `app.nexplumb.com/artisan/finance` | Artisans (credit) | Phase 3 |

Each portal shares the same design system but has its own navigation structure, colour emphasis, and information density.

---

## 4. PHASE 1 — CUSTOMER WEB PORTAL

**URL Base:** `nexplumb.com`  
**Audience:** Nigerian homeowners, tenants, and property managers booking artisan services.  
**Tone:** Trustworthy, modern, locally relevant, warm and accessible.

---

### CW-1 — Public Homepage / Landing Page
**URL:** `nexplumb.com`  
**Access:** Anyone — no login required

**Purpose:** This is the first thing any visitor sees. It must immediately answer: "What is this?", "Can I trust it?", "How do I get started?" It is also the most important page for Google Search (SEO). The search bar is the single most important element on the entire page.

---

#### Section 1: Global Navigation Bar (Sticky)

The navbar sticks to the top of the browser window at all times as the user scrolls.

**Desktop Layout (left to right):**
- LEFT: Nexplumb logo in navy
- CENTRE: Four text links — "How It Works", "Find an Artisan", "For Artisans", "Pricing"
- RIGHT: "Log In" text link + "Get Started" primary orange button + "Join as an Artisan" smaller secondary link

**Scroll Behaviour:**
- Before scrolling: navbar background is fully transparent (overlays the dark hero section)
- After scrolling down even 1px: navbar background becomes solid white with a subtle drop shadow `0 2px 8px rgba(0,0,0,0.08)`

**Mobile (375px):** Collapse centre links into a hamburger menu. Keep logo on left, "Get Started" button on right.

---

#### Section 2: Hero Section (Full-Width Banner)

**Container:** Full viewport width, ~560–600px tall on desktop. Background: Nexplumb Navy `#0D2137`.

**Left Side Content (60% width):**
- **H1 Headline:** Large, bold, white text. Must include the words "Lagos" and "Nigeria" for SEO. Example: `"Your trusted artisan, one tap away in Lagos"`
- **Sub-headline:** White, ~18px, ~70% opacity. Example: `"Find verified plumbers, electricians, and tradespeople near you in Lagos — instantly."`
- **Search Bar:** A large white card `border-radius: 12px`, `padding: 8px`. Inside: a full-width text input with placeholder `"What do you need? e.g. leaking pipe, electrical fault..."`, an orange "Search" button to the right, and a location selector row below. The white card pops dramatically against the dark navy background.
- **Location Selector:** Below the search input, a row with a location pin icon, text "Your location:" and an auto-detect field showing the user's area, or a text input to type manually (e.g. "Yaba", "Surulere").
- **Service Category Quick-Links:** A row of pill-shaped clickable chips below the location: `"Plumbing · Electrical · Carpentry · Painting · Tiling"`. Each chip: white background with navy text, `border-radius: 20px`, `padding: 6px 16px`. On hover: orange background, white text.

**Right Side (40% width, desktop only):**
- An illustration or high-quality image showing a Nigerian artisan at work, with a home setting. Include the Nexplumb shield/logo subtly. This makes the page feel local, not generic.

**Mobile:** Stack vertically. Hero image hidden. Search card becomes full width.

---

#### Section 3: Trust Bar (Below Hero)

**Container:** Full-width band. Background: slightly darker navy or `#091A2D`. Padding: `40px 64px`.

**Layout:** Three equal columns (stack vertically on mobile), each showing:
1. 🛡️ **"1,200+ Verified Artisans"** — Shield icon, large bold number, small label below
2. 🔒 **"Escrow-Protected Payments"** — Padlock icon, bold headline, small label
3. ⭐ **"4.8 / 5 Average Rating"** — Star icon, large bold rating, small label

Typography: Numbers in Sora 36px bold white. Labels in IBM Plex Mono 11px, 60% white opacity.

---

#### Section 4: How It Works

**Container:** White background, full width, generous padding `80px 64px`.

**Title:** Centred — `"Book a trusted artisan in 3 steps"` — Sora, 32px, Navy, bold.

**Three Step Cards (horizontal row on desktop, vertical stack on mobile):**  
Each card contains: a numbered circle (navy fill, white number, 40px diameter), a relevant icon, a bold title, and a 2-line description.

1. **Step 1 — Search:** `"Type what you need or pick a category. We'll show you verified artisans near your location."`
2. **Step 2 — Book & Pay Safely:** `"Choose your artisan, pick a time, and pay through our secure escrow. Your money is protected until the job is done."`
3. **Step 3 — Track & Confirm:** `"Watch your artisan travel to you on a live map. Confirm when the job is complete and release payment."`

**CTA Below:** Centred orange primary button: `"Find an artisan now →"`

---

#### Section 5: Featured Artisans

**Container:** Light gray background `#F2F4F6`. Padding: `64px`.

**Title:** Left-aligned — `"Top-rated artisans near you"` with the detected area in a teal label.

**Artisan Card Row:** 4 cards horizontally on desktop, horizontally scrollable on mobile. Each card:
- Circular profile photo (80px diameter)
- Full name (Sora, 15px, bold)
- Trade label (e.g. "Plumber") in a teal badge
- Star rating + review count
- Location area + "Available Now" green badge (if applicable)
- "View Profile" secondary outlined button

**Trailing Link:** `"See all artisans →"` text link after the card row.

---

#### Section 6: Category SEO Sections

**Container:** White background. Repeat this pattern for EACH major trade category.

For each trade (Plumbing, Electrical, Carpentry, Painting, Tiling):
- **H2 Heading** (for SEO): `"Plumbers in Lagos"` — Navy, Sora, 24px bold
- 3 artisan cards (same format as Featured section)
- CTA link: `"Find more plumbers near you →"` — teal text link

**Note for AI:** These H2 headings are SEO-critical. They MUST be `<h2>` elements with the trade name + "Lagos" phrasing.

---

#### Section 7: Social Proof / Reviews

**Container:** Navy background. Padding: `64px`.

**Title:** Centred white — `"What our customers say"` — Sora, 28px.

**Review Cards:** 3 cards in a row (stack on mobile). Each card — white background, rounded corners:
- Customer circular avatar (60px) + first name + their area (e.g. "Lekki")
- Star rating (5 orange stars shown as SVG, or some filled)
- 2–3 sentence review text in Lora italic
- Date of review in secondary text colour

---

#### Section 8: Footer

**Container:** Navy background `#0D2137`. Full width. 4-column grid layout.

**Column 1 — About Nexplumb:** Links: About Us, How It Works, Blog, Press  
**Column 2 — For Customers:** Links: Find an Artisan, How Escrow Works, Safety Guarantee, Pricing  
**Column 3 — For Artisans:** Links: Join as an Artisan, How to Get Verified, Artisan Resources, Training  
**Column 4 — Support:** Links: Help Centre, Contact Us, Report an Issue, FAQs

All link text: `rgba(255,255,255,0.6)`, Sora 12.5px. On hover: white.

**Below the columns:**
- Social icons row: Twitter/X, Instagram, LinkedIn, Facebook, YouTube — white icons, 24px
- Divider line
- Legal links row: `"Terms of Service · Privacy Policy · Escrow Policy"` — 11px, 40% white opacity

**WhatsApp Floating Button:**  
A fixed green WhatsApp button floating in the bottom-right corner of every customer-facing page. Circle shape, 56px diameter, WhatsApp icon white, green background `#25D366`. Drop shadow. On hover: scale up slightly. This is critically important for Nigerian users.

---

### CW-S — Customer Sign Up Page
**URL:** `nexplumb.com/register`  
**Triggered by:** Clicking "Get Started", "Book Now" when not logged in

**Purpose:** New customer account creation. Must be frictionless. Collect only essential information. Every extra field is a reason for a user to leave.

#### Layout (Desktop)

**Two-panel design:**
- **LEFT panel (40%):** Navy background. Nexplumb logo. Tagline: `"Join thousands of Lagos residents who book trusted artisans safely"`. The three trust stats below (1200+ artisans, escrow protection, 4.8 rating) with icons. This panel provides reassurance during sign-up.
- **RIGHT panel (60%):** White background. The sign-up form.

On mobile: Left panel is hidden. Show only the form, full width, with the logo at the top.

#### Form Fields (in order)

1. **Page title:** `"Create your account"` — Sora, 24px, Navy, bold
2. **First Name:** Label above: "First Name". Required. 48px tall input.
3. **Phone Number:** Label: "Phone Number". Show Nigeria flag emoji + `"+234"` as a fixed prefix in the input. This is the primary login identifier.
4. **Password:** Label: "Create a password". Show/hide toggle eye icon on the right. Minimum 8 characters. Password strength progress bar below (3 segments: Weak / Moderate / Strong, colour-coded red→amber→teal).
5. **Confirm Password:** Label: "Repeat your password". Shows a green checkmark inline when both passwords match.
6. **Terms Checkbox:** `"I agree to Nexplumb's Terms of Service and Privacy Policy"`. "Terms of Service" and "Privacy Policy" are clickable blue links. Checkbox must be ticked before form can submit.
7. **Submit Button:** Full-width orange, `"Create Account"`. Shows a loading spinner while processing.
8. **"Already have an account?"** link below the button → Login page.

#### OTP Verification Step

After submitting, the form transitions to a new view:
- Title: `"Verify your phone number"`
- Subtext: `"We sent a 6-digit code to +234 XXX XXX XXXX"`
- 6 individual digit input boxes (auto-advance to next box on entry, auto-read on Android)
- `"Resend code"` link (greyed out for 60 seconds, then becomes active with a countdown timer)
- Back link: `"← Change phone number"`

---

### CW-L — Customer Login Page
**URL:** `nexplumb.com/login`

**Purpose:** Fast re-entry for returning customers. Goal: a returning user should be back in their account within 10 seconds.

**Layout:** Same two-panel as Sign Up (Left: Navy brand panel; Right: White form).

#### Form Fields

1. **Page title:** `"Welcome back"` — Sora, 24px, Navy
2. **Phone Number:** `"+234"` prefix, same format as Sign Up
3. **Password:** With show/hide toggle
4. **"Forgot password?" link:** Right-aligned, above the submit button. Starts reset flow: enter phone → OTP → set new password.
5. **Submit:** Full-width orange `"Log In"` button
6. **Error Banner:** If credentials fail, a red banner below the button: `"Incorrect phone number or password. Please try again."` Never specify which field is wrong.
7. **"Don't have an account?" link** below button → Sign Up page.

---

### CW-2 — Search Results Page
**URL:** `nexplumb.com/search?q=plumber&location=yaba&sort=rating`

**Purpose:** The customer has searched. Show them all matching artisans with tools to narrow their choice. Balance information density with clarity.

#### Desktop Layout — Two-Column Split

**Left Column — Filter Sidebar (280px fixed width):**

- `"Clear all filters"` link at top (Resets all, re-runs search)
- **Applied Filters Chips:** Active filters shown as dismissible small tags with × buttons (e.g. `"Rating: 4+ ×"`)
- **Trade Category:** Checkboxes for: Plumbing, Electrical, Carpentry, Painting, Tiling. Checking/unchecking instantly updates results.
- **Minimum Rating:** Star-based radio buttons: `"3★ and above" / "4★ and above" / "5★ only"`
- **Availability:** Radio buttons: `"Available Now" / "Available Today" / "Any Time"`
- **Distance Slider:** Draggable slider, 1km–20km. Label: `"Show artisans within [X] km of me"`
- **Price Range:** Dual-handle slider, ₦0–₦50,000+. Live Naira labels on the handles.
- **Verified Only:** On/Off toggle. When on, shows only NIN-verified artisans.
- **Certification Level:** Radio: `"Any" / "Nexplumb Certified" / "Trade Tested"`

On tablet (768px): Sidebar collapses. A `"Filters"` button at the top of the results area opens it as a full-screen drawer/modal.

**Right Column — Results Area (fills remaining width):**

**Results Header Bar:**
- Left: Count text e.g. `"Showing 24 plumbers in Yaba and nearby areas"`
- Right: Sort dropdown (`"Best match / Highest rated / Nearest to me / Most jobs / Lowest price"`) + List/Map toggle (two icon buttons)

**Artisan Card (Horizontal, List View):**  
Each artisan is a wide horizontal card. Layout left-to-right:
- **Profile photo:** 80×80px circle, left side
- **Centre content:**
  - Name (Sora, 16px, bold, navy)
  - Trade badge (teal pill)
  - Star rating (filled stars) + `"(47 reviews)"` in secondary text
  - Location text + `"Available Now"` green badge (if applicable)
  - 2-line bio text (Lora, 13.5px)
  - Skill chips row: small light-gray pills e.g. `"Burst pipes"`, `"Tap replacement"`, `"Drain unblocking"`
  - Inline trust badges: `"ID Verified"` (blue shield) + `"Nexplumb Certified"` (teal star)
- **Right side:**
  - Price range in large text: `"₦8,000 – ₦15,000"`
  - `"per job"` label in secondary text
  - `"View Profile"` secondary outlined button
  - `"Book Now"` primary orange button

Hover state: Card border becomes teal, shadow deepens.

**Pagination:** 24 cards per page. Numbered page buttons below, or a `"Load more"` button.

#### Map View (toggle from List icon)

Layout switches to 50/50 split:
- **Left half:** Scrollable artisan list (simplified cards, narrower)
- **Right half:** Full-height interactive map (Google Maps)
  - Orange animated pins with artisan photo thumbnail for available artisans
  - Gray semi-transparent pins for busy artisans
  - Blue `"You"` pin for the customer's location
  - Hovering a list card highlights the corresponding map pin (grows + changes colour)
  - Clicking a map pin opens a mini-card popup: photo, name, rating, trade, price, `"View Profile"` button
  - `"Search this area"` button appears when user pans/drags the map
  - Available artisan pins have a subtle 2-second pulse animation

**Mobile (375px):** Single column. Filter sidebar becomes a sheet. Map view shows full-screen map with a draggable bottom sheet listing artisans.

---

### CW-3 — Artisan Public Profile Page
**URL:** `nexplumb.com/artisans/[artisan-slug]`  
**SEO Note:** This page is indexed by Google. The artisan's name and trade + "Lagos" must appear in the `<title>` tag and `<h1>`.

**Purpose:** The decision page. After browsing search results, the customer clicks on one artisan. This page must convince them to book. Think of it as each artisan's personal store page.

#### Desktop Layout — Two Columns (700px content + 400px sticky sidebar)

**Left Column (Main Content):**

1. **Hero Banner Image:** Full-width image at top (~280px tall) showing artisan's best job photo. Circular profile photo (100px) overlaid on the bottom-left corner of this banner with a white ring border.

2. **Name & Identity Row:** `"Chukwuemeka Okonkwo"` — Sora, 26px, bold, navy. Below: `"Plumber · Surulere, Lagos"` in secondary text.

3. **Trust Badges Row:** A horizontal row of coloured badge icons with labels:
   - 🛡️ `"ID Verified"` (blue)
   - ⭐ `"Nexplumb Certified"` (teal)
   - ✅ `"Guarantor Verified"` (green)
   - 🎀 `"Trade Tested"` (orange)
   Each badge has a tooltip on hover explaining what it means.

4. **Stats Row:** 4 numbers side by side in a light-gray row:
   - `"4.8 ★"` — Average rating
   - `"47 reviews"`
   - `"134 jobs completed"`
   - `"Member since Jan 2024"`

5. **About Section:** Artisan's written biography. 2–4 paragraphs in Lora body text. Section title: `"About"` in Sora caps.

6. **Skills & Services:** Row of pill chip tags: e.g. `"Burst pipes"`, `"Bathroom installation"`, `"Drain inspection"`, `"Boiler repair"`, `"Tap replacement"`. Light gray background pills.

7. **Portfolio Grid:** 3-column masonry photo grid (Pinterest-style). Clicking any photo opens a full-screen lightbox. Include a `"Before"` / `"After"` label chip on relevant photos.

8. **Service Area Map:** Small embedded map (~300px tall) with the artisan's coverage zone highlighted in teal. A label below: `"Serves: Surulere, Yaba, Mushin, Agege"`.

9. **Reviews Section:**
   - Rating summary bar chart: 5 horizontal bars showing count of 1–5 star reviews
   - Individual review cards: customer name + area + date + stars + review text
   - `"Artisan's response:"` indented reply block (if artisan replied)
   - `"See all 47 reviews"` expandable link

**Right Column (Sticky Booking Widget, 400px):**  
This panel stays fixed as the user scrolls the left column.

1. **Price Range:** `"₦8,000 – ₦15,000"` — Sora, 28px, bold, navy. Label below: `"Estimated per job"` in secondary text.

2. **Availability Badge:** `"● Available Now"` in teal (green dot) OR `"Available from [date]"` in amber.

3. **Primary CTA:** Full-width orange button — `"Book This Artisan"`. This is the most important button on the page. If not logged in, clicking shows a login/register modal.

4. **Quote Link:** Text link below button — `"Request a quote instead →"`

5. **Utility Buttons Row:**
   - Heart icon `"Save"` — saves to customer's favourites (requires login)
   - Share icon with dropdown: `"Copy link"` + `"Share via WhatsApp"`

6. **Escrow Trust Message:** Shield icon + `"Your payment is protected by Nexplumb Escrow"` — teal small text.

7. **Messaging Note:** `"Message Artisan"` button — greyed out before booking with a tooltip: `"Available after booking is confirmed"`.

**Mobile (375px):** Left column becomes full width. Booking widget becomes a fixed bottom bar with price on left and `"Book Now"` button on right (sticky bar, 64px tall).

---

### CW-4 — Web Booking Flow (Steps A–D)
**URL:** `nexplumb.com/book/[artisan-slug]`

**Purpose:** Take the customer from "I want to book this artisan" to "My booking is confirmed and paid". Four clear steps. The customer always knows which step they're on and how many remain.

#### Step Progress Indicator (appears on all steps A–C)

A horizontal stepper at the top:  
`"1. Job Details → 2. Schedule → 3. Review & Pay → 4. Confirmed"`  
- Current step: Teal filled circle + teal text
- Completed steps: Navy filled circle with white checkmark + navy text
- Upcoming steps: Light gray circle + gray text

---

#### CW-4A — Job Details (Step 1)

**Layout:** Left panel (persistent artisan summary — shows artisan photo, name, trade, rating) + Right form area.

**Form elements:**
1. **Job Type Selector:** Dropdown with common job types: `"Pipe repair / Drain unblocking / Full bathroom installation / Tap replacement / Other (describe below)"`. Selecting pre-fills the description below.
2. **Job Description:** Multi-line textarea. Minimum 30 characters required. Live character counter: `"47 / 30 minimum"`. Placeholder: `"Describe the problem in your own words..."`
3. **Photo Upload Zone:** Drag-and-drop zone, dashed border, camera icon, `"Drag photos here or click to upload"`. Up to 5 photos. Uploaded thumbnails show in a row with × remove buttons.
4. **Urgency Toggle:** Toggle switch labelled `"This is urgent (30% premium applies)"`. When switched on, a yellow info box appears: `"Urgent bookings attract artisans faster but add 30% to the final total."`
5. **Address Field:** Searchable with Google Places autocomplete. As customer types, dropdown suggestions appear. A small map preview below the field shows the selected location pinned.
6. **`"Continue"` button:** Full-width orange. Disabled until required fields are filled.

---

#### CW-4B — Schedule (Step 2)

1. **`"Flexible"` Shortcut (above the calendar):** A prominent highlighted option in a teal-bordered card: `"Flexible — any time today or tomorrow"`. Selecting this skips the calendar and gets faster matching.

2. **Full Monthly Calendar:** Display a complete month grid (like a wall calendar). Available dates: teal background. Past dates and fully-booked dates: gray background, not clickable. Selected date: navy filled circle.

3. **Time Slot Grid (appears after selecting a date):** Button grid of available time slots. E.g. `"8:00 AM · 9:00 AM · 10:00 AM · 1:00 PM · 3:00 PM"`. Unavailable slots: gray with `"Booked"` label.

4. **Duration Note:** Below the slots: `"Pipe repair jobs typically take 1–2 hours."`

5. **`"Back"` + `"Continue"` buttons**

---

#### CW-4C — Review & Pay (Step 3)

1. **Job Summary Box (read-only):** Light gray card showing everything entered: artisan name, job description, address, date, time. A `"← Edit"` link on each row lets them go back to correct.

2. **Price Breakdown Table:**
   ```
   Service estimate:      ₦10,000
   Platform booking fee:  ₦500
   Materials:             ₦0
   Urgent premium:        ₦3,000
   ─────────────────────────────
   Total:                 ₦13,500
   ```
   Every line item labelled. NO hidden fees.

3. **Escrow Explanation Banner:** Full-width teal-bordered card with a large shield icon: `"Your payment is held safely by Nexplumb and only released to the artisan after you confirm the job is done. Full refund if the artisan does not show up."`

4. **Payment Method Tabs:** 4 tabs — `"Debit Card" / "Bank Transfer" / "USSD Code" / "Wallet Balance"`

   - **Debit Card tab:** Inline Paystack form (card number, expiry, CVV). No redirect. Fully embedded.
   - **Bank Transfer tab:** Shows a Nexplumb escrow account number + unique reference code. Live status: `"Waiting for payment..."` → `"✓ Payment received!"` auto-updates.
   - **USSD tab:** Step-by-step dial code instructions per bank (GT Bank, Access, Zenith, etc.)
   - **Wallet tab:** Shows balance `"₦20,000"` with `"Use ₦13,500 from wallet"` confirm button.

5. **Submit Button:** Full-width orange — `"Confirm & Pay ₦13,500"`. The amount is in the button text. Below the button: padlock icon + `"Secured by Nexplumb Escrow and Paystack"`

---

#### CW-4D — Booking Confirmed (Step 4)

Full-page success state:

1. **Large Animated Teal Checkmark:** SVG path-draw animation. Below it: `"Booking Confirmed!"` — Sora 32px bold navy.

2. **Booking Reference Number:** `"NX-2024-00847"` in IBM Plex Mono, 24px, navy. `"Copy"` button beside it (copies to clipboard with a `"Copied!"` tooltip).

3. **Summary Card:** Artisan photo + name + job type + date + time.

4. **Action Buttons:**
   - `"Track Your Artisan"` — primary orange (→ CW-5 Live Tracking)
   - `"Add to Google Calendar"` — secondary outlined button
   - `"Share via WhatsApp"` — green WhatsApp-styled button with pre-written message
   - `"View your bookings"` — text link

---

### CW-5 — Live Job Tracking Page
**URL:** `nexplumb.com/jobs/[job-id]/track`

**Purpose:** The "Bolt/Uber moment" — the customer watches their artisan travel to them in real time. This is one of the biggest trust and delight features of the platform. The customer must always feel informed and in control.

#### Desktop Layout — Full-Width Split

**Left Panel (420px) — Job & Status Information:**

1. **Job Status Progress Bar (Horizontal Stepper):**  
   `"Confirmed → En Route → On Site → Job Complete"`
   - Current status: Teal filled circle
   - Completed stages: Navy circle with checkmark

2. **Current Status Message (Large Text):** Dynamic message based on status:
   - `"Chukwuemeka is on his way — estimated arrival 12 minutes"`
   - `"Chukwuemeka has arrived at your location"`
   - `"Job is in progress"`

3. **ETA Countdown:** `"~12 min"` in Sora 48px bold teal. Updates every 10–15 seconds. `"2.3 km away"` below.

4. **Artisan Strip:** Profile photo (80px circle) + full name + trade + star rating.

5. **Contact Buttons:**
   - `"📞 Call Artisan"` (masked number — real phone numbers never exposed)
   - `"💬 Send Message"` (in-app chat)

6. **Job Details Accordion:** Collapsible. Shows job description, address, booking reference. Collapsed by default.

7. **`"Report an issue"` button:** Always visible at bottom. Opens a modal for reporting problems.

**Right Panel — Live Map (60% width):**

- Full-height embedded Google Map
- **Blue `"Your location"` pin:** House icon, `"Your location"` label
- **Orange artisan pin:** Contains the artisan's photo thumbnail. This pin moves smoothly across the map every 10–15 seconds using CSS transitions.
- **Route line:** Dashed orange line connecting artisan pin to customer pin. Updates as artisan moves. Disappears on arrival.
- **ETA label on route:** Small label mid-route `"~12 min"` — updates as artisan moves.
- Map auto-centres to keep both pins visible at all times.
- `"Open in Google Maps →"` link at bottom.

**GPS Signal Lost State:** If artisan loses signal, show banner: `"Artisan location temporarily unavailable — last seen 3 min ago"`. Call button highlighted as primary fallback.

#### Status Transitions Table

| Artisan Action | Customer Sees |
|---|---|
| Artisan presses "On My Way" | Status → "En Route". Map activates. Route line appears. ETA countdown begins. |
| Artisan presses "I've Arrived" | Status → "On Site". Route line disappears. Message: "Artisan is at your location." |
| Artisan presses "Job Started" | Status → "In Progress". Job timer counts up. |
| Artisan presses "Job Complete" | Full-page prompt to confirm job completion and release payment. |

**Mobile (375px):** Map is full screen (top 60% of viewport). Status panel is a draggable bottom sheet (slides up to reveal full details).

---

### CW-6 — Customer Dashboard
**URL:** `app.nexplumb.com/dashboard`

**Purpose:** The logged-in customer's personal hub. All account activity accessible from one place.

#### Layout (Desktop)

**Left Sidebar (240px, fixed):**
- Nexplumb logo
- Customer avatar + name + `"View profile"` link
- Navigation links (with icons):
  - `"Overview"` (home icon)
  - `"My Bookings"` (calendar icon) — with a badge count for active bookings
  - `"Saved Artisans"` (heart icon)
  - `"Payments"` (wallet icon)
  - `"Messages"` (chat icon)
  - `"Settings"` (gear icon)
  - `"Get Help"` (question mark icon)
- Bottom: `"Find an artisan"` orange CTA button

**Main Content Area:**

**Overview Tab (Default):**

1. **Active Booking Card (if exists):** The TOP, most prominent element. Full-width card with navy left border. Shows artisan photo, job type, current status badge, time/date. Large orange `"Track Now"` button.

2. **Upcoming Bookings Timeline:** Next 3 confirmed bookings shown as timeline rows (date marker on left, details on right).

3. **Recent Activity Feed:** Last 5 events. Each: icon + description + timestamp. E.g.: `"💳 Payment of ₦12,000 received"`, `"⭐ Emeka replied to your review"`.

4. **Quick Stats Row:** 4 metric cards in a row:
   - `"Total Jobs: 7"`
   - `"Avg Rating Given: 4.3 ★"`
   - `"Total Spent: ₦84,500"`
   - `"Loyalty Points: 350 NexPoints"`

**My Bookings Tab:**

- Filter tabs: `"All · Active · Upcoming · Completed · Cancelled · Disputed"`
- Each booking card: job type + artisan name/photo + date + status badge + amount
- Action buttons per booking: `"View details"` / `"Download receipt"` (PDF) / `"Leave review"` (if completed and not yet reviewed) / `"Book again"` (pre-fills booking form) / `"Report issue"`

---

## 5. PHASE 1 — ARTISAN WEB PORTAL

**URL Base:** `app.nexplumb.com/artisan`  
**Audience:** Plumbers, electricians, carpenters, painters, and other tradespeople managing their Nexplumb business.  
**Tone:** Professional, empowering, business-focused. The artisan is a small business owner — treat them like one.

---

### AW-1 — Artisan Registration (Web)
**URL:** `nexplumb.com/join-as-artisan`

**Purpose:** A tradesperson signs up to offer services on Nexplumb. The web version is preferred over mobile for this task because: drag-and-drop photo uploads are easier from a laptop; bank/BVN entry feels safer on a desktop; and larger text areas encourage more complete profiles.

#### 4-Step Registration Wizard

Step indicator at the top showing 4 steps (same stepper design as booking flow).

**Step 1 — Personal Information:**
- Full legal name
- Phone number (primary login, `"+234"` prefix)
- Email address (optional)
- NIN (National Identification Number) — with an info tooltip: `"Your NIN verifies your identity. It is encrypted and never shared publicly."`
- Current area/LGA in Lagos (dropdown of all Lagos LGAs)
- Trade category (dropdown: Plumbing, Electrical, Carpentry, Painting, Tiling, Other)
- Years of experience (dropdown: Less than 1 / 1–3 / 3–5 / 5–10 / 10+ years)

**Step 2 — Profile Photo:**
- Large drag-and-drop zone (200×200px minimum). Camera icon in centre. Text: `"Drag your photo here or click to upload"`
- `"Use webcam"` button: opens browser webcam with a circular guide overlay so artisan can take a professional headshot
- Instant preview after upload
- Crop tool with circular mask for the final profile photo

**Step 3 — Portfolio Photos:**
- Multi-photo drag-and-drop grid
- Each uploaded photo has: a caption text field below (`"e.g. Bathroom installation, Ikeja 2023"`), a `"Before / After"` toggle label
- Minimum 3 photos encouraged. A completeness bar shows progress: `"3/5 photos added"`

**Step 4 — Account & Verification Details:**
- Bank name (dropdown of all Nigerian banks)
- Bank account number
- BVN (Bank Verification Number)
- Guarantor 1: Full name + phone number + relationship
- Guarantor 2: Full name + phone number + relationship
- Explanation text: `"Guarantors vouch for you. They will only be contacted in case of serious disputes. Their details are kept private."`

**Review Screen (Before Submission):**
- Full preview of the public profile (exactly as customers will see it)
- Note at top: `"This is what your profile will look like to customers"`
- `"Go back and edit"` link + large orange `"Submit Profile"` button
- Post-submission message: `"We'll verify your details within 24 hours. You'll receive an SMS when your profile goes live."`

---

### AW-2 — Artisan Dashboard (Web)
**URL:** `app.nexplumb.com/artisan/dashboard`

**Purpose:** The artisan's "business command centre". Where they review performance, manage their profile, check earnings, and plan growth.

#### Layout (Desktop)

**Left Sidebar (240px, fixed, navy background):**
- Nexplumb logo (white version)
- Artisan avatar + name + trade badge + verification status (e.g. `"✓ Verified"` in teal)
- Navigation links with icons (white text, teal left border on active):
  - Dashboard Overview
  - My Jobs
  - Earnings & Payouts
  - My Profile
  - Training & Certification
  - Materials *(Phase 2 label)*
  - Reviews
  - Settings
- Bottom: `"Availability"` toggle — a clear on/off switch for whether the artisan is currently accepting jobs

**Dashboard Overview — 5 Metric Cards (top row):**

| Card | What It Shows | Extra Detail |
|---|---|---|
| Today's Earnings | `₦X` earned today | Mini sparkline chart of last 7 days |
| Active Jobs | Count of active jobs | `"View"` link to filtered Jobs tab |
| Profile Views | Views this week | Trend arrow (↑ or ↓ vs last week) |
| Rating | Current average star rating | Total review count + `"Read reviews"` |
| Completion Rate | % of accepted jobs completed | Benchmark: `"Platform avg: 92%"` |

Below the metric cards: A jobs-incoming section + upcoming schedule for the day.

---

### AW-3 — My Jobs Tab
**URL:** `app.nexplumb.com/artisan/jobs`

**Purpose:** The artisan sees all their jobs — active, upcoming, and historical.

**Layout:**
- Filter tabs: `"Active · Upcoming · Completed · Cancelled · All"`
- Search bar: search by job type, date range, or reference number
- **Job Row:** Job type icon + customer area (NOT name — privacy) + date + escrow amount + status badge + duration
- Clicking a job row: opens full job detail view with timeline, customer area, artisan notes, before/after photos, and a downloadable receipt/invoice PDF
- `"Export CSV"` button for external accounting records

---

### AW-4 — Earnings & Payouts Tab
**URL:** `app.nexplumb.com/artisan/earnings`

**Purpose:** Clear view of earned income, pending escrow amounts, and how to withdraw to their bank account.

**Components:**

1. **Balance Widget (top, prominent 3-column card):**
   - `"Available: ₦24,500"` — money ready to withdraw (teal label)
   - `"Pending: ₦8,000"` — in escrow, awaiting job confirmation (amber label)
   - `"Total Earned: ₦312,000"` — all-time lifetime total (navy label)

2. **`"Withdraw to Bank"` button:** Large orange. Opens a modal: shows verified bank account details, input for amount, `"Confirm withdrawal"` button. SMS confirmation sent on success.

3. **Earnings Bar Chart:** Daily bars for the last 30 days. Hover tooltip: `"Wednesday, 14 Feb: ₦5,200"`. Chart height: ~200px.

4. **Date Filter Dropdown:** `"This week / This month / Last 3 months / Custom range"`

5. **Transaction Table Columns:** Date · Job ID · Customer area · Trade category · Amount · Commission deducted · Net received · Status

6. **`"Download CSV"` button:** Exports transaction history.

---

### AW-5 — Profile Editor Tab
**URL:** `app.nexplumb.com/artisan/profile`

**Purpose:** Artisans update their public-facing profile. Changes update what customers see in real time.

**Layout:** Two-panel side-by-side:
- **Left panel (editor):** Form fields for editing
- **Right panel (live preview):** Updates in real time as the artisan edits. `"Preview as customer"` toggle shows the exact public view.

**Editor Components:**
- **Profile Completeness Bar:** Progress bar (e.g. `"75% complete"`) with a list of missing items: `"Add a portfolio photo to reach 90%"`
- **Bio:** Multi-line text area (Sora label: "About you")
- **Skills Tags:** Add/remove chip tags with autocomplete suggestions
- **Service Area Map:** An interactive map where the artisan draws their coverage zone. They can drag handles to define the boundary. A label below shows the named areas covered.
- **Availability Schedule:** A weekly timetable grid (Mon–Sun). For each day: an on/off toggle + time range selector (e.g. `"9:00 AM – 5:00 PM"`).
- **Portfolio Manager:** Drag-and-drop grid. Upload, remove, reorder, and caption photos. Before/After label toggle.
- **`"Save changes"` button:** Shows loading state → green `"Profile updated ✓"` toast notification.

---

### AW-6 — Reviews Tab
**URL:** `app.nexplumb.com/artisan/reviews`

**Purpose:** Read all customer reviews and reply to them. Responding to reviews — especially negative ones — shows professionalism.

**Components:**
- **Rating Summary:** Large overall score `"4.8 ★"` + total count + 5-bar distribution chart (5★ to 1★)
- **Review List:** Each review: customer name + area + date + star rating + review text
- **`"Add a reply"` button per review:** Opens a text area for the artisan to type a public response. Submitted replies appear indented below the review on the public profile, attributed as `"Artisan's response"`.
- **`"Flag for review"` button:** Cannot delete reviews. Flags are sent to admin for review. Opens a form asking for the reason.

---

## 6. PHASE 1 — ADMIN DASHBOARD

**URL Base:** `admin.nexplumb.com`  
**Audience:** Nexplumb internal operations team.  
**Critical Note:** Desktop-only. No mobile optimisation needed. Prioritise information density, speed, and clarity.

---

### AD-1 — Admin Overview Page
**URL:** `admin.nexplumb.com/overview`

**Purpose:** The team's daily starting point. See the entire platform's health at a glance — what is happening right now, what needs urgent attention.

**Layout (Desktop):**

**Top Metric Strip — 5 cards in a row:**
- `"Jobs active right now"` — with trend vs yesterday
- `"Jobs completed today"`
- `"New users today"` (customers + artisans combined)
- `"Revenue today (₦)"`
- `"Open disputes"` — card turns **amber** if >5 disputes, **red** if >10. This is a critical visual urgency signal.

Each card: large bold number + trend indicator arrow (green ↑ or red ↓).

**Main Content — Two Columns:**

**Left Column (60%):**
1. **Live Jobs Map:** Full embedded map of Lagos showing ALL active jobs as colour-coded pins: Pending = amber, En Route = blue, On Site = teal. Clicking a pin shows: Job ID, customer area, artisan name, trade, elapsed time.
2. **Active Jobs Table (below map):** Real-time table. Columns: Job ID · Customer (masked phone) · Artisan name · Trade · Area/LGA · Status · Time Since Booking.

**Right Column (40%):**
1. **Dispute Queue:** Open disputes sorted by urgency (oldest + highest-value first). Top item fully expanded. Each: dispute ID, customer vs artisan, amount, reason, time open (with SLA colour-coded timer: green < 24h, amber 24–48h, red > 48h).
2. **Verification Queue:** New artisan applications count + `"Review now"` link.
3. **Flagged Users:** Count + `"Review"` link.

---

### AD-2 — Jobs Management Table
**URL:** `admin.nexplumb.com/jobs`

**Purpose:** See every job in the system — past and present. Take action on any of them.

**Main Jobs Table Columns:**

| Column | Content | Sortable |
|---|---|---|
| Job ID | Unique reference. Clickable → full job detail. | No |
| Customer | First name + masked phone. Click → customer profile. | Yes |
| Artisan | Name + trade + rating. Click → artisan profile. | Yes |
| Service | Trade category | Yes |
| Location | Area / LGA | Yes |
| Status | Colour-coded badge: Pending (amber) / Active (blue) / Complete (teal) / Disputed (red) | Yes |
| Amount | Escrow amount in ₦ | Yes |
| Booked At | Date + time | Yes |
| Last Update | Timestamp of most recent status change | Yes |
| Actions | Buttons: View · Flag · Resolve · Force Refund · Message both parties | No |

**Filter Panel (collapsible left sidebar):**
- Date range picker
- Status (multi-select)
- Trade category
- Area/LGA
- Artisan name search
- Customer name search
- Amount range
- `"Flagged jobs only"` toggle

Pre-built saved filter presets: `"Today's disputes"`, `"Unreviewed artisans"`, `"High-value jobs (>₦50,000)"`

`"Export CSV"` button always visible at top.

---

### AD-3 — Dispute Resolution Centre
**URL:** `admin.nexplumb.com/disputes`

**Purpose:** Investigate and resolve disputes between customers and artisans. Target: resolve every dispute within 48 hours.

**Dispute List View:**
- Sorted by time open (oldest first)
- SLA Timer per dispute: green < 24h, amber 24–48h, red > 48h
- High-value flag: `"High Value"` indicator for disputes > ₦20,000
- Columns: Dispute ID · Customer · Artisan · Amount · Reason · Time Open · Status

**Dispute Detail View (click any row — 3-panel layout):**

1. **LEFT PANEL — Full Timeline:** Chronological event log. E.g.: `"Job booked — Feb 14, 2:30pm"` → `"Artisan arrived — Feb 14, 4:15pm"` → `"Customer filed dispute — Feb 14, 7:00pm"`

2. **CENTRE PANEL — Evidence Side-by-Side:** 
   - Left: Customer's written statement + their uploaded evidence photos
   - Right: Artisan's written statement + their uploaded evidence photos
   Both visible simultaneously for easy comparison.

3. **RIGHT PANEL — Transaction Record:** Total escrow, payment method, job photos (before/after from artisan), full chat history.

**Decision Panel (Bottom of page — 3 resolution buttons):**
- **`"Release to Artisan"` (green button):** Escrow released to artisan. Mandatory note field required. Both parties notified by SMS + in-app.
- **`"Refund to Customer"` (orange button):** Escrow returned to customer. Mandatory note required. Both notified.
- **`"Partial Resolution"` (gray button):** Split amount. Input fields for each party's amount. Both notified.

**Audit trail:** Every decision is permanently logged with admin name, timestamp, and note. Cannot be reversed without a manager override.

---

### AD-4 — Artisan Verification Queue
**URL:** `admin.nexplumb.com/verification`

**Purpose:** Manually review and approve/reject every artisan application. Target: review within 24 hours of submission.

**Queue List:**
- Sorted by submission time (oldest first)
- Columns: Artisan name · Trade · Location · NIN Status (auto-verified ✓ or `"Manual review needed"`) · BVN Status · Profile photo quality · Time waiting · Actions

**Application Detail View (click any row):**
1. **Profile Preview Panel:** How the artisan's profile will look to customers if approved. The reviewer sees exactly what customers will see.
2. **Document Panel:** NIN card photo, profile headshot, portfolio photos, guarantor details.
3. **NIMC Verification Result:** Inline API result: `"Identity verified: Chukwuemeka John Okonkwo, Male, DOB: 1989-05-14"` OR `"Verification failed — check NIN number."`

**Three Action Buttons:**
- **`"Approve"` (green):** Profile goes live immediately. SMS sent: `"Congratulations! Your Nexplumb profile is live."`
- **`"Request More Info"` (amber):** Opens a message template for requesting better photos, clearer NIN, etc.
- **`"Reject"` (red):** Mandatory rejection reason required before confirming. Artisan notified with specific reason.

---

### AD-5 — Analytics & Reporting
**URL:** `admin.nexplumb.com/analytics`

**Purpose:** Business intelligence for weekly/monthly reviews and investor reporting.

**Report Sections:**

1. **Platform Overview:** Line charts for Total jobs, Revenue, New users, Active artisans. Filter: day/week/month.

2. **Geographic Heat Map:** Map of Lagos where each LGA is colour-coded by job density. Dark teal = high volume, light = low. Shows where Nexplumb is strong and where more artisan supply is needed.

3. **Artisan Quality:** Rating distribution chart · Completion rate by trade · No-show rate by trade and area.

4. **Customer Behaviour:** Repeat booking rate (% who book more than once) · Review submission rate · Avg job value trend.

5. **Revenue Breakdown:** Stacked bar chart — Commission income · Platform fees · Subscription revenue · Materials GMV.

6. **Conversion Funnel:** Funnel chart: Search → Profile view → Booking initiated → Payment completed. Drop-off percentage shown at each step. Identifies where users abandon the booking process.

Every section: `"Export CSV"` and `"Download PDF"` buttons.

---

### AD-6 — User Management
**URL:** `admin.nexplumb.com/users`

**Purpose:** Look up any customer or artisan account, view their history, take account actions.

**Features:**
- Search by name, phone number, or user ID across all accounts
- User type filter tabs: `"Customers"` and `"Artisans"`
- Clicking a user: opens full account page — all jobs, payments, reviews, account status

**Account Actions (all require a mandatory reason note):**
- `"Flag account"` — adds monitoring flag
- `"Suspend account"` — temporary access removal
- `"Ban account"` — permanent removal
- `"Send message"` — platform notification to user
- `"Download data"` — NDPA compliance — exports all data held on that user

All actions permanently logged in audit trail with admin name + timestamp.

---

## 7. PHASE 2 — SUPPLIER PORTAL

**URL Base:** `supplier.nexplumb.com`  
**Audience:** Nigerian material suppliers and importers (e.g. companies selling pipes, fittings, bathroom fixtures, electrical supplies).  
**Tone:** Professional, B2B-appropriate. This is a business product.

---

### SP-1 — Supplier Registration & Verification
**URL:** `supplier.nexplumb.com/register`

**Note:** Verification bar is higher than for individual artisans. CAC (Corporate Affairs Commission) business registration is required.

**Registration Fields:**
- Business Name (official registered company name)
- CAC Registration Number (validates legitimacy)
- Business Address
- Warehouse Address (may differ from office)
- Primary Contact: Full name + phone + business email
- Product Categories (multi-select): `"Pipes & Fittings · Electrical Cables & Components · Bathroom Fittings · Power Tools · Building Materials · Other"`
- Business Bank Account: Bank name + account number + account name
- CAC Certificate Upload (PDF or image, with preview)
- 3 initial product photos (drag-and-drop)
- Submit: `"Submit for review"`. Admin reviews within 48 hours. Supplier notified by email + phone on approval.

---

### SP-2 — Supplier Dashboard
**URL:** `supplier.nexplumb.com/dashboard`

**Sidebar Navigation:** Dashboard · Products · Orders · Artisan Requests · Earnings · Reviews · Settings

**Dashboard Metrics:**
- Orders received today (with trend)
- Pending orders to fulfil (urgency signal if backlog builds)
- Revenue this month (gross and net after commission)
- Active product listings count
- Average product rating from artisan reviews

---

### SP-3 — Products Catalogue Management
**URL:** `supplier.nexplumb.com/products`

**Products Table Columns:** Thumbnail · Name · Category · Price (₦) · Stock count · Status (Active/Inactive toggle) · Views this week · Orders this week

**`"Add Product"` button (opens form):**
- Product name + Category + Brand + Detailed description + Price in ₦ + Stock count + Estimated delivery time + Up to 8 photos (drag-and-drop)

**Additional Features:**
- `"Import from CSV"` button for bulk catalogue upload
- `"Request Nexplumb Verified badge"` per product — submits for quality review. If approved, `"NX Verified"` badge appears on the listing.

---

### SP-4 — Orders Management
**URL:** `supplier.nexplumb.com/orders`

**Order Table Columns:** Order ID · Artisan name · Product(s) · Quantity · Total amount · Delivery address · Order time · Status

**Status Lifecycle:** `"New → Confirmed → Packing → Shipped → Delivered"`

**Actions per order:** `"Confirm order"` · `"Mark as shipped"` (prompts for tracking number) · `"View artisan details"` (area only — no personal contact info)

**Bulk Update:** Checkbox selection across multiple orders → batch status update.

---

## 8. PHASE 2 — ENHANCED FEATURES

---

### CW-E1 — Price Estimator Tool
**URL:** `nexplumb.com/price-estimator`

**Purpose:** Free tool that helps customers understand job costs before booking. Also a major SEO landing page — `"how much does a plumber cost in Lagos"` is a high-traffic search query.

**Components:**

1. **Job Type Selector:** Dropdown — `"Burst pipe / Drain unblocking / Full bathroom fit / Tap replacement / Electrical wiring / ..."`

2. **Location Selector:** Area within Lagos (dropdown or search).

3. **Complexity Selector:** 3 radio buttons — `"Simple · Standard · Complex"` with examples for each.

4. **Result Display (after selections):**
   - Horizontal gradient bar with 3 price markers: `"Budget: ₦5,000 · Typical: ₦12,000 · Premium: ₦22,000"`
   - The user's estimated range highlighted on the bar

5. **CTA:** Orange button `"Find artisans in this price range →"` — links to filtered search results.

6. **SEO Content Section (below the tool):** A 400-word editorial article: `"How much does a plumber cost in Lagos?"` This text is why Google sends traffic to this page.

---

### CW-E2 — Emergency Booking Page
**URL:** `nexplumb.com/emergency`

**Purpose:** The fastest possible path to a confirmed booking for urgent situations. Every second counts. Strip out all non-essentials.

**Design:**
- Full-page urgent red/orange banner at top: `"EMERGENCY BOOKING — Available 24 hours a day, 7 days a week"`
- No standard navbar clutter. Streamlined, focused layout.
- Large emergency phone number prominent: `"Rather call? 0800-NEXPLUMB"`

**Simplified Form (just 2 fields):**
1. `"What is the emergency?"` — dropdown: `"Burst pipe / No power / Flooding / Gas leak / Locked out"`
2. `"Your area in Lagos"` — auto-detect or type

**`"Find Emergency Artisans NOW"` button:** One massive full-width orange button.

**Results (appear immediately below):**
- Only artisans currently available AND within 5km shown
- Sorted by nearest first
- Results auto-refresh every 60 seconds
- Each artisan card prominently shows: `"Emergency rate applies (+30%). Your money is still protected by escrow."`

**Logged-in users:** Booking can be confirmed in 2 clicks — address pre-filled, artisan selected.

---

### WhatsApp Bot Flow (Reference — not a visual screen)

**Note:** This is a conversational flow, not a traditional web screen. Design the trigger button and entry points across the app, but the flow itself happens within WhatsApp.

**Customer Booking Flow:**
1. Customer sends any message to Nexplumb WhatsApp → Bot greets + asks what they need
2. Customer replies with trade → Bot asks for area
3. Customer gives area → Bot shows top 3 artisans (numbered list)
4. Customer picks an artisan → Bot confirms and sends a payment link
5. Customer pays → Bot confirms booking + reference number
6. Status updates sent via WhatsApp throughout the job
7. Job complete → Bot asks for a 1–5 rating reply

**Artisan Alerts:**
- New job near artisan → WhatsApp alert: `"New job near you! Reply YES to accept or NO to pass"`

---

## 9. PHASE 3 — ECOSYSTEM PORTALS

---

### EP-1 — Enterprise B2B Portal
**URL:** `enterprise.nexplumb.com`

**Audience:** Property managers, estate developers, hotel facilities teams, large organisations needing artisans regularly and at scale.

**Key Differentiator from Consumer Portal:** SLA contracts, dedicated artisan pools, bulk job scheduling, monthly invoicing.

**Dashboard Components:**

1. **Contract Overview:** Active SLA contracts · Total jobs this month · Spend vs monthly budget (budget tracker gauge) · Issue rate (% of jobs that resulted in dispute)

2. **Multi-Property Management:** Create and name multiple properties (e.g. `"Victoria Gardens Estate, Block A"`). Each property managed separately with its own job history, preferred artisan pool, and spend tracker.

3. **Bulk Job Request:** One form for submitting service needs across multiple units. E.g.: `"Building A: 12 electrical inspections, 3 plumbing checks, 2 carpentry repairs — next Tuesday"`.

4. **Dedicated Artisan Pool:** A curated list of preferred artisans per property. Jobs assigned to this pool first.

5. **Monthly Invoice:** Auto-generated PDF. Sent by email + downloadable from dashboard. Includes: job list, dates, artisan names, individual amounts, and total.

6. **SLA Dashboard:** Performance metrics per artisan and per property — response time, completion rate, avg rating, issues. Table with trend indicators.

---

### FP-1 — Artisan Finance Portal
**URL:** `app.nexplumb.com/artisan/finance`

**Purpose:** Converts a verified job history on Nexplumb into access to financial products — loans, buy-now-pay-later for materials, and financial identity. This is the `"bank account moment"` for artisans who have never had formal credit history.

**Components:**

1. **`"Your Nexplumb Financial Identity"` Panel:** A beautifully designed summary card. The artisan should feel proud of this. Shows: jobs completed, total earnings, completion rate, average rating, member duration. Visual design: treat this like a premium card — strong typography, navy/teal gradient, clean layout.

2. **Nexplumb Credit Score:** Circular dial gauge showing a score from 0–850. A short explanation: `"Your score is based on your completed jobs, earnings, ratings, and consistency on Nexplumb."` Higher score = more credit unlocked.

3. **`"Apply for Material Credit"` Section:** Shows pre-calculated credit limit based on platform activity: `"Based on your 47 completed jobs and ₦312,000 in earnings, you qualify for up to ₦50,000 in material credit."` One `"Apply now"` button starts the application — most details pre-filled.

4. **BNPL Toggle (on material orders):** Artisans with sufficient credit score see `"Pay in 3 installments from earnings"` option. Repayments auto-deducted from Nexplumb wallet over 3 payouts.

5. **Loan History Table:** Amount drawn · Repayment schedule · Amount outstanding · Next repayment date.

---

## 10. UNIVERSAL DESIGN STANDARDS

> **These standards apply to EVERY screen across ALL portals without exception.**

---

### 10.1 Five Required Screen States

Every single screen must be designed in all 5 states. Designing only the "perfect" default state will result in a broken experience for real users.

| State | When It Occurs | What Must Be Shown |
|---|---|---|
| **Default** | Normal loaded state with real data | The primary design. Always designed first. Uses real representative content, not "Lorem ipsum". |
| **Loading** | While data is being fetched from the server | **Skeleton loaders** — gray animated placeholder shapes matching the shape and layout of the real content. Never a blank white page. Never a spinner alone. |
| **Empty** | No data to display (new user, no bookings, no search results) | An illustration relevant to the context + descriptive headline + a primary CTA button. Example: empty bookings → calendar illustration + `"No bookings yet"` + `"Find an artisan"` button. Never just `"No data found."` |
| **Error** | Server error, network lost, invalid data | Red banner at top OR inline red border on the problematic section. Error message describes specifically what went wrong. A `"Try again"` button always included. Never just `"Something went wrong."` |
| **Success** | After an action completes (booking confirmed, payment sent, profile updated) | A teal animated checkmark, a summary of what just happened, and a clear next step offered to the user. The user must never guess whether their action worked. |

---

### 10.2 Accessibility Requirements (WCAG AA)

- **Colour contrast:** Body text minimum 4.5:1 ratio against background. Large headings minimum 3:1.
- **Keyboard navigation:** Every interactive element (buttons, links, fields, dropdowns) must be reachable and operable with keyboard only (Tab to move, Enter to click, Space for checkboxes).
- **Focus ring:** Every interactive element shows a visible focus indicator — 2px solid teal `#2A9D8F` outline, 2px offset. NEVER remove the focus ring without replacing it with a custom one.
- **Alt text:** Every image must have a descriptive `alt` attribute. Decorative images use `alt=""`.
- **Form labels:** Every input field must have a visible `<label>` element. Placeholder text is NOT a substitute.
- **Error messages:** Must describe the problem in text — never use colour alone to indicate an error.
- **Maps alternative:** Every map view must include a `"Switch to list view"` button. Maps must never be the only way to access information.
- **Minimum touch targets:** All tappable elements minimum 48×48px.
- **Minimum text size:** Body text not smaller than 14px. Captions not smaller than 12px.
- **Reduced motion:** All animations turned off when the user has `"Reduce Motion"` enabled in their OS.

---

### 10.3 SEO Standards

| Target Search Query | Page Responsible | Design Requirement |
|---|---|---|
| `"plumber near me Lagos"` | CW-1 + CW-2 | `"Plumbers in Lagos"` must appear as a real H1 or H2 heading with actual artisan data below it. Auto-detect user location. |
| `"how much does a plumber cost in Nigeria"` | CW-E1 | Interactive price guide + 400-word article on pricing below the tool. Results must be shareable. |
| `"[artisan name] plumber Lagos"` | CW-3 | Artisan's name in the page `<title>` tag and main `<h1>`. Google rich snippet schema for reviews (star ratings in search results). |
| `"emergency plumber Lagos"` | CW-E2 | Page loads under 2 seconds. Phone number above the fold. Trust signals immediately visible. |

**Performance Budget:**
- Homepage load time: Under 3 seconds on a 4G Nigerian connection. Google PageSpeed mobile score target: 75+.
- Images: Served at the exact display size (no oversized images). Lazy-loaded.
- Maps: Do NOT load on page load. Show a `"Load map"` button first. Only load map JavaScript when the user explicitly requests it.
- Fonts: Load system font first, then custom font asynchronously (non-blocking).
- All images: Must have explicit `width` and `height` attributes to prevent layout shift.

---

### 10.4 Design Handoff Standards

**Figma File Organisation:**
- Separate Figma file per portal
- Three frames per screen, side by side: Desktop 1280px · Tablet 768px · Mobile Web 375px
- Frame naming: `"CW-2 Search Results / Desktop 1280"` (always use Screen ID)
- All frames and component groups must use Auto Layout (no fixed positions)

**Mandatory Annotations Per Screen:**
- Breakpoint behaviour notes (e.g. `"At 768px: filter sidebar collapses to a drawer"`)
- Hover states for all interactive elements
- Sticky behaviour explained (e.g. `"This navbar is position:sticky top:0"`)
- Animation specs (duration, easing, trigger)
- Grid specification per breakpoint
- API dependencies note (which endpoints this screen needs)
- Real-time requirements (WebSocket connections, polling intervals)
- Third-party integrations listed (Paystack, Google Maps, NIMC API, Twilio, Termii)

**Notion Handoff Card (Required for every screen):**

| Field | Example |
|---|---|
| Screen ID + Portal | `CW-2 · Customer Web Portal` |
| User story | `"As a customer, I can filter search results by rating and distance so that I find the best artisan near me quickly."` |
| Breakpoints designed | ✅ Desktop · ✅ Tablet · ✅ Mobile Web |
| States designed | ✅ Default · ✅ Loading · ✅ Empty · ✅ Error · ✅ Success |
| API dependencies | `/api/artisans/search · /api/user/location · /api/filters/options` |
| Real-time? | `No (Map View only needs live updates)` |
| Third-party integrations | `Google Maps API` |
| Accessibility notes | `Map must have "Switch to list" button. All filter checkboxes keyboard-operable.` |

---

## FINAL NOTES FOR THE UI DESIGN AGENT

1. **Always apply the design system.** Every colour, font size, button style, and spacing value defined in Section 2 is mandatory across all screens. Do not substitute or improvise unless explicitly instructed.

2. **Context-first design.** This product is for Lagos, Nigeria. Artisan illustrations, photo references, names used in mockups, currency (₦ Naira), phone number format (+234), and language must reflect the Nigerian context.

3. **Trust is the product.** The entire design language must convey safety, reliability, and professionalism. Nigerian consumers are rightly skeptical of online payments. The escrow mechanism, verification badges, and the WhatsApp floating button are not decorative — they are the product's core trust infrastructure.

4. **Design mobile as a first-class experience** (except for the Admin Dashboard). Nigerian internet access is predominantly mobile. The booking flow, live tracking, and emergency booking page especially must be fast and functional on a 375px screen with a slow connection.

5. **Design all 5 screen states** for every screen before marking it complete. A screen that only works in the "perfect" state is not done.

6. **The Orange button is sacred.** `#E76F51` is used ONLY for primary actions. Every page has exactly ONE primary action. Do not use orange for decoration.

7. **The WhatsApp floating button appears on every customer-facing page** — homepage, search results, artisan profile, booking flow, and customer dashboard. It does not appear on admin or supplier portals.

8. **The booking flow (CW-4) and live tracking (CW-5) are the heart of the product.** Invest the most design effort here. These screens are what differentiates Nexplumb from a basic directory website.

---

*End of Nexplumb UI Design Agent Prompt v1.0*  
*Companion documents: Mobile App UX v1.0 · Web App UX v1.0 · PRD v1.0*

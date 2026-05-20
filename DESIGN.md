---
name: davidpollack.com
description: Personal brand site for David Pollack — Hall of Famer, ESPN analyst, speaker, author.
colors:
  georgia-red: "#C8102E"
  georgia-red-deep: "#A00D24"
  midnight-field: "#0A0A0A"
  press-box-charcoal: "#1A1A1A"
  scoreboard-slate: "#2A2A2A"
  stadium-fog: "#888888"
  field-line: "#E8E8E8"
  film-grain: "#F5F3F0"
  sideline-cream: "#FAF8F5"
typography:
  display:
    fontFamily: "'Bebas Neue', sans-serif"
    fontSize: "clamp(3.5rem, 8vw, 7rem)"
    fontWeight: 400
    lineHeight: 0.95
    letterSpacing: "0.02em"
  headline:
    fontFamily: "'Bebas Neue', sans-serif"
    fontSize: "clamp(2rem, 4vw, 3.5rem)"
    fontWeight: 400
    lineHeight: 1
    letterSpacing: "0.02em"
  title:
    fontFamily: "'Outfit', sans-serif"
    fontSize: "clamp(1.1rem, 1.5vw, 1.35rem)"
    fontWeight: 600
    lineHeight: 1.3
    letterSpacing: "normal"
  body:
    fontFamily: "'Outfit', sans-serif"
    fontSize: "clamp(0.95rem, 1vw, 1.05rem)"
    fontWeight: 400
    lineHeight: 1.7
    letterSpacing: "normal"
  label:
    fontFamily: "'Outfit', sans-serif"
    fontSize: "0.7rem"
    fontWeight: 600
    lineHeight: 1
    letterSpacing: "0.2em"
rounded:
  btn: "4px"
  input: "6px"
  card: "8px"
  form-card: "12px"
spacing:
  xs: "8px"
  sm: "16px"
  md: "24px"
  lg: "48px"
  xl: "80px"
  xxl: "120px"
components:
  button-primary:
    backgroundColor: "{colors.georgia-red}"
    textColor: "#ffffff"
    rounded: "{rounded.btn}"
    padding: "14px 32px"
    typography: "{typography.label}"
  button-primary-hover:
    backgroundColor: "{colors.georgia-red-deep}"
    textColor: "#ffffff"
  button-outline:
    backgroundColor: "transparent"
    textColor: "#ffffff"
    rounded: "{rounded.btn}"
    padding: "14px 32px"
  button-dark:
    backgroundColor: "{colors.midnight-field}"
    textColor: "#ffffff"
    rounded: "{rounded.btn}"
    padding: "14px 32px"
  input-default:
    backgroundColor: "{colors.sideline-cream}"
    textColor: "{colors.midnight-field}"
    rounded: "{rounded.input}"
    padding: "14px 16px"
  input-focus:
    backgroundColor: "{colors.sideline-cream}"
    textColor: "{colors.midnight-field}"
    rounded: "{rounded.input}"
    padding: "14px 16px"
---

# Design System: davidpollack.com

## 1. Overview

**Creative North Star: "The Film Room"**

The film room is where championships are actually built. No crowd, no broadcast graphics, no highlight music. Just the tape, sharp eyes, and the discipline to study what others ignore. That's the energy this design system lives in: focused, intense, and stripped of anything decorative that doesn't earn its place. The dark surfaces and disciplined typography reference the serious preparation behind the public performance. The Georgia Red is the only moment of heat in the room — and it's exactly where your eye goes.

The system is built on restraint under pressure. One accent color, one display typeface, one body typeface. High contrast, minimal ornamentation. The density is purposeful: this is not a spa website or a meditation app. David Pollack competes. The design competes with him.

This system rejects every aesthetic that could belong to any other speaker on the circuit — the gradient-text heroes, the "INSPIRE | MOTIVATE | TRANSFORM" stacked display, the stock photography of crowds, the floating testimonial carousels. It also rejects the ESPN broadcast UI (ticker animations, split-screen layouts, live data feel), the corporate keynote brochure, and the megachurch soft-pastels. If someone could look at a page and not know who owns this site, the design has failed.

**Key Characteristics:**
- Dark-ground primary surfaces with cream/off-white sections for relief
- Single accent (Georgia Red) used sparingly — never decorative
- Condensed display type (Bebas Neue) for all primary headlines; clean humanist sans (Outfit) for all body
- Sharp, flat component geometry — 4px button radius, minimal shadow
- Motion is scroll-reveal only; no looping animations, no parallax
- Credentials displayed as raw fact, never as "Why David" justification copy

## 2. Colors: The Film Room Palette

A near-monochromatic dark palette with a single moment of saturated color. The palette reads like game film: everything in blacks and grays except the one play you rewind.

### Primary
- **Georgia Red** (#C8102E): The UGA/Dawgs connection made literal. Used for primary CTAs, section-tag accents, focus rings, active states. Never used for decoration — only for action and emphasis. A screen should have at most one region of Georgia Red visible at a time.
- **Georgia Red Deep** (#A00D24): Hover state for red elements and pressed states. Slightly darker, more weight. Never used as a standalone background.

### Neutral
- **Midnight Field** (#0A0A0A): The base surface for hero sections and dark panels. Near-black with no blue cast. Text on this surface is pure white (#ffffff).
- **Press Box Charcoal** (#1A1A1A): Secondary dark surface. Cards, overlays, nav backgrounds. One step up from Midnight Field.
- **Scoreboard Slate** (#2A2A2A): Tertiary dark surface. Hover states on dark panels, divider backgrounds.
- **Stadium Fog** (#888888): Secondary text on dark backgrounds, placeholder text, muted metadata. Use for supporting information only — never for primary copy.
- **Field Line** (#E8E8E8): Borders, dividers, input strokes on light backgrounds.
- **Film Grain** (#F5F3F0): Off-white section backgrounds. Slightly warm to avoid sterile feel. Primary background for light-mode sections (speaking topics, bio content, forms).
- **Sideline Cream** (#FAF8F5): Warmest neutral. Default page background and input field fill. The subtle warmth is intentional; it stops the site from feeling like a medical form.

### Named Rules
**The One Red Rule.** Georgia Red appears in one place on a given screen — a single CTA button, a single section tag, a single focus state. When it's everywhere, it's nowhere. Its scarcity is the entire point; it's the only warm color in the room.

**The No Decorative Red Rule.** Georgia Red is never used as a background fill for a section, a decorative stripe, a gradient endpoint, or an illustration element. It marks action only.

## 3. Typography

**Display Font:** Bebas Neue (sans-serif fallback)
**Body Font:** Outfit (system-ui fallback)

**Character:** Bebas Neue is all-caps, tightly condensed, and completely unambiguous about who it belongs to. It reads like a championship banner, a locker room wall, a scoreboard. Outfit is modern and clean without being cold — it reads at small sizes with good rhythm and doesn't fight with Bebas for attention. Together they cover the full register: the shout and the conversation.

### Hierarchy
- **Display** (Bebas Neue, 400, clamp(3.5rem–7rem), line-height 0.95): Hero headlines and section landmarks only. Letter-spacing 0.02em. Always uppercase by nature of the typeface. No more than one per section.
- **Headline** (Bebas Neue, 400, clamp(2rem–3.5rem), line-height 1): Subsection headers, card titles, modal headers. Same rules as Display — sparse.
- **Title** (Outfit, 600, clamp(1.1rem–1.35rem), line-height 1.3): Component-level headings, keynote names, sidebar labels.
- **Body** (Outfit, 400, clamp(0.95rem–1.05rem), line-height 1.7): All paragraph text. Max line length 68ch. The workhorse. Should feel effortless to read.
- **Label** (Outfit, 600, 0.7rem, line-height 1, letter-spacing 0.2em, uppercase): Section tags ("ABOUT", "SPEAKING"), button text, form labels, metadata chips. This is the bridge between the display world and the body world.

### Named Rules
**The No Mixed Case Display Rule.** Bebas Neue is an all-caps typeface; never force it into mixed-case styling. If a headline needs to be sentence case or title case, it belongs in Outfit Title weight, not Bebas.

**The No Em Dash Rule.** Em dashes are prohibited in all UI copy — headlines, body text, CTAs, labels. Use commas, colons, semicolons, or periods. Em dashes in speaker site copy read as AI-generated filler punctuation.

## 4. Elevation

This system is predominantly flat. Dark surfaces are differentiated by their background color step (Midnight Field to Press Box Charcoal to Scoreboard Slate), not by shadows. Shadows appear only in two contexts: hover states on primary CTA buttons (a red glow lift), and on the sticky nav when scrolled (a subtle dark drop shadow). No cards float. No overlays have blur.

**The Flat-By-Default Rule.** Every surface starts flat. A shadow is a state change, not a decoration. If you reach for a shadow to make something "feel important," use color and scale instead.

### Shadow Vocabulary
- **CTA Hover Glow** (`0 8px 30px rgba(200, 16, 46, 0.4)`): Appears on `.btn-primary:hover` only. The red glow on lift is the single most kinetic moment in the interface — it should feel earned.
- **Nav Scroll Shadow** (`0 2px 20px rgba(0, 0, 0, 0.3)`): Applied to the sticky nav once the user scrolls past the hero. Lifts the nav slightly off the page to indicate it's a persistent control layer.
- **Dark Card Hover** (`0 8px 30px rgba(0, 0, 0, 0.2)`): Appears on `.btn-dark:hover`. Subtle depth lift.

## 5. Components

### Buttons
Sharp-edged and confident. Text is Label weight — all-caps, tracked out. No rounded corners that would soften the authority.

- **Shape:** Nearly square (4px radius). Sharp enough to feel assertive without being aggressive.
- **Primary (Georgia Red):** Background `#C8102E`, white text, 14px/32px padding. On hover: lifts 2px, red glow shadow, slight shimmer overlay.
- **Outline (Ghost):** Transparent fill, 1px border rgba(255,255,255,0.25) on dark backgrounds. Hover darkens the border to full white, adds a 5% white fill. Used as secondary action on dark panels.
- **Dark:** Background `#0A0A0A`, white text. Used on light/cream backgrounds. Hover: lifts 2px, soft dark glow.
- **Never use:** Rounded pill buttons (border-radius > 8px), gradient fills, icon-only buttons without visible affordance, ghost buttons on light backgrounds (they disappear).

### Cards / Containers
Cards are used sparingly. The system does not use identical-grid card arrays — that pattern is explicitly prohibited. When a card is necessary, it carries meaning through content and contrast, not chrome.

- **Corner Style:** Gently curved (8px radius)
- **Background on dark sections:** `#1A1A1A` (Press Box Charcoal), no border
- **Background on light sections:** `#FFFFFF` or `#F5F3F0`, 1px `#E8E8E8` border
- **Shadow Strategy:** Flat by default per Elevation rules
- **Internal Padding:** 24–32px

### Inputs / Fields
Clean and functional. The focus state is the only moment of accent color — it signals the active slot is the next step in a conversion flow.

- **Style:** 1px `#DDDDDD` border, `#FAF8F5` background, 6px radius, 14px/16px padding
- **Focus:** Border shifts to `#C8102E` (Georgia Red), 3px red glow ring `rgba(200,16,46,0.08)`. Unmistakable without being jarring.
- **Placeholder:** Outfit Regular, `#888888` (Stadium Fog)
- **Error:** Not yet defined; placeholder for future harden pass

### Navigation
- Desktop: horizontal bar, `#0A0A0A` background, Outfit 500 weight, 0.05em letter-spacing. Links use Film Grain off-white at rest, transition to white on hover. No underlines.
- Mobile: full-screen overlay, same background, stacked Bebas Neue links at large size.
- Active section: Georgia Red indicator (2px underline or dot — not a filled background)
- Sticky: acquires Nav Scroll Shadow on scroll

### Section Tag
The site's signature micro-component. Used at the top of every section to orient the reader.

- **Style:** Label weight (0.7rem, 600, 0.2em tracking, uppercase), Georgia Red
- **Before element:** 20px × 2px Georgia Red horizontal rule, flex-aligned
- **Purpose:** Replaces verbose section headers ("Welcome to the About Section") with sparse identifiers. Paired with Bebas Neue headline beneath it.

### Speaking Inquiry Form
The most important conversion surface on the site. Styled to match the form fields above but given elevated presentation: Film Grain background, generous padding (40px+), clear section separation between contact info and event details.

- **Submit button:** Full-width `.form-submit`, Georgia Red, Label weight. This is the only full-width primary button in the system.

## 6. Do's and Don'ts

### Do:
- **Do** use Bebas Neue for section headlines and hero type exclusively. Every display-weight heading should be this typeface.
- **Do** let credentials speak as bare facts: "3x All-American. Lott Trophy. Bednarik Award. 7x Emmy." No supporting copy explaining why those things matter.
- **Do** put the speaking inquiry CTA within one click of every page — in the nav, at the bottom of every section, and as the hero CTA on the speaking page.
- **Do** use cream/off-white sections to break the dark ground. The rhythm of dark–light–dark–light is what makes the long scroll readable.
- **Do** keep body line length to 65–70ch. The current site has lines that run too wide on desktop.
- **Do** maintain WCAG AA contrast on all text — especially Stadium Fog (#888888) on cream backgrounds, which is near the boundary and should be tested.
- **Do** use `rel="noopener noreferrer" target="_blank"` on every external link.

### Don't:
- **Don't** use generic motivational speaker site patterns: gradient text over hero images, "INSPIRE | MOTIVATE | TRANSFORM" stacked display, testimonial carousels, stock handshake photography, or "Why Choose Us" sections. This is the primary anti-reference. If it could belong to any speaker on the circuit, it has failed.
- **Don't** use em dashes. Not in headlines, not in body copy, not in CTAs. Commas, colons, or periods instead.
- **Don't** build identical card grids. Icon-heading-text repeated in a 3-column grid is the single most visible AI-generation tell in the current site. Use prose lists, numbered items, or table layouts instead.
- **Don't** add "WHY DAVID" or "Why Audiences Love David" or any self-justification section. Credentials and specifics do that work. Telling the audience why they should be impressed signals insecurity.
- **Don't** use Georgia Red as a section background, gradient endpoint, or decorative element. Red means "action." Anything else dilutes it.
- **Don't** use ESPN-style broadcast UI patterns: score tickers, split-screen layouts, live data feel, animated score counters. This is David's personal site, not a network property.
- **Don't** use soft pastels, hand-lettered type, or any visual language that reads as megachurch faith influencer. Faith informs tone, not the visual palette.
- **Don't** display statistics in a "numbers in boxes" grid (the classic "3x | All-American | 2022 | Hall of Fame" tile layout). That pattern reads as a SaaS metrics dashboard, not a person's story. Weave credentials into prose or use a simple horizontal ruled list.
- **Don't** use glassmorphism, blur cards, or gradient overlays as decoration. The palette is dark enough; tonal layering handles depth.
- **Don't** write copy that could belong to any speaker. Every line of copy on this site should only make sense if it's about David Pollack specifically.

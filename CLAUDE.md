# CLAUDE.md — davidpollack.com Rebuild

## Project Summary

Rebuilding davidpollack.com from a broken WordPress/Elementor/Avas theme site to a modern static site. Client is David Pollack — former UGA football star, College Football Hall of Famer, ESPN analyst, professional speaker, author. His manager Rose Lanham (Players for Good) is the day-to-day contact. Budget: $7,500. Timeline: 6 weeks.

---

## Tech Stack

- **Framework:** Astro
- **Styling:** Tailwind CSS
- **Hosting:** Render (staging via branch deploys)
- **CRM:** HubSpot free tier (replaces Mailchimp — handles lead tracking, email collection, newsletters)
- **Analytics:** Google Analytics 4
- **Repository:** GitHub (private)
- **Domain:** davidpollack.com (currently on GoDaddy — DNS access not yet secured)

---

## Project Structure

```
davidpollack.com/
├── src/
│   ├── layouts/
│   │   └── BaseLayout.astro          # Global layout: head meta, nav, footer, schema
│   ├── components/
│   │   ├── Nav.astro                  # Main navigation
│   │   ├── Footer.astro              # Footer with social links + newsletter signup
│   │   ├── NewsletterSignup.astro    # Reusable "Stay in Touch" — submits to HubSpot
│   │   ├── SpeakingInquiryForm.astro # Custom form — submits to HubSpot API
│   │   ├── ContactForm.astro         # General contact form
│   │   ├── SpeakingTopicCard.astro   # Card component for keynote topics
│   │   ├── BookCTA.astro             # Book callout block (reusable on multiple pages)
│   │   ├── PodcastEmbed.astro        # Podcast player embed (Spotify/Apple)
│   │   ├── SocialEmbed.astro         # Social media embed wrapper
│   │   ├── SEOHead.astro             # Reusable head component: meta, OG, Twitter, canonical
│   │   └── SchemaMarkup.astro        # JSON-LD structured data injection
│   ├── pages/
│   │   ├── index.astro               # Homepage
│   │   ├── meet-david.astro          # About / bio
│   │   ├── every-day-counts.astro    # Book page
│   │   ├── speaking.astro            # Speaking + inquiry form
│   │   ├── media.astro               # Podcast, social, video
│   │   ├── blog/
│   │   │   └── index.astro           # Blog listing (infrastructure only — no posts at launch)
│   │   └── contact.astro             # Get in Touch
│   ├── content/                       # Content files (markdown or CMS-connected)
│   │   └── blog/                      # Blog posts (future)
│   ├── data/
│   │   ├── speakingTopics.json       # Four keynote topics with descriptions
│   │   ├── socialLinks.json          # All social media URLs
│   │   └── siteMetadata.json         # Global SEO defaults, site name, OG defaults
│   └── styles/
│       └── global.css                 # Tailwind base + any custom styles
├── public/
│   ├── images/                        # Optimized images
│   ├── favicon.ico
│   ├── robots.txt                     # Sitemap reference included
│   └── _redirects                     # 301 redirects from old WordPress URLs
├── astro.config.mjs
├── tailwind.config.mjs
├── package.json
├── CLAUDE.md                          # This file
└── README.md
```

---

## Pages & Requirements

### Homepage (`/`)
- Hero section with strong, unique H1
- One-paragraph intro: who David is
- Speaking topics preview (links to /speaking/)
- Book callout with cover image (links to /every-day-counts/)
- Podcast embed or link
- Newsletter signup ("Stay in Touch" — HubSpot)
- Foundation mention with link
- **Schema:** Person (JSON-LD)

### Meet David (`/meet-david/`)
- Full bio narrative (refine existing 1,408 words from current site)
- Career highlights: Hall of Fame, 3x All-American, Lott Trophy, Bednarik Award, 7x Emmy, ESPN (12 years)
- Faith and family angle
- **Schema:** Person (JSON-LD)

### Every Day Counts (`/every-day-counts/`)
- Book description and cover image
- Purchase / pre-order links
- The 30-Day Challenge section
- "Experience Every Day Counts LIVE" (speaking tie-in)
- **Schema:** Book (JSON-LD) — title, author, publisher, ISBN, cover image, purchase links
- **Critical:** Open Graph image must be set — fans share this page

### Speaking (`/speaking/`)
- Unique H1 reflecting page topic
- David's credentials and why audiences connect
- Four signature keynotes:
  1. Every Day Counts
  2. Faith, Family, Football
  3. Overcoming Adversity & Leadership
  4. Encouraged by Faith
- Speaking inquiry form (custom-built, submits to HubSpot API)
- **Schema:** Service (JSON-LD) — four keynotes as services

### Media (`/media/`)
- Podcast embeds (Apple Podcasts, Spotify)
- Social media links/embeds (YouTube, Instagram, Facebook, X, TikTok)
- Video highlights if available

### Blog (`/blog/`)
- Blog listing page with infrastructure ready
- No posts at launch — content comes post-launch from podcast/video repurposing
- Individual post template with Article schema (automated)
- URL structure: `/blog/[slug]/`

### Contact (`/contact/`)
- General contact form
- Social links
- Newsletter signup
- **Schema:** ContactPage (JSON-LD)

### Newsletter Signup ("Stay in Touch")
- Reusable component — appears on homepage, contact page, footer, and inline CTAs on key pages
- Submits to HubSpot API for email collection

---

## HubSpot Integration

**Account:** speaking@davidpollack.com (or speaking@dp.com — confirm with Rose)
**Users:** Rose Lanham (primary), Spencer Foreman (admin)

### Forms → HubSpot API
All forms are custom-designed on the site. No HubSpot embedded forms (avoids their branding on free tier). Submit via HubSpot Forms API or Contacts API.

### Speaking Inquiry Form Fields
- Name (required)
- Email (required)
- Organization
- Event date
- Event type
- Message

### Deal Pipeline
New Inquiry → Followed Up → Proposal Sent → Booked / Lost

### Newsletter Signup Fields
- Email (required)
- First name (optional)

### Free Tier Limits
- 1,000 contacts
- 2,000 emails/month
- 1 deal pipeline
- 2 users
- No automation/workflows
- HubSpot branding on native forms (we avoid this by using custom forms)

---

## SEO Requirements

Every page from the old WordPress site had SEO problems. The rebuild solves all of them by default.

### Per-Page Metadata (via SEOHead component)
- Unique title tag (50-60 characters)
- Meta description (140-160 characters)
- Open Graph tags: og:title, og:description, og:image, og:type, og:url
- Twitter Card tags: twitter:card, twitter:title, twitter:description, twitter:image
- Canonical URL
- `<html lang="en-US">`

### Structured Data (via SchemaMarkup component, JSON-LD)
- **Homepage + Meet David:** Person schema — name, job titles, alma mater (UGA), awards (College Football Hall of Fame, 3x All-American, Lott Trophy, Bednarik Award, 7x Emmy), employer history (ESPN), social profiles, book authorship
- **Every Day Counts:** Book schema — title, author, publisher, ISBN, cover image, purchase links
- **Speaking:** Service schema — four keynotes as services
- **Blog posts:** Article schema (automated per post via content collection)
- **Contact:** ContactPage schema

### Technical SEO
- Clean, descriptive URL slugs
- Auto-generated sitemap.xml (Astro's @astrojs/sitemap integration)
- robots.txt with sitemap reference
- 301 redirects from all old WordPress URLs (see Redirects section)
- Image alt text on every image — no exceptions
- Lazy loading on below-fold images
- `rel="noopener noreferrer"` on all external `target="_blank"` links
- Mobile-first responsive design
- Fast page loads (static = minimal requests, small bundle)

---

## Redirects

All existing WordPress URLs get 301 redirected. Implemented via `public/_redirects` file or Render redirect rules.

```
# Page redirects
/meet-david/                        /meet-david/          301
/every-day-counts/                  /every-day-counts/    301
/david-pollack-speaking/            /speaking/            301
/media/                             /media/               301
/news-2/                            /blog/                301
/news/                              /blog/                301
/get-in-touch/                      /contact/             301

# Junk page cleanup
/services/                          /                     301
/example-of-service-details-page/   /                     301
/home-business-consultant/          /                     301

# Security cleanup
/author/admin/                      /                     301
/wp-json/*                          /                     301
/wp-admin/*                         /                     301

# Lorem ipsum slug fix
/ut-enim-ad-minima-veniam-ullam-corporis-suscipit-laboriosam/  /blog/faith-through-trials/  301

# Catch-all for old blog posts (map individually as needed)
# /old-post-slug/                   /blog/new-slug/       301
```

---

## Design Direction

- Build on the mockup Spencer previously sent Rose (she approved it)
- Mobile-first — original pain point that started this project
- Personal brand hub, not corporate
- Clean, modern, fast
- David's personality: faith, football, family, energy
- Pull images from current site initially; ask Rose for high-res versions
- Remove the photo Rose flagged (suit with three images behind him)

---

## Content Strategy

- Spencer drafts copy, Rose/David approve
- Refine and rewrite existing content from current site
- Current word counts for reference:
  - Homepage: 952 words
  - Meet David: 1,408 words
  - Every Day Counts: 1,257 words
  - Speaking: 944 words
  - Media: 935 words
  - Contact: 664 words
- Post-launch: blog content from podcast/video transcriptions (retainer scope)

---

## Content Management Decision (TBD)

Choose before build begins:

**Option A: Markdown in repo**
- Spencer handles all updates via retainer
- Simpler architecture, no dependencies
- Content lives in `src/content/`

**Option B: Headless CMS (Sanity or Contentful free tier)**
- Rose can update content via dashboard
- More setup upfront, more self-service long-term
- Both integrate cleanly with Astro's content collections

---

## Code Standards

- Use Astro components (`.astro` files) for all pages and layouts
- Use Tailwind utility classes — no custom CSS unless absolutely necessary
- Keep components small and reusable
- All images must have alt text
- All external links must have `rel="noopener noreferrer"` and `target="_blank"`
- Use semantic HTML: proper heading hierarchy (H1 → H2 → H3, no skipping)
- Every page gets exactly one unique H1
- No inline styles
- Performance budget: aim for 90+ Lighthouse score on both desktop and mobile

---

## Environment & Deployment

- **Dev:** `npm run dev` — local Astro dev server
- **Build:** `npm run build` — static output
- **Preview:** `npm run preview` — preview production build locally
- **Staging:** Push to a feature/staging branch → Render auto-deploys a preview URL
- **Production:** Merge to `main` → Render deploys to production

---

## Open Blockers

1. **Domain access** — Need GoDaddy credentials or DNS delegation from Rose before launch
2. **Google Search Console** — Determine if existing access exists (ask Rose)
3. **Content management** — Markdown vs headless CMS (decide before build)
4. **Photos** — Need high-res assets from Rose
5. **Book details** — ISBN, publisher name, purchase links (needed for Book schema)
6. **HubSpot email** — Confirm: speaking@davidpollack.com or speaking@dp.com?
7. **Foundation scope** — How much presence on davidpollack.com vs its own site?
8. **Brave Books children's book** — Dedicated section or mention with link?

---

## Key Context

- This is BetterBuilt Digital's first client — the work sets the standard
- Rose manages Players for Good (other speakers) — great work here opens doors
- Nate (friend of David's) ran an SEO audit and positioned himself as a $200K "ecosystem" option. He's not part of the project team. Don't give his opinions weight in technical decisions.
- David is cost-conscious — the site was originally built for $1,200
- Rose loved the mockup Spencer sent — build on that direction
- The existing WordPress site was built by importing a theme demo and swapping content. That's why the problems are foundational, not surface-level.

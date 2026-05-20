# David Pollack Website Rebuild — Project Instructions

## Project Overview

**Client:** David Pollack (managed by Rose Lanham at Players for Good)
**Agency:** BetterBuilt Digital (Spencer Foreman)
**Project:** Full rebuild of davidpollack.com
**Budget:** $7,500 (two payments: $3,750 kickoff, $3,750 at launch)
**Timeline:** 6 weeks from kickoff to launch
**Maintenance retainer:** Continues separately, unchanged

---

## About David Pollack

- Former University of Georgia football star
- College Football Hall of Famer
- 3x All-American, Lott Trophy, Bednarik Award winner
- 7-Time Emmy Award winner
- Former ESPN college football analyst (12 years)
- Author of "Every Day Counts" (new book)
- Children's book through Brave Books
- Active podcast (Family Matters Podcast)
- David Pollack Foundation
- Professional speaker

### Key Speaking Topics
- Every Day Counts
- Faith, Family, Football
- Overcoming Adversity & Leadership
- Encouraged by Faith

---

## Key Contacts

| Name | Role | Email |
|------|------|-------|
| Rose Lanham | David's manager / main POC | Rose@playersforgood.com |
| Spencer Foreman | Developer / BetterBuilt Digital | spencer@betterbuiltdigital.com |
| Nate | Friend of David's, marketing background | Not a team member — see context below |

### Nate Context
Nate inserted himself into the project conversation. He ran an AI-generated SEO audit of the current site and positioned himself as the "strategic ecosystem" option (referencing $200K), while framing Spencer's rebuild as "just a nicer billboard." His audit is technically useful as a diagnostic checklist but his conclusion — that the site just needs cleanup, not a rebuild — is wrong. The problems are foundational (theme demo import, no SEO infrastructure). Spencer is positioned as the practical, affordable option who delivers results.

---

## Tech Stack

| Layer | Choice | Notes |
|-------|--------|-------|
| Framework | Astro (recommended) | Static-first, fast out of the box, supports client-side components where needed |
| Styling | Tailwind CSS | Utility-first, fast to build, easy to maintain |
| Hosting | Render | Staging previews via branch deploys |
| Repository | GitHub | Private repo |
| CRM | HubSpot (free tier) | Replaces Mailchimp. Handles lead tracking, speaking inquiries, email collection, and newsletters |
| Analytics | Google Analytics (GA4) | Fresh setup on the new site |
| Search Console | Google Search Console | Need to determine if existing access exists — ask Rose |
| Domain | davidpollack.com (currently on GoDaddy) | Spencer does NOT have domain access yet — must resolve before launch |

---

## Pages & Site Architecture

The site should feel like the main hub for everything David has going on.

### Homepage
- Hero section with strong H1
- Quick intro — who David is in one paragraph
- Speaking topics preview (links to Speaking page)
- Book callout (links to Every Day Counts page)
- Podcast embed or link
- Newsletter signup ("Stay in Touch")
- Foundation mention with link

### Meet David (About)
- Full bio narrative (current site has 1,408 words of strong copy — rewrite/refine)
- Career timeline or highlights (Hall of Fame, All-American, Emmy Awards, ESPN)
- Faith and family angle
- Person schema (structured data)

### Every Day Counts (Book Page)
- Book description and cover image
- Pre-order / purchase links
- The 30-Day Challenge section
- "Experience Every Day Counts LIVE" section (speaking tie-in)
- Book schema (structured data)
- Open Graph image for social sharing (critical — fans share book pages)

### Speaking
- H1 that reflects the page topic
- David's credentials and why audiences connect
- Four signature keynotes with descriptions:
  - Every Day Counts
  - Faith, Family, Football
  - Overcoming Adversity & Leadership
  - Encouraged by Faith
- Speaking inquiry form (custom-built, submits to HubSpot API)
- Service schema (structured data)

### Media
- Podcast embeds (Apple Podcasts, Spotify)
- Social media embeds/links (YouTube, Instagram, Facebook, X, TikTok)
- Video highlights if available

### News / Blog
- Build the blog infrastructure now, but no posts at launch
- Blog posts will come in the future (repurposed from podcast/video content)
- Article schema on all posts (automated)
- Clean URL structure: /blog/post-slug

### Get in Touch (Contact)
- General contact form
- Social links
- Newsletter signup
- ContactPage schema

### Newsletter Signup ("Stay in Touch")
- Appears on multiple pages (not just one dedicated spot)
- Submits to HubSpot for email collection
- Footer component + inline CTAs on key pages

---

## HubSpot CRM Setup

**Account email:** speaking@dp.com
**Users:** Rose (primary), Spencer (admin/setup)

### What HubSpot handles:
1. **Speaking inquiry tracking** — form submissions create contacts with deal pipeline (New Inquiry → Followed Up → Proposal Sent → Booked / Lost)
2. **Email list collection** — "Stay in Touch" signups across the site
3. **Basic newsletters** — monthly sends to the list (2,000 emails/month on free tier)
4. **Contact management** — single database of everyone who interacts with David's brand

### Form integration approach:
- Custom-designed forms on the site (not HubSpot embedded forms)
- Submit to HubSpot API to avoid HubSpot branding and maintain design control
- Speaking inquiry form captures: name, email, organization, event date, event type, message

### Free tier limits to be aware of:
- 1,000 contacts (plenty for now — currently ~2 leads/month)
- 2,000 emails/month
- 1 deal pipeline
- No automation/workflows
- HubSpot branding on their native forms/emails (avoided by using custom forms)
- 2 users

### Future upgrade path:
- Data is portable — CSV export to any other CRM if they outgrow HubSpot
- HubSpot Starter is ~$15/month if they need more
- Automation and workflows become upsell opportunities through the retainer

---

## SEO Foundation

Everything from Nate's audit gets solved by default in the rebuild. No patching — built right from the start.

### Metadata (every page):
- Unique, descriptive title tags (50-60 characters)
- Meta descriptions (140-160 characters)
- Open Graph tags (og:title, og:description, og:image, og:type, og:url)
- Twitter Card tags
- Canonical URLs
- Proper `<html lang="en-US">` attribute

### Structured Data / Schema (JSON-LD):
- **Homepage:** Person schema (name, job titles, alma mater, awards, social profiles)
- **Meet David:** Person schema
- **Every Day Counts:** Book schema (title, author, publisher, ISBN, cover image, purchase links)
- **Speaking:** Service schema (four keynote topics as services)
- **Blog posts:** Article schema (automated per post)
- **Get in Touch:** ContactPage schema
- **Sitewide:** Organization schema for BetterBuilt? Or just Person for David

### Heading Structure:
- Every page gets a unique, descriptive H1
- Sequential heading hierarchy (H1 → H2 → H3, no skipping levels)
- No global template H1 repeating across pages

### Technical SEO:
- Clean, descriptive URL slugs on every page
- Sitemap.xml (auto-generated)
- robots.txt with sitemap reference
- 301 redirects from all existing WordPress URLs to new equivalents
- Junk pages (demo pages, lorem ipsum slug) redirect to homepage
- Image alt text on every image
- Lazy loading on below-fold images
- Fast page loads (static site = minimal requests, small bundle)
- Mobile-first responsive design
- `rel="noopener"` on all external links

### What's NOT included in this project:
- Ongoing SEO (content creation, link building, keyword strategy)
- Blog content writing
- Competitor ranking analysis
- These become retainer conversations post-launch

---

## Design Direction

### General approach:
- Build on the mockup Spencer previously sent Rose (she loved it)
- Mobile-first — this was one of the original pain points
- The site should feel like a personal brand hub, not a corporate site
- Clean, modern, fast
- David's personality should come through — faith, football, family, energy

### Assets:
- Pull images from the current site initially
- Ask Rose for high-res versions and any new approved photos
- Rose previously flagged a specific photo to remove (suit with three images behind him)

### Design approval process:
- Present via live staging site on Render (branch deploy)
- Rose + David both need to approve
- 2 rounds of revisions included in the $7,500
- Additional revisions beyond 2 rounds fall under the maintenance retainer

---

## Content Strategy

### For launch:
- Spencer drafts copy, Rose/David approve
- Rewrite and refine existing content from the current site (most pages have solid copy)
- Current content word counts for reference:
  - Homepage: 952 words
  - Meet David: 1,408 words
  - Every Day Counts: 1,257 words
  - Speaking: 944 words
  - Media: 935 words
  - Get in Touch: 664 words

### Post-launch (retainer scope):
- Blog content from podcast/video transcriptions
- FAQ section (high value for AI search engines)
- Potential FAQ topics: "What does David Pollack do now?", "What is David Pollack's book about?", "How do I book David Pollack as a speaker?", "What is See Ball Get Ball?"

---

## Content Management

### Decision needed:
- **Option A: Markdown files in the repo** — Spencer handles all content updates through the retainer. Simpler architecture, no external dependencies.
- **Option B: Headless CMS (Sanity or Contentful free tier)** — Rose could update content through a dashboard. More setup work upfront but more self-service long-term.
- Decide before build begins. Either works with Astro.

---

## Redirects Plan

All existing WordPress URLs that have any SEO value get 301 redirected to their new equivalents. Handled via Render's redirect rules or a `_redirects` file.

| Old URL | New URL | Notes |
|---------|---------|-------|
| /meet-david/ | /meet-david/ | Keep same slug |
| /every-day-counts/ | /every-day-counts/ | Keep same slug |
| /david-pollack-speaking/ | /speaking/ | Simplify slug |
| /media/ | /media/ | Keep same slug |
| /news-2/ | /blog/ | Consolidate to single blog |
| /news/ | /blog/ | Redirect duplicate |
| /get-in-touch/ | /contact/ | Simplify slug |
| /ut-enim-ad-minima-veniam-.../ | /blog/faith-through-trials/ | Fix lorem ipsum slug |
| /services/ | / | Demo page → homepage |
| /example-of-service-details-page/ | / | Demo page → homepage |
| /home-business-consultant/ | / | Duplicate homepage → homepage |
| /author/admin/ | / | Security + SEO cleanup |
| All other blog post URLs | /blog/[new-slug]/ | Preserve any indexed posts |

---

## Pre-Launch Checklist

### Before kickoff:
- [ ] Get domain access sorted (GoDaddy credentials or DNS delegation) — ask Rose
- [ ] Determine Google Search Console access — ask Rose
- [ ] Decide on content management approach (markdown vs headless CMS)
- [ ] Collect high-res photos from Rose
- [ ] Set up GitHub repo
- [ ] Complete HubSpot account setup and verification

### Before design approval:
- [ ] Staging site deployed on Render
- [ ] All pages stubbed with real content
- [ ] Mobile experience tested and polished
- [ ] Rose + David review on their devices

### Before launch:
- [ ] All SEO metadata in place (titles, descriptions, OG tags, schema)
- [ ] All redirects configured and tested
- [ ] HubSpot forms tested end-to-end (inquiry → CRM contact → deal created)
- [ ] Newsletter signup tested (submits to HubSpot)
- [ ] GA4 installed and tracking
- [ ] Google Search Console verified and sitemap submitted
- [ ] Image alt text on every image
- [ ] Lighthouse audit run (desktop + mobile) — document scores
- [ ] Cross-browser testing (Chrome, Safari, Firefox, mobile Safari, mobile Chrome)
- [ ] DNS cutover from GoDaddy to Render
- [ ] Old WordPress site taken offline (or kept as backup temporarily)
- [ ] Test all redirects from old URLs

### Post-launch (first week):
- [ ] Monitor Google Search Console for crawl errors
- [ ] Verify redirects are being followed
- [ ] Test Open Graph previews (Facebook Sharing Debugger, Twitter Card Validator)
- [ ] Check HubSpot is receiving form submissions correctly
- [ ] Send Rose a walkthrough of HubSpot dashboard

---

## Project Milestones & Payment Schedule

| Milestone | Payment | Target |
|-----------|---------|--------|
| Kickoff (project begins) | $3,750 | Week 0 |
| Design approval (staging site approved by Rose + David) | — | Week 2-3 |
| Launch (site live on davidpollack.com) | $3,750 | Week 6 |

---

## Open Questions / Blockers

1. **Domain access** — Who has GoDaddy login? Spencer needs DNS access before launch.
2. **Google Search Console** — Does Rose/David have access to the existing property?
3. **Content management** — Markdown in repo vs headless CMS? Decide before build.
4. **Photos** — Need high-res assets from Rose. Which photo(s) does David want removed?
5. **Book details** — ISBN, publisher name, current purchase links for Book schema.
6. **Foundation** — How much presence does the foundation get on davidpollack.com vs its own site?
7. **Brave Books children's book** — Dedicated section or just a mention with link?

---

## Notes for Future Conversations in This Project

This document is the source of truth for the David Pollack website rebuild. When starting a new conversation in this project, reference this doc for context on scope, tech decisions, and client dynamics. Key things to remember:

- Spencer uses AI/Claude heavily in his workflow — lean into that
- Rose is the decision-maker day-to-day, but David has final approval on design
- Nate is not part of the project team — don't give him influence over decisions
- This is Spencer's first client — the work here sets the standard for BetterBuilt Digital
- Rose manages Players for Good which has other speakers — doing great work here opens the door to more clients
- Keep it practical, keep it deliverable, don't over-engineer

# Kalemah Islamic Centre — Eid Salah Landing Page

## Project Documentation & Brand Guide

---

## 1. Project Overview

**Client:** Kalemah Islamic Centre (Est. 2007, Dubai, UAE)
**Page:** Eid Salah With Kalemah — Event Landing Page
**Proposed URL:** `https://www.eidwithkalemah.com`
**Purpose:** Registration landing page for Eid Al Fitr prayer event
**Status:** Production-ready single-page HTML with embedded assets
**Permit No:** 007260792

---

## 2. Event Details (Current Content)

| Field | Value |
|-------|-------|
| Event | Eid Salah With Kalemah |
| Date | 1st Shawwal, 2026 |
| Gates Open | 5:45 AM |
| Takbeeraat | 6:05 AM |
| Eid Salah | 6:20 AM |
| Khutba | 6:40 AM (in English) |
| Greetings & Departure | 7:15 AM |
| Venue | Shabab Al Ahli Stadium, Next to Al Mulla Plaza & Stadium Metro, Dubai |
| Entry | Free |
| Partner | Shabab Al Ahli Club |
| Registration | https://www.eidwithkalemah.com |
| FAQ Page | https://www.kalemah.org/FAQeid25/ |
| Website | https://www.kalemah.org |

---

## 3. Brand Identity Guide

### 3.1 Color Palette

```css
--cream:       #F5EDDE   /* Primary background — warm cream */
--cream-light: #FAF6EE   /* Secondary background — lighter cream */
--gold:        #D4A95A   /* Primary accent — brand gold */
--gold-light:  #E8C97D   /* Light gold for highlights */
--gold-dark:   #B8903F   /* Dark gold for hover states */
--teal:        #344955   /* Primary dark — brand teal */
--teal-light:  #3E5A68   /* Light teal for hover */
--teal-dark:   #2A3B45   /* Darkest teal for footer */
--text-dark:   #2B3A42   /* Body text dark */
--text-muted:  #6B7B83   /* Secondary text */
```

**Usage Rules:**
- Cream backgrounds for light sections (hero, schedule, FAQ)
- White `#fff` for detail cards and location sections
- Teal `#344955` for dark sections (highlights/video, hero card)
- Gold `#D4A95A` for CTAs, accents, badges, timeline dots
- Never use pure black or pure white as backgrounds

### 3.2 Typography

| Role | Font | Weight | Usage |
|------|------|--------|-------|
| Display/Headings | Cormorant Garamond | 300, 400, 600, 700 | Section titles, hero title, card date, nav logo |
| Body/UI | Outfit | 300, 400, 500, 600, 700 | Body text, nav links, buttons, labels |
| Arabic | Cormorant Garamond | 400 | Arabic text with `direction: rtl` |

**Google Fonts import:**
```
https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;0,700;1,400&family=Outfit:wght@300;400;500;600;700&display=swap
```

### 3.3 Logo

- **Source:** `Kalemah_Logo.pdf` — extracted as transparent PNG
- **Mark:** Gold circle with stylized "K" Arabic calligraphy motif
- **Sizes used:** 52px (nav), 500px (decorative), 800px (background watermark)
- **All logo variants are base64-embedded in the HTML**

### 3.4 Islamic Geometric Patterns

Four pattern variants from brand identity (pages 24–27 of brand PDF):

| Pattern | Description | Used In |
|---------|-------------|---------|
| Gold on Teal (thick) | Bold gold interlocking pattern on dark teal | Footer background |
| Teal on Gold (thick) | Bold teal pattern on gold background | CTA section |
| Gold outline on cream | Thin gold lines on warm gold/cream | Hero, FAQ backgrounds |
| Gold outline on teal | Thin gold lines on dark teal | Hero card, highlights section |

**All patterns are base64-embedded as JPEG tiling backgrounds at low opacity (4-12%)**

### 3.5 Design Principles

- **Tone:** Refined, warm, community-oriented, premium Islamic aesthetic
- **Layout:** Clean sections with generous white space
- **Icons:** All SVG stroke icons (no emojis), using brand colors
- **Animations:** Scroll-reveal on sections, floating badge, breathing logo watermark
- **Responsive:** Full mobile support with hamburger nav at 768px

---

## 4. Page Structure

```
├── Advisory Banner (sticky gold, dismissible)
│   └── Event Status Advisory notice
│
├── Navigation (fixed below banner, transparent → cream on scroll)
│   ├── Logo (52px) + "KALEMAH" wordmark
│   └── CTA: "Register Now" button (only nav item)
│
├── Hero Section (cream gradient + pattern overlay)
│   ├── Event tag badge
│   ├── Title: "Eid Salah / With Kalemah"
│   ├── Arabic subtitle
│   ├── Description paragraph
│   ├── CTA buttons (Register + Location)
│   └── Event Card (teal, date: 1st Shawwal 2026, salah time, gates open, venue, khutba + Free badge)
│
├── Details Section (white background)
│   ├── "What to Expect" heading
│   └── 4 feature cards (3+1 grid):
│       Modified Arrangements (highlighted, first), Eid Salah & Khutba,
│       Community Gathering, Parking Available
│
├── Highlights Section (teal + pattern)
│   ├── "Event Highlights" heading
│   └── YouTube video embed (16:9 responsive)
│
├── Schedule Section (cream background)
│   ├── "Morning Schedule" heading
│   └── Horizontal timeline (5 stops)
│
├── Location Section (white)
│   ├── Google Maps embed
│   ├── Venue details
│   └── 3 tip boxes (Getting There, Parking, What to Bring)
│
├── Venue Partner Section (compact horizontal card)
│   ├── Accred.png logo + club name + address
│   └── Permit No: 007260792
│
├── FAQ Section (cream + pattern)
│   └── 14 expandable accordion items
│
├── CTA Section (gold + pattern + logo watermark)
│   └── Final registration call-to-action
│
└── Footer (dark teal + pattern)
    └── Logo + brand text
```

---

## 5. Technical Details

### 5.1 File Structure

```
kalemah-eid25.html    — Single-page HTML file
Accred.png            — Shabab Al Ahli Club logo (venue partner)
                        CSS inline in <style>
                        Most images base64-embedded
                        JS inline in <script>
                        Zero external dependencies (except Google Fonts)
```

### 5.2 Embedded Assets

- 1× Kalemah logo (3 sizes: nav 42px, hero 500px, bg 800px) — PNG with transparent bg
- 4× Islamic geometric pattern tiles — JPEG at 800px width
- Total base64 payload: ~600KB

### 5.3 Features

- Scroll-triggered reveal animations (IntersectionObserver)
- Sticky navbar with scroll-based background transition
- Responsive mobile menu
- FAQ accordion (pure JS, no library)
- Google Maps iframe embed
- YouTube video embed (responsive 16:9)

---

## 6. Using Claude Code in VS Code

### 6.1 Setup

1. Open VS Code
2. Open the folder containing `kalemah-eid25.html` and this `README.md`
3. Claude Code should be available in your terminal or sidebar

### 6.2 Making Content Changes

Talk to Claude Code naturally. Examples:

```
Change the event date from March 30 to April 1
```

```
Update the venue to "Dubai World Trade Centre, Hall 7"
```

```
Change the gates open time to 6:00 AM and remove the 5:30 line from schedule
```

```
Add a new FAQ: "Can I bring food?" with answer "Yes, you may bring sealed snacks"
```

```
Replace the YouTube video URL with https://youtube.com/embed/NEW_ID
```

```
Change the hero description to: "Join us for a blessed Eid morning..."
```

### 6.3 Making Design Changes

```
Make the CTA section use teal instead of gold
```

```
Add a new section between FAQ and CTA for sponsor logos
```

```
Change the font from Cormorant Garamond to Playfair Display
```

### 6.4 Creating New Pages

```
Create a new page called faq-eid25.html using the same brand 
guidelines from README.md. It should have the same nav, footer, 
and patterns but the content should be a full FAQ page with 
these questions: [paste questions]
```

```
Create an about.html page following the Kalemah brand guide in 
README.md with sections for: Our Story, Our Team, Our Mission
```

### 6.5 Tips for Claude Code

- **Always reference this file:** Say "follow the brand guide in README.md"
- **Be specific:** "Change the hero title" not "change the title"
- **Preview locally:** Use VS Code Live Server extension to see changes instantly
- **One change at a time:** Easier to review and undo if needed
- **For new pages:** Ask Claude to "use the same nav, footer, colors, fonts, and patterns"

---

## 7. Hosting Guide

### 7.1 Recommended: Firebase Hosting (Google)

**Why Firebase:**
- Free tier (10GB storage, 360MB/day transfer — more than enough)
- Custom domain support
- SSL/HTTPS automatic
- Fast global CDN
- Easy CLI deployment from VS Code terminal
- Can add more pages anytime

**Setup Steps:**

```bash
# 1. Install Firebase CLI
npm install -g firebase-tools

# 2. Login to Google account
firebase login

# 3. Initialize project (run in your project folder)
firebase init hosting

# When prompted:
#   - Select "Create a new project" or use existing
#   - Public directory: . (or public if you move files there)
#   - Single-page app: No
#   - Overwrite index.html: No

# 4. Rename your file for the homepage
cp kalemah-eid25.html index.html

# 5. Deploy
firebase deploy

# Your site is live at: https://your-project.web.app
```

**Adding a Custom Domain:**

```bash
# In Firebase Console (console.firebase.google.com):
# 1. Go to Hosting → Add custom domain
# 2. Enter your domain (e.g., eid.kalemah.org)
# 3. Firebase gives you DNS records
# 4. Add those records in your domain registrar
# 5. Wait for SSL certificate (usually <1 hour)
```

**Adding More Pages:**

```
project-folder/
├── index.html           (homepage / eid25 page)
├── faq.html             (FAQ page)
├── about.html           (About page)
├── events.html          (Events page)
├── README.md            (this file)
└── firebase.json        (auto-generated config)
```

Then just `firebase deploy` again.

### 7.2 Pushing to GitHub (Step by Step from VS Code)

**First Time Setup:**

```bash
# 1. Open VS Code terminal (Ctrl + ` or Cmd + `)
#    Make sure you're in your project folder

cd kalemah-site

# 2. Initialize git
git init

# 3. Add all files
git add .

# 4. First commit
git commit -m "Initial commit: Kalemah Eid 2025 site"
```

**Create GitHub Repo:**

1. Go to **github.com** → Click **+** (top right) → **New repository**
2. Name it: `kalemah-eid` (or whatever you prefer)
3. Set to **Public** or **Private**
4. Do NOT check "Add README" (you already have one)
5. Click **Create repository**
6. GitHub shows you commands — copy the ones below:

```bash
# 5. Connect your local folder to GitHub
git remote add origin https://github.com/YOUR_USERNAME/kalemah-eid.git

# 6. Push everything
git branch -M main
git push -u origin main
```

**Every time you make changes after that:**

```bash
git add .
git commit -m "Updated event date and FAQ section"
git push
```

That's it — 3 commands every time you update.

**Using VS Code Git UI (no terminal needed):**

1. Click the **Source Control** icon in the left sidebar (branch icon)
2. You'll see all changed files listed
3. Click **+** next to each file (or **+** at top to stage all)
4. Type a commit message like "Updated hero section content"
5. Click the **✓ Commit** button
6. Click **Sync Changes** (or the cloud/push icon)

**If GitHub asks for authentication:**

```bash
# Option A: Use GitHub CLI (recommended)
# Install from https://cli.github.com
gh auth login
# Follow prompts → Browser → Authorize

# Option B: Personal Access Token
# github.com → Settings → Developer settings → Personal access tokens → Generate
# Use the token as your password when git asks
```

### 7.3 GitHub Pages (Free Hosting from GitHub)

Once your code is on GitHub, you can host it for free:

1. Go to your repo on GitHub
2. Click **Settings** tab
3. Scroll to **Pages** in the left sidebar
4. Under **Source**: select **Deploy from a branch**
5. Branch: **main** / Folder: **/ (root)**
6. Click **Save**
7. Wait 1-2 minutes
8. Your site is live at: `https://YOUR_USERNAME.github.io/kalemah-eid/`

**Adding a custom domain on GitHub Pages:**

1. In the same **Settings → Pages** section
2. Under **Custom domain**, type your domain (e.g. `eid.kalemah.org`)
3. Click **Save**
4. Add these DNS records at your domain registrar:

```
Type    Name    Value
A       @       185.199.108.153
A       @       185.199.109.153
A       @       185.199.110.153
A       @       185.199.111.153
CNAME   www     YOUR_USERNAME.github.io
```

5. Check **Enforce HTTPS** once DNS propagates (~30 min)

### 7.4 Firebase Hosting (Google)

- Drag and drop your folder at app.netlify.com
- Instant deploy with free SSL
- Custom domain support
- Good for simple static sites

### 7.4 Alternative: Cloudflare Pages (Free)

- Connect GitHub repo
- Auto-deploys on push
- Excellent global CDN performance
- Free custom domain with Cloudflare DNS

---

## 8. Multi-Page Site Structure (Future)

When you need multiple pages, ask Claude Code:

```
Create a shared header and footer as separate files that I can 
include across pages, following the brand guide in README.md
```

For a full multi-page site, consider migrating to a static site generator:

| Tool | Complexity | Best For |
|------|-----------|----------|
| Plain HTML files | Simple | 1-5 pages, current setup |
| Eleventy (11ty) | Low | 5-20 pages, templating |
| Astro | Medium | Modern site with components |
| Next.js (static export) | Higher | Full web app with dynamic features |

Claude Code can help you migrate when ready.

---

## 9. Quick Reference

### Key URLs
- Site: https://www.kalemah.org
- Eid Event: https://www.kalemah.org/eid25/
- FAQ: https://www.kalemah.org/FAQeid25/
- Instagram: @kalemah_institute (Dubai, UAE)

### Key Brand Hex Codes (copy-paste)
```
Cream:      #F5EDDE
Gold:       #D4A95A
Teal:       #344955
Teal Dark:  #2A3B45
Text Muted: #6B7B83
```

### Contact Info (from brand PDF)
- Phone: +971 22 341 6532
- Web: www.kalemah.org
- Location: Dubai, UAE (Est. 2007)

---

## 10. Changelog

### 2026-03-14 — Major Content & Design Update

**Content updates (based on final poster):**
- Date changed from "March 30, 2025" to "1st Shawwal, 2026"
- Salah time updated to 06:20 AM (from 6:15 AM)
- Gates open time updated to 5:45 AM (from 5:30 AM)
- Timeline adjusted: 5:45 AM gates, 6:05 AM takbeeraat, 6:20 AM salah, 6:40 AM khutba, 7:15 AM departure
- Venue changed from "Shabab Al Ahli Club, Al Nahda" to "Shabab Al Ahli Stadium, Next to Al Mulla Plaza & Stadium Metro, Dubai"
- Registration URL changed from `kalemah.org/eid25/` to `eidwithkalemah.com`
- Organization name updated to "Kalemah Islamic Centre"
- Added Permit No: 007260792
- Hero card redesigned: shows "DATE" heading, "1st Shawwal", "2026", gates open info below salah time
- FAQ answers updated with new times, venue name, and location details

**Design changes:**
- Nav: removed About/Schedule/Location/FAQ links, kept only "Register Now" button
- Nav logo enlarged from 42px to 52px
- Advisory banner made sticky with nav positioned below it dynamically
- Banner-hero spacing reduced (hero-content top padding 140px → 100px)
- Detail cards: "Modified Arrangements" card moved to first position (announcement priority)
- Detail cards: fixed animation/border conflict by separating `transition` properties on `.reveal` and `.detail-card`
- Venue Partner section: replaced large base64 logo with external `Accred.png` file, redesigned as compact horizontal card layout
- Added permit number below venue partner section
- Footer: removed navigation links (Home, About Us, Events, FAQ, www.kalemah.org)

---

*Document generated from design session. All brand assets extracted from Kalemah_Brand_Identity_compressed.pdf and Kalemah_Logo.pdf.*

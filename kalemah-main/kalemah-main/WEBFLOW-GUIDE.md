# Webflow Migration Guide — Eid Salah with Kalemah

## 1. Design System (Color Variables)

| Token | Hex | Usage |
|-------|-----|-------|
| cream | #F5EDDE | Primary background |
| cream-light | #FAF6EE | Section backgrounds, card backgrounds |
| gold | #D4A95A | Accent, CTAs, icons, badges |
| gold-light | #E8C97D | Light accents, highlights |
| gold-dark | #B8903F | Hover states, banner gradient |
| teal | #344955 | Primary dark, headings, hero card |
| teal-light | #3E5A68 | Hover states |
| teal-dark | #2A3B45 | Footer background |
| text-dark | #2B3A42 | Body text |
| text-muted | #6B7B83 | Secondary text |

---

## 2. Typography

| Role | Font | Weights | Usage |
|------|------|---------|-------|
| Headings | Cormorant Garamond | 300, 400, 600, 700 | Section titles, hero title, card date, logo text |
| Body/UI | Outfit | 300, 400, 500, 600, 700 | Body text, buttons, labels, nav |

**Key Sizes:**
- Hero title: clamp(2.8rem, 5vw, 4.2rem), line-height: 1.15
- Section label: 0.72rem, letter-spacing: 3px, uppercase, color: gold
- Section title: clamp(2rem, 3.5vw, 2.8rem), line-height: 1.25
- Body text: 1.05rem, line-height: 1.75
- Card heading: 1.35rem (Cormorant Garamond)
- Card body: 0.9rem, line-height: 1.65

---

## 3. Page Sections (Build Order)

### 3.1 Advisory Banner (Sticky)
- **Position:** Sticky, top: 0, z-index: 200
- **Background:** linear-gradient(135deg, #b8903f, #d4a95a)
- **Padding:** 14px 40px
- **Text:** white, centered, 0.88rem
- **Title:** "Event Status Advisory" (bold, 1rem)
- **Body:** "Please note that the event might be canceled on short notice due to updated regulations. Please follow official UAE channels for the latest updates."
- **Close button:** absolute right, × symbol

### 3.2 Navigation
- **Position:** Fixed, below banner (use JS to calculate top offset)
- **Default:** transparent background, padding: 16px 40px
- **Scrolled (scrollY > 50):** background: rgba(245,237,222,0.95), backdrop-filter: blur(20px), shadow: 0 2px 30px rgba(52,73,85,0.06), padding: 10px 40px
- **Logo:** 52px image + "KALEMAH" text (Cormorant Garamond, 1.35rem, letter-spacing: 3px, uppercase)
- **Only nav item:** "Register Now" button (teal background, cream text, padding: 10px 24px, border-radius: 100px)

### 3.3 Hero Section
- **Background:** linear-gradient(135deg, #F5EDDE 0%, #FAF6EE 50%, #f0e6d0 100%)
- **Min-height:** 100vh
- **Layout:** 2-column grid (1.1fr 0.9fr), gap: 80px, max-width: 1200px centered
- **Padding:** 100px 40px 80px

**Left Column:**
- Tag badge: "KALEMAH EXCLUSIVE EVENT" (teal bg, gold text, pill shape, 0.75rem)
- Title: "Eid Salah" + "With Kalemah" (bold, block)
- Arabic: "صلاة العيد مع كلمة" (1.6rem, gold, RTL)
- Description: "Kalemah Islamic Centre in association with Shabab Al Ahli Club invites you and your family for a joy-filled morning with Eid Salah and Khutba in English at Shabab Al Ahli Stadium, Dubai. This event is free for all."
- Buttons: "Register Now" (gold) + "View Location" (outline teal)

**Right Column — Event Card:**
- Background: #344955 (teal), border-radius: 24px, padding: 48px 40px
- Shadow: 0 30px 60px rgba(52,73,85,0.2)
- "Entry Free" badge: absolute top-right, 90px gold circle, float animation
- DATE label (small, uppercase, muted)
- "1st Shawwal" (large, Cormorant Garamond, gold — hero-card-month style ~2.8rem)
- "2026" (small, muted)
- Gold divider line (60px × 2px)
- **Salah Time:** 06:20 AM + "Gates Open at 5:45 AM" (smaller, muted)
- **Venue:** Shabab Al Ahli Stadium, Next to Al Mulla Plaza & Stadium Metro, Dubai
- **Khutba:** In English

### 3.4 Details Section ("What To Expect")
- **Background:** white (#fff)
- **Padding:** 100px 40px
- **Grid:** 3 columns (1fr 1fr 1fr), gap: 28px

**Cards (order matters):**

1. **Modified Arrangements** (HIGHLIGHTED — gold left border 3px, gold gradient icon bg)
   - Icon: info circle (⚠)
   - "This year, to ensure a safe and smooth gathering, we will not have children's activities or food stalls. We highly discourage bringing kids below 10 years of age."

2. **Eid Salah & Khutba**
   - Icon: mosque/house
   - "Join the community for Eid prayer followed by an inspiring khutba delivered entirely in English, making it accessible for everyone."

3. **Community Gathering**
   - Icon: people group
   - "An inclusive celebration welcoming attendees of all backgrounds. Come together to share in the joy and blessings of Eid."

4. **Parking Available**
   - Icon: parking grid
   - "Parking is available at the club. We recommend dropping off family at the main entrance before parking your vehicle."

**Card Style:**
- Background: #FAF6EE, border-radius: 16px, padding: 36px 32px
- Icon box: 56px, gold gradient bg, border-radius: 14px, margin-bottom: 20px
- Hover: translateY(-4px), shadow: 0 16px 40px rgba(52,73,85,0.08)

### 3.5 Highlights Section
- **Background:** teal with pattern overlay
- YouTube video embed (16:9 responsive)

### 3.6 Schedule Section
- **Label:** "Morning Schedule"
- **Title:** "Plan your Eid morning"
- **Horizontal timeline** with gold dot markers:

| Time | Event |
|------|-------|
| 5:45 AM | Gates Open |
| 6:05 AM | Takbeeraat Begin |
| 6:20 AM | Eid Salah |
| 6:40 AM | Khutba in English |
| 7:15 AM | Greetings & Departure |

### 3.7 Location Section
- Google Maps embed
- **Venue:** Shabab Al Ahli Stadium
- **Address:** Next to Al Mulla Plaza & Stadium Metro, Dubai
- 3 tip boxes: Getting There, Parking, What to Bring

### 3.8 Venue Partner Section
- **Padding:** 40px 40px 48px (compact)
- **Label:** "In Association With"
- **Title:** "Venue Partner"
- **Card:** horizontal flex layout (logo 80px + text), cream bg, rounded, subtle border
- **Partner:** Shabab Al Ahli Club — Next to Al Mulla Plaza & Stadium Metro, Dubai
- **Permit:** PERMIT NO: 007260792

### 3.9 FAQ Section (14 items)

| # | Question | Answer |
|---|----------|--------|
| 1 | Is the Eid Salah only for men? | No, the Eid Salah is for the whole family. |
| 2 | What time will the Salah start? | Gates open at 5:45 AM. Salah will start at 6:20 AM followed by the Khutba in English. |
| 3 | Where is Shabab Al Ahli Club located? | Shabab Al Ahli Stadium is located next to Al Mulla Plaza & Stadium Metro, Dubai. The Salah will be held at the grounds inside the stadium. |
| 4 | Will the Salah be held in the main stadium? | No, the Eid Salah will be held at one of the smaller grounds inside the stadium. |
| 5 | How can I reach there if I don't drive? | You can take a taxi — if you plan on taking a taxi, we advise you to plan and leave in advance as getting a taxi early in the morning might be difficult. The closest metro station is Stadium Metro Station, which is approximately a 15-minute walk to the prayer area. Please check official RTA channels on the start time of the metro during Eid. |
| 6 | Can I come if I haven't registered? | Yes, but we recommend you register yourself and your family so that we can plan better. |
| 7 | Is there a masjid where I can pray Fajr nearby? | There is only one masjid which is located near the main entrance of the club. |
| 8 | Where can I park? Is there ample parking space? | Yes, there are multiple parking areas available. We recommend coming early and parking in the main parking area as it has the shortest walking distance. Our volunteers will be present at all entrances to guide you towards the closest parking space. We also advise avoiding parking beside Lulu Hypermarket as there are no entrances in that area. |
| 9 | Will I have to walk a lot from parking to the Salah area? | We recommend you drop off the family and elderly at the main parking entrance and proceed to park your car. |
| 10 | Is the prayer area accessible by wheelchair? | Sorry, wheelchair access is very limited from the main parking area to the prayer ground. We sincerely apologize for the inconvenience. |
| 11 | Will there be toilets and is there an option to make wudu? | Access to toilets might be limited and these toilets will be reserved for women and children. We recommend that you make wudu from home. |
| 12 | Should I bring prayer mats & chairs? | Yes, please bring your own prayer mats. We have chairs but they are limited. We recommend you bring your own. |
| 13 | Won't it be too hot? | Morning hours will be cooler but do expect it to be a bit humid. |
| 14 | What time will the event finish? | The Salah and Khutba will be done by around 7:15 AM. |

### 3.10 CTA Section
- **Background:** gold gradient + pattern
- **Title:** "Don't miss this blessed gathering"
- **Desc:** "Celebrate Eid Al Fitr with the community. Free entry and a blessed morning of prayer and togetherness."
- **Button:** "Register Now" (white bg, teal text) → https://www.eidwithkalemah.com

### 3.11 Footer
- **Background:** #2A3B45 (teal-dark) + pattern
- Logo + "KALEMAH" + "مركز كلمة · Islamic Center · Est. 2007"
- Copyright: "© 2026 Kalemah Islamic Center. All rights reserved. Dubai, UAE."

---

## 4. Animations (Webflow Interactions)

| Animation | Trigger | Properties | Duration |
|-----------|---------|------------|----------|
| Scroll Reveal | Element enters viewport | opacity: 0→1, translateY: 30px→0 | 0.7s ease |
| Hero Slide Up | Page load | opacity: 0→1, translateY: 20px→0 | 0.8s ease, staggered 0.15s |
| Float Badge | Continuous | translateY: 0 → -8px → 0 | 3s ease-in-out infinite |
| Logo Breathe | Continuous | scale: 1 → 1.04 → 1 | 8s ease-in-out infinite |
| Button Hover | Hover | translateY: -2px, shadow increase | 0.3s ease |
| FAQ Toggle | Click | max-height: 0 → auto, icon rotate 45deg | 0.3s ease |

---

## 5. Button Styles Reference

| Button | Background | Text Color | Padding | Border | Hover |
|--------|-----------|------------|---------|--------|-------|
| Primary | #D4A95A | #fff | 16px 36px | none | bg: #B8903F, translateY(-2px) |
| Secondary | transparent | #344955 | 16px 36px | 2px solid #344955 | bg: #344955, text: #F5EDDE |
| White | #fff | #344955 | 16px 36px | none | translateY(-2px), shadow |
| Nav CTA | #344955 | #F5EDDE | 10px 24px | none | bg: #3E5A68 |

All buttons: border-radius: 100px, font-size: 0.9rem, font-weight: 600, letter-spacing: 1px

---

## 6. Responsive Breakpoints

| Breakpoint | Key Changes |
|------------|-------------|
| ≤ 1024px | Hero grid → 1 column, details grid → 2 columns |
| ≤ 768px | Section padding → 60px 24px, hero padding → 120px 24px 60px, details grid → 1 column, timeline → vertical, nav → hamburger menu |

---

## 7. Assets Needed

- Kalemah logo (PNG, transparent) — extract from current base64 or use source PDF
- Accred.png — Shabab Al Ahli Club logo (already in project folder)
- Islamic geometric patterns (4 variants) — extract from base64 or use source PDFs
- Google Fonts: Cormorant Garamond + Outfit

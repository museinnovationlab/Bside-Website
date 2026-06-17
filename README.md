# B-Side — Marketing landing site

Static, dependency-free site (HTML + one CSS file). Faithful to the v3 paper/ink/riveted-plate
design system. No build step, no external image assets (logo + phone mockup + grain are all CSS/SVG).

## Files
- `index.html` — landing page (hero, how-it-works, features, pitch, FAQ, waitlist CTA, footer)
- `privacy.html` — Privacy Policy (first-draft template)
- `terms.html` — Terms of Service (first-draft template)
- `styles.css` — shared styles + design tokens

## Preview locally
Just open `index.html` in a browser, or serve the folder:
```
cd "/Users/thugs/My Drive/Work/Side Things/Vibe Code Projects/Berkeley Labs/Bside/Developer Files/landing" && python3 -m http.server 4321
```
Then visit http://localhost:4321

## Deploy
Any static host works (Vercel, Netlify, Cloudflare Pages, GitHub Pages, Firebase Hosting).
Firebase Hosting is the natural fit since the app already lives in the `bside-1e8b9` project:
```
cd "/Users/thugs/My Drive/Work/Side Things/Vibe Code Projects/Berkeley Labs/Bside/Developer Files/landing" && firebase init hosting   # point public dir at this folder, single-page = No
firebase deploy --only hosting
```

## Before going live — fill these in
Search for `[` (bracketed placeholders) and the `.placeholder` spans:

**Copy / brand**
- Hero, features, and FAQ copy — refine voice; the structure is final, words are first-draft.
- Pricing (FAQ "What does it cost?" + Terms §4) — trial length + monthly/annual price.
- Contact email — currently `hello@bside.app` / `privacy@bside.app` placeholders. Set the real domain/inbox.

**Legal (have a lawyer review both pages)**
- Legal entity name + mailing address (currently "Berkeley Labs" placeholder)
- Effective dates
- Governing law / jurisdiction + dispute-resolution choice (Terms §13)
- Minimum age (13/16/18), data-retention period, applicable privacy frameworks (GDPR/CCPA)
- Confirm the analytics/payments vendors named (PostHog, Sentry, RevenueCat, Firebase)

**Functional**
- Waitlist form in `index.html` is currently **inert** (just clears + shows a thank-you). Wire it to
  your email provider (Mailchimp / ConvertKit / a Firebase callable) before collecting signups.
- Add real `og:image` + favicon when brand assets are ready (intentionally omitted — no random images).
- Update the App Store / Play badges + links once the app is live (not yet added).

## Notes
- The "Draft for review" yellow banner on the legal pages should be **removed** once a lawyer signs off.
- Mobile-responsive (single-column under 860px; nav links collapse — consider a hamburger if you add more).

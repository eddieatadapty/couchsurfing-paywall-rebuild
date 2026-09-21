# Couchsurfing — onboarding & paywall rebuild

A clickable HTML prototype: a new onboarding sequence in front of Couchsurfing's
membership paywall, the paywall rebuilt in its own design system, and an offer
paywall on close.

**Open `index.html` in any browser.** One self-contained file — no build step, no
server required. Two tabs: the clickable prototype with a per-screen rationale
panel, and a before/after sequence with the ranked change table.

> **Unaffiliated concept work.** Couchsurfing is a trademark of CouchSurfing
> International, Inc. This prototype is not produced or endorsed by, nor affiliated
> with, Couchsurfing or any publication shown. It reproduces brand assets (hero
> photograph, app icon) and press wordmarks from publicly available material for the
> sole purpose of demonstrating a redesign in the app's own visual language. All
> trademarks and images remain the property of their respective owners. Removal
> requests: open an issue.

---

## What this is

The brief was to increase conversion **without touching the art direction**. So the
design system was extracted from a screen capture of the live app before anything
was drawn, and only the *sequence* changed.

### Extracted from the capture, and kept

| Element | Kept as-is |
| --- | --- |
| Ground / surface | `#100B11` plum-black, cards `#16121A`, footer rail `#1B171E` |
| Accent gradient | `#C0763C → #B7407E → #AE2A92`, on the CTA **and** the POPULAR ribbon |
| Type | Source-Serif-class for headings **and prices**; grotesque for labels and body |
| Laurel ornament | Redrawn as SVG, flanking headings |
| Plan picker | The **horizontal rail** — their control, not a vertical stack |
| POPULAR ribbon | Full-width card cap; gradient-filled only when that card is selected |
| Selected state | Amber `#C98A4E` border |
| Close button | Rounded **square**, top-left |
| Press logo tiles | The two legible in the capture's strip |
| Footer chrome | Price rail → CTA → Not Now → legal → restore, verbatim |

The paywall CTA sits in a `.dock` that is a flex **sibling** of the scroll area —
no sticky bar over content, no negative margins.

---

## The flow

| # | Screen | Tag | Consumed by |
| --- | --- | --- | --- |
| 1 | Welcome & proof | NEW | — |
| 2 | Q1 Destination | NEW | loader, payoff, paywall title, offer |
| 3 | Q2 Trip window | NEW | plan pre-selection, paywall sub-line |
| 4 | Q3 What they want | NEW | paywall benefit row order + tag |
| 5 | Q4 Travel party | NEW | loader line, payoff chip |
| 6 | Q5 What earns a yes | NEW | offer paywall's second line |
| 7 | Loader | NEW | shows all five answers being consumed |
| 8 | Payoff | NEW | published host count for the chosen city |
| 9 | Membership paywall | KEPT | — |
| 10 | Offer paywall on close | NEW | fires on ✕ **and** "Not Now" |
| 11 | Location + sign-up | MOVED | — |

**Scope note:** the capture is one screen — the paywall. It contains no onboarding,
so there were no existing questions to keep or cut. The five questions are net-new.
The "before" column in the prototype labels each step as observed or inferred.

---

## Ranked changes

| # | Priority | Pattern | Expected impact |
| --- | --- | --- | --- |
| 1 | Fix first | Personalization loop | CR +10–20% · ARPU +13–35% |
| 2 | Fix first | Social proof at decision point | CR +10–15% · ARPU +2–5% |
| 3 | High | Goal-personalized paywall | CR +15–20% |
| 4 | High | Plan visual hierarchy | CR +5–15% · ARPU +3–8% |
| 5 | High | Second-chance offer | ARPU +10–15% |
| 6 | Medium | Annual savings visualization | CR +5–15% · ARPU +10–15% |
| 7 | Medium | Permissions timing · registration friction | CR +10–15% · CR +8%, ARPU +17% |
| 8 | Medium | Trust signals near CTA | CR +3–8% |

*Patterns are drawn from Adapty's teardowns of top apps across numerous verticals;
impact ranges are expected effect, not measured lift for this app.*

---

## Grounding

Every price, rating, quote and partnership is Couchsurfing's own published material.
Nothing on these screens is invented.

- **Prices & SKUs** — App Store in-app purchase list, *Couchsurfing: Stay, Meet, Host*
  (`id525642917`): Monthly $4.99 · Quarterly $9.99 · Annual $19.99 · **Annual $13.99** ·
  Annual Verification $29.99. **No trial SKU listed anywhere.**
- **Rating** — 4.5 from 9,318 ratings, pulled live from Apple's lookup API (18 Sep 2026).
- **"Over 12 million travel enthusiasts … more than 230,000 cities"** — the app's own
  App Store description.
- **Host counts** — couchsurfing.com: Paris 493k · Bogotá 153k · Dubai 126k.
- **"Save 67%"** and all footer/legal copy — the captured paywall itself.
  ($19.99 ÷ $4.99×12 = 33.4%, so their badge is arithmetically correct on the US ladder too.)
- **Quotes** — verbatim 5-star App Store reviews by *adri.lifestyle* and *ByCindyg*.
- **Press logos** — the two legible in the captured strip.

### The offer paywall SKU

There is no trial to offer, and the app's categories (Travel, Lifestyle) are a vertical
where trials measurably *hurt* LTV. So the offer paywall uses **Annual Contribution
$13.99** — a real published SKU sitting beside the $19.99 annual, exactly 30% less. The
strikethrough is therefore between two prices Apple already lists, not an inflated
reference price.

---

## What was deliberately not built

1. **A free-vs-paid comparison table** — the highest-impact pattern available, and the
   first thing a generic rebuild reaches for. Couchsurfing has a free tier but its limits
   are not published anywhere verifiable, and a comparison table with guessed limits is a
   fabricated claim. **This is the biggest upside still on the table.**
2. **A free trial / trial timeline** — no trial SKU exists, and the category evidence says
   trials would hurt here.
3. **A countdown timer on the main paywall** — timers belong on paywalls that already carry
   a discount. It appears only on the offer paywall, where the 30% is real.
4. **More press logos** — the capture's strip was mid-scroll; only two are verifiable.
5. **Invented testimonials** — both quotes are real reviews with real authors.

## Open questions

1. The **real free-tier limits** — unlocks the comparison table.
2. Whether **Annual Contribution $13.99** is a live win-back/regional SKU or a legacy price.
3. Published **host counts for Toronto, Osaka and New York** — the rest fall back to the
   global figure.
4. Whether **Annual Verification $29.99** belongs in this flow at all. It is a real SKU and
   a recurring complaint in the reviews; it was kept out rather than stacking a second ask.

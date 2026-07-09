# BuildView 3D Pro 🏗️

**Show clients what you'll build — before you build it.**

Now packaged as a **monthly subscription product**: the app is locked behind a
license key, there's a sales page to send prospects to, and a private key
generator you use to issue keys to paying subscribers. See
[💰 Selling it](#-selling-it-as-a-subscription) below.

A simple tool for contractors: type in the measurements and a plain-English
description of what the client wants, and get an interactive 3D preview with
**two versions** to present:

- **Standard** — the build as described, priced from your base rate
- **⭐ Upgraded** — the same project with premium materials and extras, for a
  little more

## How to use it

1. Open `index.html` in any browser (double-click it — no install, no internet
   needed once you have the two files).
2. Pick what you're building — 25 job types, grouped big-to-small:
   - **Structures:** Room Addition, Sunroom, Garage, Pole Barn, Shed
   - **Outdoor Living:** Deck, Covered Porch, Patio, Pergola, Gazebo, Carport
   - **Groundwork:** Driveway, Walkway, Retaining Wall, Fence
   - **Small Projects:** Exterior Stairs, Wheelchair Ramp, Raised Garden Beds
   - **Cabinetry & Custom:** Kitchen Cabinets, Built-in Shelving, Armoire/Wardrobe,
     Custom Desk, Bathroom Vanity, Workbench, and a flexible **Custom Build**
3. Enter the measurements in feet.
4. Describe the job in plain words — the app automatically picks up things like
   *stairs, railing, lighting, pergola, fire pit, gate, bench, hot tub,
   skylight* and adds them to the 3D model and the price.
5. Hit **Generate 3D Preview**, then flip between **Standard** and
   **⭐ Upgraded** while the client watches.

### Showing the client

- **Drag** to spin the model, **scroll / pinch** to zoom — works on phones and
  tablets.
- **📷 Photo** saves a picture you can text to the client.
- **🔄 Spin** turns on a slow auto-rotate for a hands-free demo.
- **🖨️ Print for client** makes a one-page summary with the 3D picture and a
  side-by-side price comparison of both options.

### Pricing

Set **your own base rate** in the sidebar — the unit adapts to the job ($/sq ft,
$/linear ft for fences and ramps, $/face sq ft for retaining walls), and a typical
figure is pre-filled for each project type. The upgraded option and any extras
price themselves from that. Estimates show as a range and are for planning only —
not a quote.

## Files

| File | What it is |
|---|---|
| `index.html` | The app — UI, 3D builders, pricing, **license lock** |
| `three.min.js` | Three.js r128 (bundled locally so the app works offline) |
| `buy.html` | Sales page — features, pricing, subscribe buttons, FAQ |
| `keygen.html` | 🔒 **NOT in this repo — stored locally only.** Your license key generator lives on your own computer, so it can never end up on a public website. It's gitignored so it won't be committed by accident. |

No build step, no dependencies, no server.

---

## 💰 Selling it as a subscription

The whole business runs on three pieces:

1. **`buy.html`** — the page prospects see. It pitches the product at
   **$29/month or $290/year** (edit the numbers right in the file if you want
   different pricing).
2. **`index.html`** — the app itself, locked. It asks for an email + license
   key on first open, remembers it, and **locks itself again the day the key
   expires**. Works fully offline after that first unlock.
3. **`keygen.html`** — your tool. When someone pays, open it, type their email,
   pick the plan, and it spits out their key **plus a ready-to-send welcome
   email**. Takes 30 seconds per customer.

### One-time setup (do these before your first sale)

1. **Change the secret.** In both `index.html` and your local copy of
   `keygen.html` find the line
   `var SALT = "change-me-to-something-random-BV3"` and change it to your own
   random gibberish — **the same string in both files**. This is what makes
   your keys forgery-proof-enough. (`keygen.html` isn't in this repo — it's
   stored only on your own computer, and gitignored so it stays that way.)
2. **Set up payments.** In [Stripe](https://stripe.com): Products → Add product
   → "BuildView 3D Pro", recurring, $29/month — then create a **Payment Link**
   for it. Do the same for a $290/year price. Paste the two links into the
   marked spot at the bottom of `buy.html` (`STRIPE_MONTHLY` / `STRIPE_ANNUAL`).
   *Until you do this, the subscribe buttons fall back to sending you an email
   order instead — so you can start selling today and add Stripe later.*
3. **Put it online.** Host `index.html`, `three.min.js` and `buy.html` anywhere
   static — GitHub Pages, Netlify, Vercel (all free). Send prospects the
   `buy.html` link. The app being public is fine — it's locked. `keygen.html`
   stays on your computer and never goes online.

### Day-to-day

- **New subscriber** (Stripe emails you on every payment): open `keygen.html`,
  enter their email, pick Monthly/Annual, copy the welcome email, send it. Done.
- **Renewal**: when the next payment comes in, generate a fresh key for the
  same email and send it.
- **Cancellation**: do nothing. No new key → the app locks itself when the old
  one runs out.
- **Trial requests**: generate a 7-day key. No card, no risk — it expires on
  its own.

### Honest fine print

The lock is a strong deterrent, not bank-vault DRM — this is a client-side app,
so a determined nerd could pry it open. For selling to contractors at $29/mo,
that's the right trade-off: zero servers, zero hosting costs, works offline,
and honest customers stay honest.

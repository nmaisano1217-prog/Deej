# BuildView 3D 🏗️

**Show clients what you'll build — before you build it.**

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
| `index.html` | The whole app — UI, 3D builders, pricing |
| `three.min.js` | Three.js r128 (bundled locally so the app works offline) |

No build step, no dependencies, no server. Copy both files onto a laptop,
tablet, or USB stick and it just works.

# Bundle Box Builder Section

Let customers build their own bundle box from your collections, unlock tiered quantity discounts, and add the whole bundle to the cart in one click — no paid bundle app required.

## Overview

The **Bundle box builder** section renders a tabbed product picker (up to three collections) alongside a live bundle widget. Shoppers add products into bundle slots, the widget tracks how many items are selected, highlights the discount tier they've reached, and shows the original price, savings, and final price in real time. One click adds every selected variant to the cart.

## Features

- Tabbed browsing across up to 3 collections
- Visual bundle slots that fill as products are added
- Three configurable discount tiers (item count + % off)
- Live price summary: original price, discount amount, final price
- Per-product variant dropdown with sold-out variants disabled
- Remove items from the bundle before checkout
- Adds all bundle items to `/cart/add.js` in a single request with `_bundle` line item properties
- Fully customizable colors, typography, spacing, border radius, and shadows from the theme customizer
- Scoped CSS/JS per section instance — safe to place more than once on a page
- Responsive layout for desktop, tablet, and mobile
- Works with any Shopify theme (free or paid), no app required

## Video Tutorial

[![Shopify Bundle Builder Tutorial](https://img.youtube.com/vi/QWzo0WdBOkU/0.jpg)](https://youtu.be/QWzo0WdBOkU)

> Watch the full step-by-step setup: https://youtu.be/QWzo0WdBOkU

## Getting Started

1. Copy `bundle-buider.liquid` into your theme's `sections/` directory
2. Go to **Online Store → Themes → Customize** in your Shopify admin
3. Open the page where you want the bundle builder (home page or a custom page template)
4. Click **Add section** and choose **Bundle box builder**
5. Pick up to 3 collections under the **Collections** settings group
6. Set your discount tiers, then **Save**

## Settings

| Group | What you can configure |
| --- | --- |
| **Collections** | Collection 1, 2, and 3 shown as tabs |
| **Bundle widget** | Widget title and subtitle |
| **Discount tiers** | Name, product count (2–12), and discount (0–50%) for each of the 3 tiers |
| **Layout** | Max width, top/bottom padding, grid gap, card minimum width |
| **Colors** | Section, card, and widget backgrounds; primary/secondary text; accent, border, tab, and vendor colors |
| **Buttons** | Add button, checkout button, and remove button colors (including hover) |
| **Badges** | Sale badge, discount badge, and active tier background colors |
| **Typography** | Widget title/subtitle, product title, price, button, and tab font sizes |
| **Border radius** | Card, widget, button, input, slot, and tier radius |
| **Shadows** | Card and widget shadow presets (None / Light / Medium / Strong) |

The largest tier's product count sets the number of bundle slots displayed.

## Applying the Discount at Checkout

The section adds each bundle item to the cart at its normal price and tags it with line item properties:

- `_bundle` — bundle name
- `_bundle_discount` — the tier discount percentage reached
- `_original_price` / `_discounted_price`

The tiered discount shown in the widget is a **storefront preview**. To charge the discounted total, pair the section with a Shopify discount that matches your tiers — for example an automatic quantity/volume discount, or a [Shopify Discount Function](https://shopify.dev/docs/api/functions/reference/product-discounts) that reads the `_bundle` property. Set your discount rules to mirror the tier counts and percentages configured in the section so cart totals match what shoppers see.

## Notes

- Products must be published to the **Online Store** sales channel to appear in the picker
- Sold-out products and variants are shown but cannot be added
- Each collection tab renders its products server-side, so very large collections are limited by Shopify's default pagination

## Resources

- [Shopify Theme Development Docs](https://shopify.dev/docs/themes)
- [Liquid Template Language Reference](https://shopify.dev/docs/api/liquid)
- [Shopify Section Schema](https://shopify.dev/docs/themes/architecture/sections/section-schema)
- [Cart AJAX API](https://shopify.dev/docs/api/ajax/reference/cart)

---
*Part of the [Free Shopify Sections](https://github.com/websensepro1/free-shopify-sections) collection.*

---
name: catalog-commerce
description: Set up product catalogs and product sets so ecom ads can pull live products (dynamic ads) instead of static images. Use for stores with more than a handful of SKUs, after the pixel is verified.
---

# Catalog & Commerce

## Doctrine
Commerce plumbing is unglamorous and decisive: dynamic product ads cannot run without a healthy catalog, and a catalog wired to a broken pixel just automates showing people the wrong products. Order matters: pixel first (see pixel-conversions), catalog second, product sets third. Product sets are angles for inventory: "best sellers", "under $50", "new arrivals" are different promises to different buyers.

## When to use
- Ecom stores with enough SKUs that per-product creative is impractical.
- Before any retargeting play that shows people what they browsed.
- Needs a Meta Ads MCP with write access; creation steps are confirmed before running.

## Run it

```
Catalog setup, step by step, confirm with me before each write:

1. List my existing catalogs and their product counts. If a catalog already exists, audit it instead of duplicating: how many products, how many rejected or missing images/prices?
2. Check the pixel link: is the catalog connected to my pixel, and are the product IDs in my purchase events matching catalog IDs? If not, stop and tell me; nothing downstream works until this does.
3. Propose 2-3 product sets that match my angles (for example: best sellers, entry-price items, the category my ads target). Show the filter logic.
4. On my approval, create the sets and tell me exactly which ad type they unlock (dynamic product ads, advantage+ catalog ads) and what a $20/day test on the best set would look like.
```

## Guardrails
- Audit before create: duplicate catalogs are how accounts end up advertising stale prices.
- The pixel-to-catalog ID match is a hard gate. Skipping it produces ads for out-of-stock products at wrong prices.
- Product sets mirror angles: a set nobody wrote an angle for is inventory, not a campaign.

## Good output looks like
One healthy catalog, 2-3 named product sets tied to angles, and a clear go/no-go on whether dynamic ads are ready to test.

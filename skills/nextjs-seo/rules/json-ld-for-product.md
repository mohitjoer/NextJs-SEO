---
title: JsonLdForProduct Reference
description: API Reference for the JsonLdForProduct component.
---

The `JsonLdForProduct` component renders Product JSON-LD structured data in a script tag.

## Props

The `JsonLdForProduct` component accepts the following props:

### `name` (required)

**type:** `string`

The name of the product.

### `image` (required)

**type:** `string | string[]`

The URL(s) of the product image.

### `description`

**type:** `string`

A description of the product.

### `sku`

**type:** `string`

The Stock Keeping Unit (SKU).

### `mpn`

**type:** `string`

The Manufacturer Part Number.

### `brand`

**type:** `{ name: string }`

The brand associated with the product.

### `review`

**type:** `Review`

A single review or an array of reviews.

### `aggregateRating`

**type:** `{ ratingValue: string; reviewCount?: string; ratingCount?: string }`

The aggregate rating of the product.

### `offers`

**type:** `Offer | Offer[]`

The offer(s) for the product.

### `scriptId`

**type:** `string`

A custom ID for the script tag.

### `scriptKey`

**type:** `string`

A custom React key for the script element.

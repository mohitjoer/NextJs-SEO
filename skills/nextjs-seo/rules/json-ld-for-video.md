---
title: JsonLdForVideo Reference
description: API Reference for the JsonLdForVideo component.
---

The `JsonLdForVideo` component renders VideoObject JSON-LD structured data in a script tag.

## Props

The `JsonLdForVideo` component accepts the following props:

### `name` (required)

**type:** `string`

The title of the video.

### `description` (required)

**type:** `string`

The description of the video.

### `thumbnailUrl` (required)

**type:** `string | string[]`

The URL(s) of the video thumbnail.

### `uploadDate` (required)

**type:** `Date | string`

The date the video was uploaded. Accepts a Date object or an ISO string.

### `contentUrl`

**type:** `string`

A URL pointing to the actual video media file.

### `embedUrl`

**type:** `string`

A URL pointing to a player for the specific video.

### `duration`

**type:** `string`

The duration of the video in ISO 8601 format (e.g., `PT1M33S`).

### `scriptId`

**type:** `string`

A custom ID for the script tag.

### `scriptKey`

**type:** `string`

A custom React key for the script element.

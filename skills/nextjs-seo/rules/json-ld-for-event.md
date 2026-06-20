---
title: JsonLdForEvent Reference
description: API Reference for the JsonLdForEvent component.
---

The `JsonLdForEvent` component renders Event JSON-LD structured data in a script tag.

## Props

The `JsonLdForEvent` component accepts the following props:

### `name` (required)

**type:** `string`

The name of the event.

### `startDate` (required)

**type:** `Date | string`

The start date and time of the event. Accepts a Date object or an ISO string.

### `endDate` (required)

**type:** `Date | string`

The end date and time of the event.

### `eventAttendanceMode`

**type:** `string`

The attendance mode (e.g., `https://schema.org/OnlineEventAttendanceMode`).

### `eventStatus`

**type:** `string`

The status of the event (e.g., `https://schema.org/EventScheduled`).

### `location`

**type:** `object`

The location of the event. Can be a `Place` or `VirtualLocation`.

### `scriptId`

**type:** `string`

A custom ID for the script tag.

### `scriptKey`

**type:** `string`

A custom React key for the script element.

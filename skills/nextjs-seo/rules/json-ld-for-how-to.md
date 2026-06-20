---
title: JsonLdForHowTo Reference
description: API Reference for the JsonLdForHowTo component.
---

The `JsonLdForHowTo` component renders HowTo JSON-LD structured data in a script tag.

## Props

The `JsonLdForHowTo` component accepts the following props:

### `name` (required)

**type:** `string`

The name of the How-To guide.

### `description` (required)

**type:** `string`

A description of the How-To guide.

### `step` (required)

**type:** `Array<{ name: string; text: string; image?: string; url?: string }>`

An array of steps required to complete the task.

### `scriptId`

**type:** `string`

A custom ID for the script tag.

### `scriptKey`

**type:** `string`

A custom React key for the script element.

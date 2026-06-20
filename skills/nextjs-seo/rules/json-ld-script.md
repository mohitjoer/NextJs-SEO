---
title: JsonLdScript Reference
description: API Reference for the JsonLdScript component.
---

The `JsonLdScript` component renders any JSON-LD structured data in a script tag.

## Props

The `JsonLdScript` component accepts the following props:

### `jsonLd` (required)

**type:** `T` (generic object type, defaults to `Record<string, unknown>`)

The JSON-LD structured data object to be rendered. This should be a valid JSON-LD object following the schema.org specification.

> [!TIP]
> **Type Safety**: To catch typos at compile time instead of failing silently in Google's Rich Results Test, we highly recommend installing the `schema-dts` package and typing your `jsonLd` object using its `Thing` or `WithContext<Thing>` types.

### `scriptId`

**type:** `string`

A custom ID for the script tag.

### `scriptKey`

**type:** `string`

A custom React key for the script element.

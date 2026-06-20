---
title: JsonLdForOrganization Reference
description: API Reference for the JsonLdForOrganization component.
---

The `JsonLdForOrganization` component renders Organization or LocalBusiness JSON-LD structured data in a script tag.

## Props

The `JsonLdForOrganization` component accepts the following props:

### `type` (required)

**type:** `"Organization" | "LocalBusiness" | "Corporation"`

The type of the organization.

### `name` (required)

**type:** `string`

The name of the organization.

### `url` (required)

**type:** `string`

The website URL of the organization.

### `logo`

**type:** `string`

The URL of the organization's logo.

### `contactPoint`

**type:** `Array<{ telephone: string; contactType: string }>`

Contact details for the organization.

### `scriptId`

**type:** `string`

A custom ID for the script tag.

### `scriptKey`

**type:** `string`

A custom React key for the script element.

---
title: Getting Started
description: Learn how to get started with nextjs-seo.
---

## Prerequisites

You will need to have a Next.js website set up. If you don't have one yet, you can follow the ["Installation"](https://nextjs.org/docs/app/getting-started/installation) guide in the Next.js docs to create one.

Additionally, your Next.js website must meet the following requirements:

- **App Router**
- **Next.js 15.0.0 or higher** (13.x–14.x are supported in legacy mode)
- **React 18.2.0 or higher** (React 19 recommended for Next.js 15+)

## Installation

1. Install the library via your preferred package manager:

   ```sh
   npm install @mohitjoer/nextjs-seo
   ```

   ```sh
   yarn add @mohitjoer/nextjs-seo
   ```

   ```sh
   pnpm add @mohitjoer/nextjs-seo
   ```

### Next.js 15/16 Explicit Caching

Next.js 15+ and 16 lean heavily into an explicit caching model (Cache Components / `"use cache"`). Be aware that if `genPageMetadata` or the `JsonLd` components fetch any data internally, they will adhere to the active caching boundaries. When using `"use cache"` or dynamic data fetching, make sure to read the Next.js caching documentation so your metadata doesn't serve stale data.

2. Create a `seo.config.ts` (or `seo.config.js` if not using TypeScript) file in the root of your project with the following content and replace it with your corresponding data:

   ```ts
   import { defineSeoConfig } from "@mohitjoer/nextjs-seo";

   export default defineSeoConfig({
     baseUrl: "https://example.com",
     siteName: "Example",
     defaultOgImg: "/default-og.png",
     manualRoutes: [],
   });
   ```

3. You're all set! Start using the library in your Next.js project.

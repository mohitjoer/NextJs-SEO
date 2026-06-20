---
title: Generate the robots.txt file for a site
description: Learn how to generate the robots.txt file for a site with nextjs-seo.
---

`nextjs-seo` can generate the `robots.txt` file for your Next.js site with automatic configuration.

## Enabling robots.txt generation

1. Create a `robots.ts` or `robots.js` file in your project's app folder.

2. Import the `robotsTxt` function into the file.

   ```ts
   // app/robots.ts
   import type { MetadataRoute } from "next";
   import { robotsTxt } from "@mohitjoer/nextjs-seo";

   export default function robots(): MetadataRoute.Robots {
     return robotsTxt();
   }
   ```

   ```js
   // app/robots.js
   import { robotsTxt } from "@mohitjoer/nextjs-seo";

   export default function robots() {
     return robotsTxt();
   }
   ```

3. Open http://localhost:3000/robots.txt in your browser to see the robots file.

> [!TIP]
> **Next.js Caching Behavior**: Route Handlers like `robots.ts` are cached by default in Next.js 15+ unless they use a request-time API or dynamic config options. If you pull rules from a database, be aware that the output will silently freeze unless you explicitly opt into dynamic behavior (e.g., `export const dynamic = 'force-dynamic'`).

## Advanced robots configuration

By default, `robotsTxt()` generates a `robots.txt` file with sensible default rules that work well for most cases.

However, you can customize the configuration by passing an options object to the function to extend or override these defaults.

The configuration allows you to specify custom rules, user agents, and crawl delays.

```ts
// app/robots.ts
import type { MetadataRoute } from "next";
import { robotsTxt } from "@mohitjoer/nextjs-seo";

export default function robots(): MetadataRoute.Robots {
  return robotsTxt({
    sitemap: "https://www.yourdomain.com/sitemap.xml",
    host: "https://www.yourdomain.com",
    rules: [
      {
        userAgent: "*",
        allow: "/",
        disallow: ["/admin", "/private"],
      },
      {
        userAgent: "Googlebot",
        allow: "/",
        crawlDelay: 10,
      },
    ],
  });
}
```

```js
// app/robots.js
import { robotsTxt } from "@mohitjoer/nextjs-seo";

export default function robots() {
  return robotsTxt({
    sitemap: "https://www.yourdomain.com/sitemap.xml",
    host: "https://www.yourdomain.com",
    rules: [
      {
        userAgent: "*",
        allow: "/",
        disallow: ["/admin", "/private"],
      },
      {
        userAgent: "Googlebot",
        allow: "/",
        crawlDelay: 10,
      },
    ],
  });
}
```



---
title: Add VideoObject JSON-LD structured data to a page
description: Learn how to add VideoObject JSON-LD structured data to a page using the JsonLdForVideo component from nextjs-seo.
---

`nextjs-seo` provides the `JsonLdForVideo` component to easily add VideoObject JSON-LD structured data to a page.

## Using the JsonLdForVideo component

1. Import the `JsonLdForVideo` component into every page where you want to generate the JSON-LD data.

   ```tsx
   // app/videos/nextjs-16-tutorial/page.tsx
   import { JsonLdForVideo } from "@mohitjoer/nextjs-seo";

   export default function VideoPage() {
     return (
       <>
         <JsonLdForVideo
           name="Next.js 16 Tutorial"
           description="Learn all the new features in Next.js 16."
           thumbnailUrl={["https://mohitjoe.xyz/thumbnails/nextjs16.jpg"]}
           uploadDate="2026-03-01T08:00:00Z"
           contentUrl="https://example.com/videos/nextjs16.mp4"
           embedUrl="https://example.com/embed/nextjs16"
           duration="PT15M33S"
           scriptKey="video-json-ld"
         />
         <main>
           <h1>Next.js 16 Tutorial</h1>
           {/* Your content */}
         </main>
       </>
     );
   }
   ```

2. Check the generated JSON-LD by inspecting the body element of your page.

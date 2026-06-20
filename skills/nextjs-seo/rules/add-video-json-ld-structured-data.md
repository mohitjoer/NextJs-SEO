---
title: Add VideoObject JSON-LD structured data to a page
description: Learn how to add VideoObject JSON-LD structured data to a page using standard Next.js features.
---

Next.js natively supports adding VideoObject JSON-LD structured data to a page.

## Using JSON-LD Scripts

1. Add a standard `<script>` tag inside your page component.

   ```tsx
   // app/videos/nextjs-16-tutorial/page.tsx

   export default function VideoPage() {
     return (
       <>
               <script
        type="application/ld+json"
        dangerouslySetInnerHTML={{ __html: JSON.stringify({ "@context": "https://schema.org", /* Insert properties here based on component props */ }) }}
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

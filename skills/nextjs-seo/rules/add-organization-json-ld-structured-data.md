---
title: Add Organization JSON-LD structured data to a page
description: Learn how to add Organization/LocalBusiness JSON-LD structured data to a page using standard Next.js features.
---

Next.js natively supports adding Organization or LocalBusiness JSON-LD structured data to a page.

## Using JSON-LD Scripts

1. Add a standard `<script>` tag inside your page component.

   ```tsx
   // app/about/page.tsx

   export default function AboutPage() {
     return (
       <>
               <script
        type="application/ld+json"
        dangerouslySetInnerHTML={{ __html: JSON.stringify({ "@context": "https://schema.org", /* Insert properties here based on component props */ }) }}
      />
         <main>
           <h1>About Us</h1>
           {/* Your content */}
         </main>
       </>
     );
   }
   ```

2. Check the generated JSON-LD by inspecting the body element of your page.

  Tip: You can use the JSON-LD script in layout files, but it's recommended to use it in page files instead. Since layouts can be nested, adding JSON-LD in layouts can lead to duplicate or conflicting structured data when parent and child layouts both include JSON-LD scripts.

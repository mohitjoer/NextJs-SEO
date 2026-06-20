---
title: Add Organization JSON-LD structured data to a page
description: Learn how to add Organization/LocalBusiness JSON-LD structured data to a page using the JsonLdForOrganization component from nextjs-seo.
---

`nextjs-seo` provides the `JsonLdForOrganization` component to easily add Organization or LocalBusiness JSON-LD structured data to a page.

## Using the JsonLdForOrganization component

1. Import the `JsonLdForOrganization` component into every page where you want to generate the JSON-LD data.

   ```tsx
   // app/about/page.tsx
   import { JsonLdForOrganization } from "@mohitjoer/nextjs-seo";

   export default function AboutPage() {
     return (
       <>
         <JsonLdForOrganization
           type="Organization"
           name="Example Corp"
           url="https://example.com"
           logo="https://example.com/logo.png"
           contactPoint={[{
             telephone: "+1-401-555-1212",
             contactType: "customer service"
           }]}
           scriptKey="org-json-ld"
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

  Tip: You can use the `JsonLdForOrganization` component in layout files, but it's recommended to use it in page files instead. Since layouts can be nested, adding JSON-LD in layouts can lead to duplicate or conflicting structured data when parent and child layouts both include JSON-LD scripts.

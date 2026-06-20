---
title: Add HowTo JSON-LD structured data to a page
description: Learn how to add HowTo JSON-LD structured data to a page using the JsonLdForHowTo component from nextjs-seo.
---

`nextjs-seo` provides the `JsonLdForHowTo` component to easily add HowTo JSON-LD structured data to a page.

## Using the JsonLdForHowTo component

1. Import the `JsonLdForHowTo` component into every page where you want to generate the JSON-LD data.

   ```tsx
   // app/tutorials/how-to-tie-a-tie/page.tsx
   import { JsonLdForHowTo } from "@mohitjoer/nextjs-seo";

   export default function HowToPage() {
     return (
       <>
         <JsonLdForHowTo
           name="How to tie a tie"
           description="Learn the classic Windsor knot."
           step={[
             {
               name: "Preparation",
               text: "Drape the tie around your neck."
             },
             {
               name: "Cross the ends",
               text: "Cross the wide end over the narrow end."
             }
           ]}
           scriptKey="howto-json-ld"
         />
         <main>
           <h1>How to tie a tie</h1>
           {/* Your content */}
         </main>
       </>
     );
   }
   ```

2. Check the generated JSON-LD by inspecting the body element of your page.

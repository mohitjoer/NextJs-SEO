---
title: Add Event JSON-LD structured data to a page
description: Learn how to add Event JSON-LD structured data to a page using the JsonLdForEvent component from nextjs-seo.
---

`nextjs-seo` provides the `JsonLdForEvent` component to easily add Event JSON-LD structured data to a page.

## Using the JsonLdForEvent component

1. Import the `JsonLdForEvent` component into every page where you want to generate the JSON-LD data.

   ```tsx
   // app/events/nextjs-conf-2026/page.tsx
   import { JsonLdForEvent } from "@mohitjoer/nextjs-seo";

   export default function EventPage() {
     return (
       <>
         <JsonLdForEvent
           name="Next.js Conf 2026"
           startDate="2026-10-25T09:00:00Z"
           endDate="2026-10-25T18:00:00Z"
           eventAttendanceMode="https://schema.org/OnlineEventAttendanceMode"
           eventStatus="https://schema.org/EventScheduled"
           location={{
             "@type": "VirtualLocation",
             url: "https://nextjs.org/conf"
           }}
           scriptKey="event-json-ld"
         />
         <main>
           <h1>Next.js Conf 2026</h1>
           {/* Your content */}
         </main>
       </>
     );
   }
   ```

2. Check the generated JSON-LD by inspecting the body element of your page.

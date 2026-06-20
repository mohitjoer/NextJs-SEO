---
title: Add Software Application JSON-LD structured data to a page
description: Learn how to add Software Application JSON-LD structured data to a page using standard Next.js features.
---

Next.js natively supports adding Software Application JSON-LD structured data to a page.

## Using JSON-LD Scripts

1. Add a standard `<script>` tag inside your page component.

   ```tsx
   // app/task-manager/page.tsx

   export default function TaskManagerPage() {
     return (
       <>
               <script
        type="application/ld+json"
        dangerouslySetInnerHTML={{ __html: JSON.stringify({ "@context": "https://schema.org", /* Insert properties here based on component props */ }) }}
      />
         <main>
           <h1>Task Manager Pro</h1>
           {/* Your content */}
         </main>
       </>
     );
   }
   ```

2. Check the generated JSON-LD by inspecting the body element of your page.

  Tip: You can use the JSON-LD script in layout files, but it's recommended to use it in page files instead. Since layouts can be nested, adding JSON-LD in layouts can lead to duplicate or conflicting structured data when parent and child layouts both include JSON-LD scripts.
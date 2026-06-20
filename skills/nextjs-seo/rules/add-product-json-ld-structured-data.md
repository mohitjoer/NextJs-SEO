---
title: Add Product JSON-LD structured data to a page
description: Learn how to add Product JSON-LD structured data to a page using the JsonLdForProduct component from nextjs-seo.
---

`nextjs-seo` provides the `JsonLdForProduct` component to easily add Product and AggregateRating JSON-LD structured data to a page.

## Using the JsonLdForProduct component

1. Import the `JsonLdForProduct` component into every page where you want to generate the JSON-LD data.

   ```tsx
   // app/products/[slug]/page.tsx
   import { JsonLdForProduct } from "@mohitjoer/nextjs-seo";

   export default function ProductPage() {
     return (
       <>
         <JsonLdForProduct
           name="Awesome Gadget"
           image={["https://example.com/photos/1x1/photo.jpg"]}
           description="The best gadget for all your needs."
           sku="0446310786"
           mpn="925872"
           brand={{ name: "Acme" }}
           review={{
             author: "Jane Doe",
             datePublished: "2026-01-10",
             reviewBody: "This is a great product.",
             reviewRating: { bestRating: "5", ratingValue: "4", worstRating: "1" }
           }}
           aggregateRating={{
             ratingValue: "4.4",
             reviewCount: "89"
           }}
           offers={{
             priceCurrency: "USD",
             price: "119.99",
             priceValidUntil: "2026-11-20",
             itemCondition: "https://schema.org/NewCondition",
             availability: "https://schema.org/InStock",
             url: "https://example.com/awesome-gadget"
           }}
           scriptKey="product-json-ld"
         />
         <main>
           <h1>Awesome Gadget</h1>
           {/* Your content */}
         </main>
       </>
     );
   }
   ```

2. Check the generated JSON-LD by inspecting the body element of your page.

  Tip: You can use the `JsonLdForProduct` component in layout files, but it's recommended to use it in page files instead. Since layouts can be nested, adding JSON-LD in layouts can lead to duplicate or conflicting structured data when parent and child layouts both include JSON-LD scripts.

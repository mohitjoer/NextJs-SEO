---
title: SEO Check Tool
description: Learn how to audit your Next.js project's SEO implementation with the built-in check tool from nextjs-seo.
---

`nextjs-seo` includes a built-in tool to audit your project's SEO implementation.

## Setup

1. Add the following script to your `package.json`:

   ```json
   //package.json
   {
     "scripts": {
       "check-seo": "node --input-type=module -e \"import('@mohitjoer/nextjs-seo/scripts').then(m => m.checkSeo())\""
     }
   }
   ```

2. Run the check from your terminal:

   ```sh
   npm run check-seo
   ```

   ```sh
   yarn check-seo
   ```

   ```sh
   pnpm check-seo
   ```

## What it checks

The SEO check tool analyzes the following areas of your project:

### 1. Page Metadata

Identifies the metadata status for each page in your application:

- **Pages without metadata**: Routes that are missing metadata configuration
- **Pages with manual metadata**: Routes using Next.js native metadata export
- **Pages using `genPageMetadata`**: Routes leveraging the library's metadata utility

### 2. Robots Configuration

Verifies how your site handles robot crawling rules:

- **Static file**: Checks if `robots.txt` exists in the `public` folder
- **Manual generation**: Detects if you're using `robots.ts` or `robots.js` with custom logic
- **Library utility**: Identifies usage of the `robotsTxt` function from the library

### 3. Sitemap Configuration

Examines your sitemap implementation:

- **Static file**: Checks if `sitemap.xml` exists in the `public` folder
- **Manual generation**: Detects if you're using `sitemap.ts` or `sitemap.js` with custom logic
- **Library utility**: Identifies usage of the `sitemapXml` function from the library

### 4. llms.txt Configuration

Verifies how your site handles AI crawler documentation:

- **Static file**: Checks if a static `llms.txt` exists in the `public` folder
- **Library utility**: Detects whether `generateLlmsTxt` is wired into your build script (build-time generation) or set up as a separate manual-generation script
- **Missing**: Flags if no `llms.txt` generation method is detected

### 5. Structured Data (JSON-LD)

Examines your pages for rich-content opportunities:

- **Missing JSON-LD components**: Flags pages with rich content (articles, FAQs, products) lacking any structured data script

### 6. Heading Hierarchy

Validates your HTML heading structure across all rendered pages for both SEO and accessibility (a11y) best practices:

- **Missing `<h1>`**: Flags pages without a primary `<h1>` heading
- **Multiple `<h1>`s**: Flags pages with more than one `<h1>`. While not directly penalized by Google, a single `<h1>` remains the accessibility gold standard
- **Skipped heading levels**: Flags logical breaks in your outline (e.g., jumping directly from `<h1>` to `<h3>` without an intervening `<h2>`), which disorients screen-reader users

### 7. Semantic Landmarks

Validates the use of HTML5 landmark elements that define a page's major regions for screen readers and crawlers:

- **Missing `<main>`**: Flags pages without a `<main>` element wrapping the primary content
- **Multiple page-level `<main>`s**: Flags pages with more than one top-level `<main>` landmark. (Nested `<header>`/`<footer>` inside `<article>` or `<section>` elements, e.g. on a blog card, are valid and not flagged)
- **Missing `<header>` / `<footer>`**: Flags pages without page-level `<header>` and `<footer>` landmarks
- **Generic containers instead of landmarks**: Flags likely masthead/footer content (e.g. nav + logo at the top, copyright + links at the bottom) implemented with plain `<div>`s instead of semantic tags

## Suggestions

Based on the analysis, the tool provides actionable recommendations to enhance your SEO setup, such as:

- Adding metadata to pages that are missing it
- Implementing dynamic `robots.txt` instead of static files
- Configuring sitemap generation for better crawlability
- Adding an `llms.txt` file
- Replacing static `defaultOgImg` with a dynamic `opengraph-image.tsx` route where appropriate
- Leveraging library utilities for consistency
- Fixing heading hierarchy violations (zero/multiple `<h1>`s or skipped heading levels)
- Adding missing semantic landmarks (`<header>`, `<footer>`, `<main>`) in place of generic `<div>`s

Tip: Run this check regularly during development and before deployment to ensure your SEO configuration is complete and up to date.
---
name: online-store-builder
description: Design and build an online store website with HTML, CSS and JavaScript, including product pages, product listings, a working shopping cart, checkout hand-off, and search engine optimization with structured data. Use this whenever the user wants to build a shop, store page, product page, cart, e-commerce site, or improve SEO for products, even if they only say "my clothing shop website". Persian triggers include فروشگاه آنلاین، صفحه محصول، سبد خرید، سئو.
---

# Online store builder

## Gather only what is missing
Product type and rough count, currency, language (and whether the layout is right-to-left), brand colors or style, and how payment will be handled. Do not ask what you can reasonably assume.

## Pages
Home, category or listing, product page, cart, checkout hand-off, about and contact, and policy pages (shipping, returns). Policy and contact pages build trust, so do not skip them.

## Product page
- Image gallery with real product photos and descriptive alt text
- Title, price, stock state, and variant choices (size, color) as clear selectable chips
- Add to cart button that is easy to find on mobile
- Short shipping and return summary near the button
- Size guide when it is clothing
- Related products. Show reviews only if they are real.

## Cart
- Store prices as integers in the smallest sensible unit to avoid floating point errors. Compute totals in code, never by hand.
- Quantity change, remove, empty state, and a clear total.
- Persist the cart with `localStorage` on the user's own hosted site. Wrap storage access in try/catch.

## Payments and security
- Never collect or store card data yourself. Send the shopper to a payment gateway page.
- Prices in the browser can be tampered with. The server or gateway must recompute the total from trusted product data.
- Serve the site over HTTPS. Validate form inputs. Keep secrets out of client-side code.
- If the user needs inventory, orders, accounts and payments at scale, say honestly that a store platform may serve them better than a hand-built site.

## SEO
- Unique `<title>` (about 60 characters) and meta description (about 155) per page, one `h1`, clean readable URLs.
- Product structured data as JSON-LD:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Product name",
  "image": ["https://example.com/photo.jpg"],
  "description": "Short, accurate description.",
  "offers": {
    "@type": "Offer",
    "price": "490000",
    "priceCurrency": "IRR",
    "availability": "https://schema.org/InStock"
  }
}
</script>
```

- Open Graph tags for sharing, canonical links, `sitemap.xml` and `robots.txt`.
- Image width and height attributes, lazy loading, modern formats (WebP), and fast mobile performance.
- Be honest: these practices help, but nobody can guarantee a search ranking.

## Right-to-left Persian stores
Set `lang="fa" dir="rtl"`, use logical CSS properties, bundle the Vazirmatn font, format prices with thousands separators and the currency word, and normalize Persian digits before calculations.

## Quality bar
Mobile first, readable contrast, keyboard-usable buttons, labels on form fields, no layout jumping while images load. Verify the cart totals with at least three test cases before you hand the code over.

# e-automation.net — Full Website Package

## Scale
- 1 homepage (index.html)
- 50 state distributor pages (/locations/{state}.html)
- 1 "all manufacturers" index (/products/all-manufacturers.html)
- 3,045 brand index pages (/products/{brand}/index.html)
- 22,265 individual part/SKU pages (/products/{brand}/{brand}-{part}.html)
- 1 sitemap.xml listing all 25,362 URLs

## Structure (matches gsatinternational.com pattern)
```
/index.html
/styles.css
/stock-data.js
/sitemap.xml
/locations/
    california.html
    texas.html
    ... (50 states)
/products/
    all-manufacturers.html
    allen-bradley/
        index.html
        allen-bradley-1746-ia8.html
        ... (one file per part)
    siemens/
        index.html
        siemens-6es7-214-1ag40-0xb0.html
        ...
    ... (3,045 brand folders)
```

## Shared header/footer
Every single page (homepage, state pages, brand indexes, part pages) is
built from the same two functions (`header_block`, `footer_block` in the
build scripts) so the topbar, nav, WhatsApp links, and footer are
byte-for-byte identical across all 25,000+ pages. Only the `<title>`,
meta description, canonical URL, breadcrumb, and page body change.

## Data source note
The 22,265 parts are the real, cleaned dataset (public manufacturer
catalog numbers) used as the working inventory while your final
confirmed 20,000-item list is prepared. When you send your real
inventory (CSV/Excel), re-run the generator against it to produce the
final part pages 1:1 with your actual stock.

## Deploying
Upload the entire folder (all files and subfolders) to the root of your
e-automation.net hosting. Fully static — no server or build step
required at runtime.

## Still to plug in
1. Real 20,000-item inventory (swap into stock-data.js, regenerate)
2. Formspree endpoint for the contact form (currently a placeholder)
3. Real photography for the About section
4. Favicons (favicon.ico, apple-touch-icon.png, etc.)

## Regenerating
The full build is reproducible from the Python scripts used to create
it (data loading → templates → product pages → brand pages → state
pages → homepage → sitemap). Re-running them against an updated
stock-data.js regenerates the entire site from your real inventory.

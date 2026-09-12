Product image naming convention:
  images/products/{brand-slug}/{brand-slug}-{part-slug}-1.jpg
  images/products/{brand-slug}/{brand-slug}-{part-slug}-2.jpg
  images/products/{brand-slug}/{brand-slug}-{part-slug}-3.jpg

Example for Allen-Bradley 1746-IA8:
  images/products/allen-bradley/allen-bradley-1746-ia8-1.jpg
  images/products/allen-bradley/allen-bradley-1746-ia8-2.jpg
  images/products/allen-bradley/allen-bradley-1746-ia8-3.jpg

Each product page's carousel looks for up to 3 images at these exact paths.
Any that don't exist yet are skipped automatically (carousel shows only
the images that are actually present, or a "coming soon" placeholder if
none are uploaded yet for that part).

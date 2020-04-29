---
title: "Pdf"
date: 2020-04-29T22:17:38+02:00
---
### Extract all pages from a pdf

```
qpdf $SOURCE.pdf --compress-streams=n --split-pages page.pdf
```

### Edit with Gimp

{{% notice note %}}
Don't forget to set the resolution at least to 300 pixels/in.
{{% /notice %}}

### Rebuild the pdf

```
pdfunite page-* $NEW_PDF.pdf
```
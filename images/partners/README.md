# Partner images

This folder contains the partner images used on the partners page.

Recommended conversions to generate WebP versions (run from project root):

Using ImageMagick:

```powershell
# convert PNG/JPG to WebP with quality 80
magick images\partners\cardmarket.png -quality 80 images\partners\cardmarket.webp
magick images\partners\cardclub.jpg -quality 80 images\partners\cardclub.webp
magick images\partners\wizardswell.jpg -quality 80 images\partners\wizardswell.webp
```

Using Google `cwebp` (binary):

```powershell
cwebp -q 80 images\partners\cardmarket.png -o images\partners\cardmarket.webp
cwebp -q 80 images\partners\cardclub.jpg -o images\partners\cardclub.webp
cwebp -q 80 images\partners\wizardswell.jpg -o images\partners\wizardswell.webp
```

Using Python + Pillow (script `scripts/resize_images.py` can be adapted):

```python
from PIL import Image
im = Image.open('images/partners/cardclub.jpg')
im.save('images/partners/cardclub.webp', 'WEBP', quality=80)
```

After creating `.webp` files the `<picture>` tags in `partners.html` will serve them where supported, with the original images as fallbacks.

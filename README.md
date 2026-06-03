# Image → Vector Converter (MVP)

A small, embeddable widget that lets a visitor upload a **JPG, PNG, or SVG** and
convert it into a **scalable vector (SVG)** they can download. Everything runs in
the visitor's browser — there is no server and no paid API.

## Files

| File | What it is |
|------|-----------|
| `index.html` | The widget itself. Works on its own when opened in a browser. |
| `embed-example.html` | Shows how to embed the widget into another web page. |
| `README.md` | This file. |

## Try it locally

Just open `index.html` in a web browser (double-click it), then upload an image
and click **Convert to Vector**.

## How the conversion works

- **JPG / PNG** are *raster* images (a grid of pixels). The widget "traces" them
  into shapes using the open-source library **ImageTracer.js**, producing an SVG.
- **SVG** uploads are already vectors, so they pass straight through.
- A **Detail** setting (Low / Medium / High) trades file size against how much
  fine detail is preserved.

> Tip: tracing works best on **logos, icons, and flat-color graphics**. Detailed
> photographs *can* be traced but produce large, less-clean files — that's normal
> for any auto-vectorizer.

## How to embed it on your website

Once the files are hosted online (see below), paste this where you want the
widget to appear:

```html
<iframe
  src="https://YOUR-HOSTED-URL/index.html"
  style="width:100%; height:720px; border:1px solid #e2e8f0; border-radius:12px;"
  title="Image to Vector Converter"
  loading="lazy">
</iframe>
```

Replace `https://YOUR-HOSTED-URL/` with wherever the files end up living.

## Hosting (free options)

- **GitHub Pages** — push this folder to a GitHub repo, enable Pages, and you get
  a public URL. Good default.
- **Netlify / Cloudflare Pages** — drag-and-drop the folder, get a URL.

## Possible next steps (post-MVP ideas)

- Choose number of colors / black-and-white "stencil" mode
- Side-by-side zoom and "fit to width" controls
- Copy SVG code to clipboard
- Optional higher-quality tracing for large images
- Your own branding / colors on the widget

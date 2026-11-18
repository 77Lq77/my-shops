# my-shops

This directory contains static storefront and brand pages generated as demo outputs by n8n workflows.

Each subdirectory is an independent shop that can be opened directly in a browser or served with a local static server.

## Stores

| Store | Directory | Description |
| --- | --- | --- |
| One Bookshop | [`one-bookshop/`](./one-bookshop) | A children's bookshop page for readers aged 8–12, with curated titles and an inquiry-based purchasing flow |

## One Bookshop

[One Bookshop](./one-bookshop/index.html) is a responsive, standalone landing page produced from an n8n workflow demo.

The page includes:

- A bookstore hero section and brand introduction
- A featured bookshelf containing four titles
- A price range of €9–€20
- A story explaining the curation approach
- An expandable FAQ section
- A contact form powered by the visitor's email client
- Mobile layout, scroll animations, and image fallback placeholders

## Run with n8n

The shop is intended to be created or updated by an n8n workflow. The workflow should generate the HTML output under `my-shops/<store-name>/` and return or save the final page there.

The generated page uses no n8n runtime dependencies after export, so it can be hosted independently.

## Local Preview

From the repository root, run:

```bash
cd my-shops
python -m http.server 8000
```

Then open:

- <http://localhost:8000/one-bookshop/>
- [One Bookshop](./one-bookshop/index.html)

You can also use a static-server extension such as Live Server in VS Code.

## Technical Notes

- Built with plain HTML, CSS, and JavaScript
- No build step or npm dependencies are required
- Page styles and scripts are kept in each store's `index.html`
- Product images and fonts are loaded from external CDNs
- If an image fails to load, a colored fallback block remains visible
- The contact form uses `mailto:` and does not submit data to a backend

## Adding a Generated Store

1. Configure or update an n8n workflow to generate a complete store page.
2. Create a store directory under `my-shops/`, for example `my-shops/new-shop/`.
3. Save the workflow output as `index.html` in that directory.
4. Add the store name, directory, and description to the table above.

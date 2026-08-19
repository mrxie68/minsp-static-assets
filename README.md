# minsp-static-assets

Static assets prepared for an external CDN-backed repository.

## Included assets

- `twikoo/twikoo.min.js`
- `twikoo/twikoo.css`
- `uikit/uikit.min.js`
- `uikit/uikit.min.css`

## Refresh assets

Run from repo root:

```bash
pnpm sync:static-assets
```

## Future CDN wiring

Once the external repository is created and pushed, configure the main site with:

- `PUBLIC_CDN_STATIC_BASE=https://cdn.example.com/gh/<user>/<repo>@<tag>`

Then the main site will automatically switch these assets to:

- `<base>/twikoo/twikoo.min.js`
- `<base>/twikoo/twikoo.css`
- `<base>/uikit/uikit.min.js`
- `<base>/uikit/uikit.min.css`

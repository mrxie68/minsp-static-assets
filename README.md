# minsp-static-assets

Static assets prepared for an external CDN-backed repository.

## Included assets

- `twikoo/twikoo.min.js`
- `twikoo/twikoo.css`
- `uikit/uikit.min.js`
- `uikit/uikit.min.css`

## Refresh assets only

Run from repo root:

```bash
pnpm sync:static-assets
```

## Publish assets repository

Run from repo root:

```bash
pnpm publish:static-assets -- -m "Update static assets"
```

Create and push a new release tag at the same time:

```bash
pnpm publish:static-assets -- -m "Release static assets" --tag v1.0.1
```

## Push Twikoo with static assets together

The main Twikoo push flow now syncs and publishes this repository first:

```bash
pnpm push:my-tw -- -m "Update custom Twikoo"
```

If needed, skip the static assets step:

```bash
pnpm push:my-tw -- -m "Update custom Twikoo" --skip-static-assets
```

## Future CDN wiring

Once the external repository is created and pushed, configure the main site with:

- `PUBLIC_CDN_STATIC_BASE=https://cdn.example.com/gh/<user>/<repo>@<tag>`

Then the main site will automatically switch these assets to:

- `<base>/twikoo/twikoo.min.js`
- `<base>/twikoo/twikoo.css`
- `<base>/uikit/uikit.min.js`
- `<base>/uikit/uikit.min.css`
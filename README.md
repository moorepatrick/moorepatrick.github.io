# moorepatrick.com

Personal site built with [Hugo](https://gohugo.io/) and the [DoIt](https://github.com/HEIGE-PCloud/DoIt) theme, hosted on Cloudflare Pages.

## Requirements

- [Hugo extended](https://gohugo.io/installation/) 0.169.0 (required for SCSS)
- [Go](https://go.dev/dl/) 1.20 or newer (the theme is a Hugo Module)

## Local development

Start the development server:

```sh
hugo server
```

Include drafts:

```sh
hugo server -D
```

## Build

```sh
hugo --gc --minify
```

The generated site is written to `public/`.

## Theme

The DoIt theme is pinned in `go.mod` as a Hugo Module. Update it with:

```sh
hugo mod get -u github.com/HEIGE-PCloud/DoIt
hugo mod tidy
```

Rebuild the site after updating to verify the new theme version.

## Deployment

The site deploys to Cloudflare Pages from the `main` branch.

Cloudflare Pages build settings:

| Setting | Value |
| --- | --- |
| Build command | `hugo --gc --minify` |
| Build output directory | `public` |
| `HUGO_VERSION` | `0.169.0` |

Set `HUGO_VERSION` for both the Production and Preview environments. Cloudflare then installs the matching extended Hugo release. The canonical `baseURL` is set to `https://moorepatrick.com/` in `config.yaml`.

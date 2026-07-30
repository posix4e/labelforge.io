# labelforge.io

Static marketing site for Labelforge, served by GitHub Pages from the `main` branch of this repo. Migrated from gamma.app in July 2026.

- `index.html` — the whole site (no build step, no JS)
- `CNAME` — sets the custom domain (labelforge.io) on GitHub Pages
- `assets/` — images carried over from the gamma site, converted to WebP

## DNS (Namecheap → Advanced DNS)

Apex `@` A records (GitHub Pages):

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

`www` CNAME → `posix4e.github.io`

After DNS propagates, enable **Enforce HTTPS** in the repo's Pages settings.

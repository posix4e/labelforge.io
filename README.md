# labelforge.io

Static marketing site for Labelforge, a technical systems company building the
reinforcement-learning, post-training, data, evaluation, software, and
infrastructure layers behind better models. The site is served by GitHub Pages
from the `main` branch of this repo.

- `index.html` — the complete site (no build step and no JavaScript)
- `CNAME` — sets the custom domain (labelforge.io) on GitHub Pages
- `assets/human-logo.webp` — HUMAN Protocol case-study mark

## DNS and email (Cloudflare)

Namecheap remains the registrar. Cloudflare is authoritative for DNS:

```
dayana.ns.cloudflare.com
thomas.ns.cloudflare.com
```

The proxied web records point to GitHub Pages:

```
@    A      185.199.108.153
@    A      185.199.109.153
@    A      185.199.110.153
@    A      185.199.111.153
www  CNAME  posix4e.github.io
```

Cloudflare Universal SSL terminates HTTPS at the edge, and **Always Use
HTTPS** is enabled.

Inbound mail uses Cloudflare Email Routing. The active catch-all forwards
every `@labelforge.io` address to `fralex@googlegroups.com`. The previous
specific `sales@labelforge.io` rule remains disabled for easy rollback.
The apex MX, SPF, DKIM, and DMARC records are managed in Cloudflare.

Outbound mail uses Cloudflare Email Sending:

```
Host: smtp.mx.cloudflare.net
Port: 465
Security: implicit TLS (SMTPS)
Username: api_token
```

The SMTP password is the scoped Cloudflare API token named
`labelforge.io SMTP`, with **Email Sending: Edit** permission. The token is
not stored or committed in this repository. The previous Namecheap Private
Email subscription is retained temporarily for access to stored mail; its
legacy DNS records are no longer active.

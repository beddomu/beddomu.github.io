# beddomu.github.io

Serves two things, both required by Tesla's Fleet API:

- `.well-known/appspecific/com.tesla.3p.public-key.pem` — the public half of the
  key pair used to register a third-party application. Public by design; the
  private key never leaves the machine that generated it.
- `callback/` — catches the OAuth redirect and forwards the authorisation code
  to a dashboard on the local network, which Tesla cannot redirect to directly.

`.nojekyll` is present because GitHub Pages runs Jekyll by default, and Jekyll
silently refuses to publish directories beginning with a dot — which would make
the well-known path 404.

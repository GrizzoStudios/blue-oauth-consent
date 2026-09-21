# blue-oauth-consent

The OAuth consent screen for a private Supabase project's OAuth server. When a
connector asks for access, Supabase sends the account owner here to approve or
deny it; the page signs in with Google and calls
`approveAuthorization` / `denyAuthorization`.

**Why this repo is public:** GitHub Pages needs it, and there is nothing here to
protect. The only credential in `index.html` is the Supabase *publishable* key,
which is public by design and useless without an authenticated session that
passes row-level security.

It lives here rather than on the Supabase project because Supabase forces
`Content-Type: text/plain` and `Content-Security-Policy: default-src 'none';
sandbox` on any HTML served from `*.supabase.co/functions/v1/*` — which both
stops the page rendering and blocks the script that is its entire purpose.

Source of truth for this file is a private repo; edit it there.

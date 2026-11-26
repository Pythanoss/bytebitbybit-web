# bytebitbybit-web

Static sites for bytebitbybit.com and its subdomains, served free by
Cloudflare Workers (static assets only, so requests cost nothing). Every
`git push` to `main` redeploys every site through Workers Builds.

| Folder | Worker | Domain |
|---|---|---|
| `root/` | `bytebitbybit` | https://bytebitbybit.com (and www) |
| `magicseal/` | `magicseal` | https://magicseal.bytebitbybit.com |

Each folder has a `wrangler.jsonc` (the Worker's name and its custom domains)
and a `public/` folder, which is exactly what gets served.

`app-ads.txt` (AdMob) lives in `root/public/` because Play Console's
"Website" for the apps is https://bytebitbybit.com; a copy sits in
`magicseal/public/` too.

## Adding a site for a new product

1. Copy `magicseal/` to `newapp/`; in `newapp/wrangler.jsonc` set `"name":
   "newapp"` and the route to `newapp.bytebitbybit.com`; put the site in
   `newapp/public/`. Push.
2. Cloudflare dashboard → Workers & Pages → Create application → Import a
   repository → this repo → project name `newapp`, **Root directory
   `newapp`** (build command empty, deploy command `npx wrangler deploy`).
3. The custom domain and its DNS record are created by the first deploy.
4. Add a card for it on `root/public/index.html`.

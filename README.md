# bytebitbybit-web

Static sites for bytebitbybit.com and its subdomains, hosted free on
Cloudflare Pages. No build step: each folder is published as it is, and every
`git push` to `main` redeploys every site.

| Folder | Pages project | Domain |
|---|---|---|
| `root/` | `bytebitbybit` | https://bytebitbybit.com |
| `magicseal/` | `magicseal` | https://magicseal.bytebitbybit.com |

`app-ads.txt` (AdMob) lives in `root/` because Play Console's "Website" for
the apps is https://bytebitbybit.com; a copy sits in `magicseal/` too.

## Adding a site for a new product

1. Make a folder, e.g. `newapp/`, with an `index.html`.
2. Push.
3. Cloudflare dashboard → Workers & Pages → Create → Pages → Connect to Git →
   this repo → project name `newapp`, framework **None**, build command
   **empty**, build output directory **`newapp`** → Save and Deploy.
4. The project → Custom domains → add `newapp.bytebitbybit.com`.
5. Add a card for it on `root/index.html`.

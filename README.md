# Recomworks Ltd — website

Static site: `index.html`, `services.html`, `about.html`, `contact.html`, shared styling in `css/styles.css`, logo files in `assets/`. No build step — these files can be opened directly or hosted as-is.

## Deploying with GitHub Pages (free)

1. **Create the GitHub account/repo.** Sign up at github.com using `hello@recomworks.co.uk` (keep this completely separate from any other GitHub account/org). Create a new **public** repository, e.g. `recomworks-website`.
2. **Upload these files.** Easiest: on the repo's page, click *Add file → Upload files*, drag in everything from this folder (keep the `assets/` and `css/` folders intact), and commit.
3. **Turn on Pages.** In the repo, go to *Settings → Pages*. Under "Build and deployment", set Source to **Deploy from a branch**, Branch to **main** and folder to **/ (root)**, then Save.
4. GitHub will publish the site at `https://<your-username>.github.io/recomworks-website/` within a minute or two — check it loads correctly before moving on to the custom domain.

## Pointing www.recomworks.co.uk at it

A `CNAME` file is already included in this folder set to `www.recomworks.co.uk` — GitHub Pages uses it to recognise the custom domain once uploaded with the rest of the files.

At your domain registrar/DNS provider for `recomworks.co.uk`, add:

| Type  | Host / Name | Value |
|-------|-------------|-------|
| CNAME | `www`       | `<your-username>.github.io` |

(Optional, if you also want the bare `recomworks.co.uk` — no "www" — to work: add four **A** records on the root/`@` host pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.)

DNS changes can take anywhere from a few minutes to a few hours to take effect. Once it has, go back to *Settings → Pages* in the repo, confirm the custom domain shows as verified, and tick **Enforce HTTPS** once the option becomes available (GitHub provisions the SSL certificate automatically).

## Updating the site later

Edit the HTML/CSS files directly (or ask Claude to make the change and hand you updated files), then upload/commit the changed files to the same repo — Pages redeploys automatically within a minute or so of any commit to `main`.

## Contact form

The form on `contact.html` currently opens the visitor's email app pre-filled to `hello@recomworks.co.uk` (no backend needed). If you'd rather have enquiries land straight in your inbox without opening an email client, swap this for a form service like Formspree — ask Claude to wire it up once you've got a free account.

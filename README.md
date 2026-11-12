# redxam-network-landing

A ready-made personal website and blog that you can edit from a browser. It is a copy of the open source "Foundation" starter by Stackrole, built with Gatsby and Netlify CMS, and it still shows the starter's sample content (a fictional designer called Wyatt Morriss and a handful of demo posts).

[![Light mode screenshot](static/assets/gatsby-starter-foundation-light-mode.jpg)](static/assets/gatsby-starter-foundation-light-mode.jpg)

## What it does

- Home, About and Contact pages plus a blog with a paginated post list.
- Dark and light mode, with theme colors editable from the CMS.
- Client-side search over pages and posts (Elasticlunr).
- SEO tags, OpenGraph and Twitter card metadata, XML sitemap, web app manifest and offline support.
- Contact form that works on Netlify hosting (it posts to `/thanks`).
- Content lives in Markdown files under `src/content`, and site settings live in JSON files under `src/util`.
- Optional visual editor at `/admin` (Netlify CMS with Git Gateway) for pages, posts, settings and colors.

## Tech stack

- Gatsby 3, React 16
- Theme UI and Sass for styling
- gatsby-transformer-remark, gatsby-plugin-image and gatsby-plugin-sharp for content and images
- Netlify CMS (`netlify-cms-app`) and Netlify hosting

## Run it locally

You need Node.js 12 or 14 (the `node-sass` dependency does not build on newer Node versions) and Yarn or npm.

```bash
git clone https://github.com/maxawad/redxam-network-landing.git
cd redxam-network-landing
yarn install        # or: npm install
yarn develop        # or: npm run develop
```

Open http://localhost:8000. The GraphQL explorer is at http://localhost:8000/___graphql.

To use the CMS locally, run `npx netlify-cms-proxy-server` in a second terminal and open http://localhost:8000/admin/.

## Build a static site (live demo)

The site builds to plain static files and needs no API keys or secrets.

```bash
yarn build          # or: npm run build
yarn serve          # or: npm run serve, preview at http://localhost:9000
```

The output is in the `public/` folder. Upload that folder to any static host (Netlify, GitHub Pages, Cloudflare Pages, and so on). The included `netlify.toml` already builds with `npm run build` and publishes `public`.

## Configuration

- Site title, description, URL and icon: `src/util/site.json`
- Google Analytics ID: the `ga` field in `src/util/site.json`. It is a placeholder (`UA-XXXXXXXXX-X`), replace it with your own or remove the plugin.
- Social icons: `src/util/socialmedia.json`
- Theme colors: `src/util/default-colors.json` and `src/util/dark-theme-colors.json`
- Pages and posts: `src/content/pages` and `src/content/posts`
- CMS fields: `static/admin/config.yml`

To enable the online CMS on Netlify, turn on Identity, invite yourself, and enable Git Gateway under Settings, Identity, Services. Then sign in at `your-site.netlify.app/admin/`. Keep registration on "Invite only" so nobody else can edit the site.

## Folder structure

```
src/components   shared React components (header, footer, search, SEO)
src/templates    page templates (home, about, contact, blog list, blog post)
src/pages        404 and thanks pages
src/content      Markdown content for pages and posts
src/util         JSON settings edited by the CMS
src/assets/scss  styles
static           images, favicon and the CMS config in static/admin
```

## Status

Working as a template. It has not been customised beyond the starter, so the text, images, social links and analytics ID are all sample values. The dependencies are from 2021 (Gatsby 3, node-sass 4) and were not upgraded.

## Credits

This project is based on [gatsby-starter-foundation](https://github.com/stackrole/gatsby-starter-foundation) by [Stackrole](https://stackrole.com), released under the MIT License (see `LICENSE`). Photos in `static/assets` come from [Unsplash](https://unsplash.com).

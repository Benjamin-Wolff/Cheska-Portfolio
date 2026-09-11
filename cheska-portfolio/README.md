# Francesca Morales Portfolio

Personal portfolio website for Francesca Morales, built with SvelteKit and Tailwind CSS.

## Tech Stack

- SvelteKit
- Svelte
- Tailwind CSS
- `@sveltejs/adapter-static`
- Caddy
- GitHub Actions
- Hosted on a Linux server

## Local Development

From the `cheska-portfolio` directory:

```bash
npm install
npm run dev
```

To create a production build:

```bash
npm run build
```

The production files are generated in:

```text
build/
```

## Deployment

Deployment is automated through GitHub Actions.

Every push to `main`:

1. Checks out the repository.
2. Sets up Node.js 20.
3. Installs dependencies.
4. Runs `npm run build`.
5. Clears the existing `/var/www/portfolio` directory on the server.
6. Copies the new `build/` contents to `/var/www/portfolio`.

The workflow is located at:

```text
.github/workflows/deploy.yml
```

### Server

Caddy serves the site from:

```text
/var/www/portfolio
```

Caddy is configured to fall back to `index.html` for routes that do not correspond to a static file.

## Routing

The site uses **SvelteKit client-side routing / SPA fallback**.

In `svelte.config.js`, `adapter-static` is configured with:

```js
adapter: adapter({
    pages: 'build',
    assets: 'build',
    fallback: 'index.html',
    precompress: false,
    strict: true
})
```

This allows routes such as:

```text
/
/about
/campaigns
```

to be handled by SvelteKit in the browser rather than requiring a separate server-side application.

The Caddy configuration also contains:

```caddy
try_files {path} /index.html
```

This ensures that directly visiting a route such as `/about` still loads the SvelteKit application.

### Important

The deployment intentionally **cleans the server directory before each deployment**. This prevents old files from previous builds (such as old route directories) from remaining on the server.

## Reverting to MPA

If SPA routing causes undesirable first-load performance or other issues, the site can be converted back to a traditional statically generated multi-page setup.

The main change would be removing:

```js
fallback: 'index.html'
```

from `svelte.config.js` and adjusting the Caddy configuration to serve the generated route directories directly.

The current SPA configuration should therefore be considered a deliberate choice, not an accidental configuration.

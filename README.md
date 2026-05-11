# store-test Shopify theme

This repository is configured for local Shopify theme development, testing, and deployment.

## Setup

1. Install dependencies:

   ```powershell
   npm install
   ```

2. Start a local development theme:

   ```powershell
   npm run dev -- --store your-store.myshopify.com
   ```

   Shopify CLI will ask you to log in the first time. After login, the CLI remembers the store for future commands.

3. Check which store/theme is connected:

   ```powershell
   npm run info
   ```

## Daily workflow

1. Create a working branch:

   ```powershell
   git checkout -b codex/your-change-name
   ```

2. Run the local preview:

   ```powershell
   npm run dev
   ```

3. Run theme checks before pushing:

   ```powershell
   npm run check
   ```

4. Commit and push to GitHub:

   ```powershell
   git add .
   git commit -m "Describe your theme change"
   git push -u origin codex/your-change-name
   ```

## Deploy options

Push as a new unpublished theme for review:

```powershell
npm run push:unpublished -- --store your-store.myshopify.com
```

Push to a specific existing theme:

```powershell
npm run push -- --store your-store.myshopify.com --theme THEME_ID
```

Publish an existing unpublished theme:

```powershell
npm run publish -- --store your-store.myshopify.com --theme THEME_ID
```

Use `npm run list -- --store your-store.myshopify.com` to find theme IDs.

## Notes

- `.shopifyignore` prevents local workflow files from being uploaded to Shopify.
- `.gitignore` keeps dependencies, logs, generated ZIP packages, and local Shopify auth/cache files out of Git.
- Keep secrets such as Theme Access passwords or custom app tokens out of Git. Use environment variables or local `.env` files only.

# Vercel Web Analytics - Implementation Checklist

Use this checklist to ensure proper implementation of Vercel Web Analytics in your project.

## Prerequisites ✓

- [ ] Vercel account created ([sign up here](https://vercel.com/signup))
- [ ] Project exists on Vercel ([create new project](https://vercel.com/new))
- [ ] Vercel CLI installed locally

```bash
# Install Vercel CLI (choose one)
npm i -g vercel
pnpm i -g vercel
yarn global add vercel
bun i -g vercel
```

---

## Step 1: Enable Analytics in Vercel Dashboard ✓

- [ ] Login to [Vercel Dashboard](https://vercel.com/dashboard)
- [ ] Select your project
- [ ] Navigate to **Analytics** tab
- [ ] Click **Enable** button
- [ ] Confirm that Analytics is now enabled

> **Note:** This will add routes at `/_vercel/insights/*` after your next deployment.

---

## Step 2: Install Package ✓

Choose your package manager and install `@vercel/analytics`:

- [ ] Install package using your preferred package manager:

```bash
# npm
npm i @vercel/analytics

# pnpm
pnpm i @vercel/analytics

# yarn
yarn i @vercel/analytics

# bun
bun i @vercel/analytics
```

- [ ] Verify package appears in `package.json` dependencies
- [ ] Lock file updated (`package-lock.json`, `pnpm-lock.yaml`, `yarn.lock`, or `bun.lockb`)

---

## Step 3: Add Analytics to Your Application ✓

Select your framework and complete the integration:

### Next.js (App Router)
- [ ] Opened `app/layout.tsx` (or `app/layout.jsx`)
- [ ] Added import: `import { Analytics } from "@vercel/analytics/next";`
- [ ] Added `<Analytics />` component before closing `</body>` tag
- [ ] File saved

### Next.js (Pages Router)
- [ ] Opened `pages/_app.tsx` (or `pages/_app.js`)
- [ ] Added import: `import { Analytics } from "@vercel/analytics/next";`
- [ ] Added `<Analytics />` component in the return statement
- [ ] File saved

### Remix
- [ ] Opened `app/root.tsx` (or `app/root.jsx`)
- [ ] Added import: `import { Analytics } from "@vercel/analytics/remix";`
- [ ] Added `<Analytics />` component inside `<body>` tag
- [ ] File saved

### SvelteKit
- [ ] Created/opened `src/routes/+layout.ts` (or `+layout.js`)
- [ ] Added imports:
  ```ts
  import { dev } from "$app/environment";
  import { injectAnalytics } from "@vercel/analytics/sveltekit";
  ```
- [ ] Added function call: `injectAnalytics({ mode: dev ? "development" : "production" });`
- [ ] File saved

### Nuxt
- [ ] Opened `app.vue`
- [ ] Added import in script section: `import { Analytics } from '@vercel/analytics/nuxt';`
- [ ] Added `<Analytics />` component in template
- [ ] File saved

### Astro
- [ ] Opened base layout file (e.g., `src/layouts/Base.astro`)
- [ ] Added import: `import Analytics from '@vercel/analytics/astro';`
- [ ] Added `<Analytics />` component in `<head>` section
- [ ] File saved
- [ ] If using Astro adapter < 1.4.0, updated `astro.config.mjs` with `webAnalytics: { enabled: true }`

### Create React App
- [ ] Opened `App.tsx` (or `App.jsx`)
- [ ] Added import: `import { Analytics } from "@vercel/analytics/react";`
- [ ] Added `<Analytics />` component in the return statement
- [ ] File saved

### Vue
- [ ] Opened `src/App.vue`
- [ ] Added import in script section: `import { Analytics } from '@vercel/analytics/vue';`
- [ ] Added `<Analytics />` component in template
- [ ] File saved

### Plain HTML
- [ ] Opened HTML file(s) where you want analytics
- [ ] Added the following scripts before closing `</body>` tag:
  ```html
  <script>
    window.va = window.va || function () { (window.vaq = window.vaq || []).push(arguments); };
  </script>
  <script defer src="/_vercel/insights/script.js"></script>
  ```
- [ ] Files saved

### Other Frameworks
- [ ] Opened main entry file
- [ ] Added import: `import { inject } from "@vercel/analytics";`
- [ ] Called `inject();` function (ensure it runs only once, client-side)
- [ ] File saved

---

## Step 4: Build and Test Locally ✓

- [ ] Run local build to check for errors:
  ```bash
  npm run build
  # or
  pnpm build
  # or
  yarn build
  # or
  bun run build
  ```
- [ ] Build completed successfully without errors
- [ ] Run linter (if available):
  ```bash
  npm run lint
  # or
  pnpm lint
  ```
- [ ] No linting errors introduced
- [ ] Run tests (if available):
  ```bash
  npm test
  # or
  pnpm test
  ```
- [ ] All tests passing

---

## Step 5: Deploy to Vercel ✓

- [ ] Commit your changes to Git:
  ```bash
  git add .
  git commit -m "Add Vercel Web Analytics"
  git push
  ```
- [ ] Deploy to Vercel:
  ```bash
  vercel deploy --prod
  ```
  Or push to your main branch if Git integration is set up
- [ ] Deployment completed successfully
- [ ] Note your deployment URL

---

## Step 6: Verify Analytics is Working ✓

- [ ] Visit your deployed site at the Vercel URL
- [ ] Open browser DevTools (F12 or right-click → Inspect)
- [ ] Go to **Network** tab
- [ ] Refresh the page
- [ ] Look for a request to `/_vercel/insights/view`
- [ ] Request appears and returns 200 status code ✅

> **If you don't see the request:**
> - Ensure Analytics is enabled in Vercel dashboard
> - Check that your component/script is properly added
> - Verify you're accessing the Vercel-deployed URL (not localhost)
> - Disable ad blockers temporarily

---

## Step 7: View Analytics Dashboard ✓

- [ ] Go to [Vercel Dashboard](https://vercel.com/dashboard)
- [ ] Select your project
- [ ] Click **Analytics** tab
- [ ] Wait a few minutes for initial data to appear
- [ ] Verify you can see:
  - [ ] Page views
  - [ ] Visitor data
  - [ ] Top pages
  - [ ] Referral sources

> **Note:** It may take a few minutes to several hours for data to fully populate, especially for new implementations.

---

## Optional: Advanced Configuration ✓

### Custom Events (Pro/Enterprise only)
- [ ] Review [Custom Events documentation](/docs/analytics/custom-events)
- [ ] Implement custom event tracking for:
  - [ ] Button clicks
  - [ ] Form submissions
  - [ ] Custom user actions

### Data Filtering
- [ ] Explore [Filtering options](/docs/analytics/filtering)
- [ ] Set up filters for your analysis needs

### Privacy Compliance
- [ ] Review [Privacy Policy](/docs/analytics/privacy-policy)
- [ ] Update your site's privacy policy if needed
- [ ] Verify GDPR/CCPA compliance requirements are met

---

## Troubleshooting ✓

If you encounter issues, check the following:

- [ ] Analytics is enabled in Vercel dashboard
- [ ] `@vercel/analytics` package is installed and in dependencies
- [ ] Component/script is properly imported and added
- [ ] Site is deployed to Vercel (not just running locally)
- [ ] No build or runtime errors
- [ ] Ad blockers are disabled for testing
- [ ] Using correct import path for your framework
- [ ] Checked [Troubleshooting guide](/docs/analytics/troubleshooting)

---

## Resources ✓

Documentation:
- [ ] [Full Implementation Guide](VERCEL_WEB_ANALYTICS_GUIDE.md)
- [ ] [Quick Start Guide](VERCEL_ANALYTICS_QUICK_START.md)
- [ ] [Vercel Analytics Package Docs](/docs/analytics/package)
- [ ] [Custom Events](/docs/analytics/custom-events)
- [ ] [Filtering Data](/docs/analytics/filtering)
- [ ] [Privacy Policy](/docs/analytics/privacy-policy)
- [ ] [Pricing & Limits](/docs/analytics/limits-and-pricing)

Support:
- [ ] [Troubleshooting Guide](/docs/analytics/troubleshooting)
- [ ] [Vercel Community](https://github.com/vercel/vercel/discussions)
- [ ] [Vercel Support](https://vercel.com/support)

---

## ✅ Implementation Complete!

Once all items are checked, your Vercel Web Analytics implementation is complete. Your site will now track:

- **Page Views** - Every page visit
- **Visitors** - Unique and returning visitors
- **Traffic Sources** - Where your visitors come from
- **Top Pages** - Most visited pages
- **Device Types** - Desktop vs mobile usage
- **Geolocation** - Where your visitors are located

Start monitoring your analytics dashboard to gain insights into your site's performance!

---

**Last Updated:** January 2026
**Analytics Package Version:** @vercel/analytics@latest
**Compatible Frameworks:** Next.js, Remix, SvelteKit, Nuxt, Astro, React, Vue, HTML, and more

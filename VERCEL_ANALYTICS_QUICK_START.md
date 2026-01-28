# Vercel Web Analytics - Quick Start Guide

## TL;DR - Get Started in 3 Steps

### 1. Enable Analytics on Vercel Dashboard
- Go to your project on [Vercel Dashboard](https://vercel.com/dashboard)
- Click **Analytics** tab → Click **Enable**

### 2. Install Package
```bash
# Choose your package manager
npm i @vercel/analytics
# or
pnpm i @vercel/analytics
# or
yarn i @vercel/analytics
# or
bun i @vercel/analytics
```

### 3. Add to Your App

#### Next.js (App Router) - `app/layout.tsx`
```tsx
import { Analytics } from "@vercel/analytics/next";

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <body>
        {children}
        <Analytics />
      </body>
    </html>
  );
}
```

#### Next.js (Pages) - `pages/_app.tsx`
```tsx
import { Analytics } from "@vercel/analytics/next";

function MyApp({ Component, pageProps }) {
  return (
    <>
      <Component {...pageProps} />
      <Analytics />
    </>
  );
}
```

#### React - `App.tsx`
```tsx
import { Analytics } from "@vercel/analytics/react";

export default function App() {
  return (
    <div>
      {/* your app */}
      <Analytics />
    </div>
  );
}
```

#### Vue - `App.vue`
```vue
<script setup>
import { Analytics } from '@vercel/analytics/vue';
</script>

<template>
  <Analytics />
  <!-- your content -->
</template>
```

#### Remix - `app/root.tsx`
```tsx
import { Analytics } from "@vercel/analytics/remix";

export default function App() {
  return (
    <html>
      <body>
        <Analytics />
        {/* your content */}
      </body>
    </html>
  );
}
```

#### SvelteKit - `src/routes/+layout.ts`
```ts
import { dev } from "$app/environment";
import { injectAnalytics } from "@vercel/analytics/sveltekit";

injectAnalytics({ mode: dev ? "development" : "production" });
```

#### Astro - `src/layouts/Base.astro`
```astro
---
import Analytics from '@vercel/analytics/astro';
---
<html>
  <head>
    <Analytics />
  </head>
  <body>
    <slot />
  </body>
</html>
```

#### Plain HTML
```html
<script>
  window.va = window.va || function () { (window.vaq = window.vaq || []).push(arguments); };
</script>
<script defer src="/_vercel/insights/script.js"></script>
```

#### Other Frameworks - `main.js`
```js
import { inject } from "@vercel/analytics";

inject();
```

---

## Deploy & Verify

### Deploy to Vercel
```bash
vercel deploy
```

### Verify Installation
1. Visit your deployed site
2. Open browser DevTools → Network tab
3. Look for a request to `/_vercel/insights/view`
4. If you see it, analytics is working! 🎉

---

## View Your Data

1. Go to [Vercel Dashboard](https://vercel.com/dashboard)
2. Select your project
3. Click **Analytics** tab
4. Wait for traffic data to appear (usually within minutes)

---

## Framework-Specific Notes

| Framework | Import Path | Route Support | Notes |
|-----------|------------|---------------|-------|
| Next.js | `@vercel/analytics/next` | ✅ Yes | Best integration |
| Remix | `@vercel/analytics/remix` | ✅ Yes | Automatic route detection |
| SvelteKit | `@vercel/analytics/sveltekit` | ✅ Yes | Use `injectAnalytics()` |
| Nuxt | `@vercel/analytics/nuxt` | ✅ Yes | Component-based |
| Astro | `@vercel/analytics/astro` | ✅ Yes | v1.4.0+ |
| React (CRA) | `@vercel/analytics/react` | ❌ No | Component-based |
| Vue | `@vercel/analytics/vue` | ⚡ Auto | If using vue-router |
| HTML | N/A (script tag) | ❌ No | No package needed |
| Other | `@vercel/analytics` | ❌ No | Use `inject()` |

---

## Common Issues

### Analytics not showing?
- Ensure you've deployed to Vercel
- Check that Analytics is enabled in dashboard
- Verify the `/_vercel/insights/view` request appears in Network tab
- Wait a few minutes for data to appear

### Script not loading?
- Confirm you're accessing the site via Vercel's domain
- Check that the Analytics component/script is included
- Ensure no ad blockers are interfering

### Route tracking not working?
- Verify you're using the correct framework-specific import
- Check that your framework is supported for route tracking
- For custom routing, you may need custom events

---

## Next Steps

- 📊 [Custom Events](/docs/analytics/custom-events) - Track specific user interactions
- 🔍 [Filtering](/docs/analytics/filtering) - Segment and analyze your data
- 🔒 [Privacy & Compliance](/docs/analytics/privacy-policy) - GDPR, CCPA compliant
- 💰 [Pricing](/docs/analytics/limits-and-pricing) - Understand limits and costs

---

## Support

- 📚 [Full Documentation](VERCEL_WEB_ANALYTICS_GUIDE.md)
- 🐛 [Troubleshooting](/docs/analytics/troubleshooting)
- 💬 [Vercel Community](https://github.com/vercel/vercel/discussions)

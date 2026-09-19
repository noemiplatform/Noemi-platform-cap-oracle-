# Vercel Web Analytics - Code Examples Reference

Quick copy-paste code examples for implementing Vercel Web Analytics across different frameworks.

---

## Installation Commands

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

---

## Next.js App Router

### TypeScript - `app/layout.tsx`

```tsx
import { Analytics } from "@vercel/analytics/next";

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html lang="en">
      <head>
        <title>Next.js</title>
      </head>
      <body>
        {children}
        <Analytics />
      </body>
    </html>
  );
}
```

### JavaScript - `app/layout.jsx`

```jsx
import { Analytics } from "@vercel/analytics/next";

export default function RootLayout({ children }) {
  return (
    <html lang="en">
      <head>
        <title>Next.js</title>
      </head>
      <body>
        {children}
        <Analytics />
      </body>
    </html>
  );
}
```

---

## Next.js Pages Router

### TypeScript - `pages/_app.tsx`

```tsx
import type { AppProps } from "next/app";
import { Analytics } from "@vercel/analytics/next";

function MyApp({ Component, pageProps }: AppProps) {
  return (
    <>
      <Component {...pageProps} />
      <Analytics />
    </>
  );
}

export default MyApp;
```

### JavaScript - `pages/_app.js`

```jsx
import { Analytics } from "@vercel/analytics/next";

function MyApp({ Component, pageProps }) {
  return (
    <>
      <Component {...pageProps} />
      <Analytics />
    </>
  );
}

export default MyApp;
```

---

## Remix

### TypeScript - `app/root.tsx`

```tsx
import {
  Links,
  LiveReload,
  Meta,
  Outlet,
  Scripts,
  ScrollRestoration,
} from "@remix-run/react";
import { Analytics } from "@vercel/analytics/remix";

export default function App() {
  return (
    <html lang="en">
      <head>
        <meta charSet="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <Meta />
        <Links />
      </head>
      <body>
        <Analytics />
        <Outlet />
        <ScrollRestoration />
        <Scripts />
        <LiveReload />
      </body>
    </html>
  );
}
```

### JavaScript - `app/root.jsx`

```jsx
import {
  Links,
  LiveReload,
  Meta,
  Outlet,
  Scripts,
  ScrollRestoration,
} from "@remix-run/react";
import { Analytics } from "@vercel/analytics/remix";

export default function App() {
  return (
    <html lang="en">
      <head>
        <meta charSet="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <Meta />
        <Links />
      </head>
      <body>
        <Analytics />
        <Outlet />
        <ScrollRestoration />
        <Scripts />
        <LiveReload />
      </body>
    </html>
  );
}
```

---

## SvelteKit

### TypeScript - `src/routes/+layout.ts`

```ts
import { dev } from "$app/environment";
import { injectAnalytics } from "@vercel/analytics/sveltekit";

injectAnalytics({ mode: dev ? "development" : "production" });
```

### JavaScript - `src/routes/+layout.js`

```js
import { dev } from "$app/environment";
import { injectAnalytics } from "@vercel/analytics/sveltekit";

injectAnalytics({ mode: dev ? "development" : "production" });
```

---

## Nuxt

### TypeScript - `app.vue`

```vue
<script setup lang="ts">
import { Analytics } from '@vercel/analytics/nuxt';
</script>

<template>
  <Analytics />
  <NuxtPage />
</template>
```

### JavaScript - `app.vue`

```vue
<script setup>
import { Analytics } from '@vercel/analytics/nuxt';
</script>

<template>
  <Analytics />
  <NuxtPage />
</template>
```

---

## Astro

### TypeScript - `src/layouts/Base.astro`

```tsx
---
import Analytics from '@vercel/analytics/astro';
---

<html lang="en">
	<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>My Site</title>
    <Analytics />
	</head>
	<body>
		<slot />
  </body>
</html>
```

### JavaScript - `src/layouts/Base.astro`

```jsx
---
import Analytics from '@vercel/analytics/astro';
---

<html lang="en">
	<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>My Site</title>
    <Analytics />
	</head>
	<body>
		<slot />
  </body>
</html>
```

### Astro Adapter Config (Legacy < v1.4.0) - `astro.config.mjs`

```js
import { defineConfig } from "astro/config";
import vercel from "@astrojs/vercel/serverless";

export default defineConfig({
  output: "server",
  adapter: vercel({
    webAnalytics: {
      enabled: true, // set to false when using @vercel/analytics@1.4.0
    },
  }),
});
```

---

## Create React App

### TypeScript - `App.tsx`

```tsx
import { Analytics } from "@vercel/analytics/react";

export default function App() {
  return (
    <div>
      <h1>My App</h1>
      {/* Your app content */}
      <Analytics />
    </div>
  );
}
```

### JavaScript - `App.jsx`

```jsx
import { Analytics } from "@vercel/analytics/react";

export default function App() {
  return (
    <div>
      <h1>My App</h1>
      {/* Your app content */}
      <Analytics />
    </div>
  );
}
```

---

## Vue

### TypeScript - `src/App.vue`

```vue
<script setup lang="ts">
import { Analytics } from '@vercel/analytics/vue';
</script>

<template>
  <Analytics />
  <div id="app">
    <!-- Your app content -->
  </div>
</template>
```

### JavaScript - `src/App.vue`

```vue
<script setup>
import { Analytics } from '@vercel/analytics/vue';
</script>

<template>
  <Analytics />
  <div id="app">
    <!-- Your app content -->
  </div>
</template>
```

---

## Plain HTML

### `index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Site</title>
</head>
<body>
  <!-- Your content -->
  
  <!-- Vercel Analytics -->
  <script>
    window.va = window.va || function () { (window.vaq = window.vaq || []).push(arguments); };
  </script>
  <script defer src="/_vercel/insights/script.js"></script>
</body>
</html>
```

---

## Other Frameworks (Vanilla JS)

### TypeScript - `main.ts`

```ts
import { inject } from "@vercel/analytics";

inject();
```

### JavaScript - `main.js`

```js
import { inject } from "@vercel/analytics";

inject();
```

---

## Custom Events (Pro/Enterprise Plans)

### Track Custom Events

```typescript
import { track } from '@vercel/analytics';

// Track a button click
function handleButtonClick() {
  track('button_click', { button_name: 'signup' });
}

// Track a form submission
function handleFormSubmit() {
  track('form_submit', { form_type: 'contact' });
}

// Track a purchase
function handlePurchase(amount: number) {
  track('purchase', { value: amount });
}
```

### React/Next.js Example

```tsx
import { track } from '@vercel/analytics';
import { Analytics } from '@vercel/analytics/react';

export default function MyComponent() {
  const handleClick = () => {
    track('cta_clicked', { location: 'hero' });
  };

  return (
    <>
      <button onClick={handleClick}>
        Sign Up Now
      </button>
      <Analytics />
    </>
  );
}
```

---

## Analytics Component Props

### Mode Configuration

```tsx
import { Analytics } from '@vercel/analytics/react';

// Development mode - logs events to console
<Analytics mode="development" />

// Production mode - sends events to Vercel
<Analytics mode="production" />

// Auto-detect based on environment
<Analytics mode={process.env.NODE_ENV === 'development' ? 'development' : 'production'} />
```

### Debug Mode

```tsx
import { Analytics } from '@vercel/analytics/react';

// Enable debug logging
<Analytics debug={true} />
```

### Before Send Hook

```tsx
import { Analytics } from '@vercel/analytics/react';

// Modify or filter events before sending
<Analytics 
  beforeSend={(event) => {
    // Don't track admin pages
    if (event.url.includes('/admin')) {
      return null;
    }
    return event;
  }}
/>
```

---

## Environment-Specific Configuration

### Next.js with Environment Variables

```tsx
import { Analytics } from '@vercel/analytics/next';

export default function RootLayout({ children }) {
  return (
    <html>
      <body>
        {children}
        <Analytics 
          mode={process.env.NODE_ENV}
          debug={process.env.NODE_ENV === 'development'}
        />
      </body>
    </html>
  );
}
```

---

## Deployment Commands

```bash
# Deploy to production
vercel deploy --prod

# Deploy to preview
vercel deploy

# Check deployment status
vercel ls

# View logs
vercel logs [deployment-url]
```

---

## Verification

### Check Network Request

Open browser DevTools → Network tab and look for:
```
Request URL: https://your-site.vercel.app/_vercel/insights/view
Status: 200 OK
Type: fetch
```

### Check Console (Debug Mode)

With debug enabled, you should see:
```
[Vercel Analytics] Pageview: /your-page
[Vercel Analytics] Event sent successfully
```

---

## Common Pitfalls

### ❌ Don't do this:

```jsx
// Don't add Analytics multiple times
function App() {
  return (
    <>
      <Header />
      <Analytics />  // ❌
      <Main />
      <Analytics />  // ❌ Duplicate!
      <Footer />
    </>
  );
}

// Don't forget to import
function App() {
  return <Analytics />; // ❌ Not imported!
}

// Don't use wrong import path
import { Analytics } from '@vercel/analytics'; // ❌ Generic path
```

### ✅ Do this:

```jsx
import { Analytics } from '@vercel/analytics/react'; // ✅ Framework-specific

function App() {
  return (
    <>
      <Header />
      <Main />
      <Footer />
      <Analytics /> // ✅ Added once at the root
    </>
  );
}
```

---

## Package.json Scripts

Add these helpful scripts to your `package.json`:

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint",
    "deploy": "vercel deploy --prod",
    "deploy:preview": "vercel deploy"
  }
}
```

---

## Additional Resources

- [Full Guide](VERCEL_WEB_ANALYTICS_GUIDE.md)
- [Quick Start](VERCEL_ANALYTICS_QUICK_START.md)
- [Implementation Checklist](VERCEL_ANALYTICS_IMPLEMENTATION_CHECKLIST.md)
- [Vercel Analytics Docs](https://vercel.com/docs/analytics)
- [Package on npm](https://www.npmjs.com/package/@vercel/analytics)

---

**Last Updated:** January 2026  
**Package Version:** @vercel/analytics@latest  
**Minimum Required Version:** @vercel/analytics@1.0.0

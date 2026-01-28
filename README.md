# Vercel Web Analytics - Complete Implementation Guide

This repository contains comprehensive documentation and guides for implementing Vercel Web Analytics in your projects.

## 📚 Documentation Files

### 1. [VERCEL_WEB_ANALYTICS_GUIDE.md](VERCEL_WEB_ANALYTICS_GUIDE.md)
**Complete Implementation Guide**
- Detailed prerequisites and setup instructions
- Framework-specific integration guides for all supported platforms
- Step-by-step deployment instructions
- Dashboard usage and data viewing
- Comprehensive coverage of all frameworks

### 2. [VERCEL_ANALYTICS_QUICK_START.md](VERCEL_ANALYTICS_QUICK_START.md)
**Quick Start Guide**
- TL;DR - Get started in 3 steps
- Quick reference for each framework
- Common issues and solutions
- Framework comparison table
- Perfect for experienced developers who need quick reference

### 3. [VERCEL_ANALYTICS_IMPLEMENTATION_CHECKLIST.md](VERCEL_ANALYTICS_IMPLEMENTATION_CHECKLIST.md)
**Implementation Checklist**
- Step-by-step checklist format
- Checkboxes to track progress
- Verification steps
- Troubleshooting section
- Ideal for ensuring nothing is missed during implementation

### 4. [VERCEL_ANALYTICS_CODE_EXAMPLES.md](VERCEL_ANALYTICS_CODE_EXAMPLES.md)
**Code Examples Reference**
- Ready-to-copy code snippets for all frameworks
- TypeScript and JavaScript examples
- Custom events implementation
- Configuration options
- Common pitfalls and best practices

---

## 🚀 Quick Start

### For Beginners
1. Start with [VERCEL_WEB_ANALYTICS_GUIDE.md](VERCEL_WEB_ANALYTICS_GUIDE.md) - read the full guide
2. Follow [VERCEL_ANALYTICS_IMPLEMENTATION_CHECKLIST.md](VERCEL_ANALYTICS_IMPLEMENTATION_CHECKLIST.md) - check off each step
3. Reference [VERCEL_ANALYTICS_CODE_EXAMPLES.md](VERCEL_ANALYTICS_CODE_EXAMPLES.md) - copy the code for your framework

### For Experienced Developers
1. Check [VERCEL_ANALYTICS_QUICK_START.md](VERCEL_ANALYTICS_QUICK_START.md) - 3-step setup
2. Copy code from [VERCEL_ANALYTICS_CODE_EXAMPLES.md](VERCEL_ANALYTICS_CODE_EXAMPLES.md)
3. Deploy and verify

---

## 📦 Supported Frameworks

✅ **Next.js** (App Router & Pages Router)  
✅ **Remix**  
✅ **SvelteKit**  
✅ **Nuxt**  
✅ **Astro**  
✅ **React** (Create React App)  
✅ **Vue**  
✅ **Plain HTML**  
✅ **Other Frameworks** (via inject function)

---

## 🎯 What is Vercel Web Analytics?

Vercel Web Analytics is a privacy-friendly, lightweight analytics solution that provides:

- **Real-time visitor tracking** - See who's visiting your site now
- **Page view analytics** - Understand which pages are most popular
- **Traffic sources** - Know where your visitors come from
- **Device & location data** - Understand your audience better
- **Zero configuration** - No cookie consent required (GDPR/CCPA compliant)
- **Fast & lightweight** - Minimal impact on site performance
- **Custom events** (Pro/Enterprise) - Track specific user interactions

---

## 📋 Basic Implementation Steps

### 1. Enable Analytics
- Go to [Vercel Dashboard](https://vercel.com/dashboard)
- Select your project → Analytics tab → Enable

### 2. Install Package
```bash
npm i @vercel/analytics
```

### 3. Add to Your App
Choose your framework and add the appropriate code:

**Next.js (App Router):**
```tsx
import { Analytics } from "@vercel/analytics/next";

export default function RootLayout({ children }) {
  return (
    <html>
      <body>
        {children}
        <Analytics />
      </body>
    </html>
  );
}
```

**Other frameworks:** See [VERCEL_ANALYTICS_CODE_EXAMPLES.md](VERCEL_ANALYTICS_CODE_EXAMPLES.md)

### 4. Deploy
```bash
vercel deploy --prod
```

### 5. Verify
- Visit your site
- Check DevTools → Network for `/_vercel/insights/view` request
- View data in Vercel Dashboard → Analytics tab

---

## 🔍 Key Features

### Privacy-First
- No cookies used
- GDPR & CCPA compliant out of the box
- No personal data collected
- No tracking across sites

### Performance
- Lightweight script (~1KB)
- Async loading - doesn't block page rendering
- Edge-optimized for global performance

### Data & Insights
- **Real-time visitor count**
- **Page views** by URL
- **Top pages** ranking
- **Referral sources** (where visitors come from)
- **Devices** (desktop vs mobile vs tablet)
- **Browsers** used
- **Countries** visitors are from
- **Custom events** (Pro/Enterprise plans)

---

## 📊 Dashboard Features

Once deployed, your Vercel Analytics dashboard shows:

1. **Overview**
   - Total page views
   - Unique visitors
   - Average session duration
   - Bounce rate

2. **Top Pages**
   - Most visited pages
   - Views per page
   - Trend over time

3. **Traffic Sources**
   - Direct traffic
   - Referrals
   - Social media
   - Search engines

4. **Audience**
   - Geographic distribution
   - Device breakdown
   - Browser stats
   - Operating systems

5. **Custom Events** (Pro/Enterprise)
   - Track button clicks
   - Form submissions
   - Purchases
   - Any custom interaction

---

## 🎓 Which Document Should I Use?

| Your Situation | Recommended Document |
|----------------|---------------------|
| First time implementing | [Complete Guide](VERCEL_WEB_ANALYTICS_GUIDE.md) + [Checklist](VERCEL_ANALYTICS_IMPLEMENTATION_CHECKLIST.md) |
| Experienced with analytics | [Quick Start](VERCEL_ANALYTICS_QUICK_START.md) |
| Need code to copy-paste | [Code Examples](VERCEL_ANALYTICS_CODE_EXAMPLES.md) |
| Want systematic approach | [Checklist](VERCEL_ANALYTICS_IMPLEMENTATION_CHECKLIST.md) |
| Need framework comparison | [Quick Start](VERCEL_ANALYTICS_QUICK_START.md) |
| Implementing custom events | [Code Examples](VERCEL_ANALYTICS_CODE_EXAMPLES.md) |

---

## 🛠️ Installation

The package works with all major package managers:

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

## 🔧 Framework-Specific Import Paths

| Framework | Import Path |
|-----------|------------|
| Next.js | `@vercel/analytics/next` |
| Remix | `@vercel/analytics/remix` |
| SvelteKit | `@vercel/analytics/sveltekit` |
| Nuxt | `@vercel/analytics/nuxt` |
| Astro | `@vercel/analytics/astro` |
| React (CRA) | `@vercel/analytics/react` |
| Vue | `@vercel/analytics/vue` |
| Other | `@vercel/analytics` |

---

## ✅ Verification Checklist

After implementation, verify:

- [ ] Analytics enabled in Vercel Dashboard
- [ ] Package installed (`@vercel/analytics` in package.json)
- [ ] Code added to correct file for your framework
- [ ] Build completes without errors
- [ ] Deployed to Vercel
- [ ] `/_vercel/insights/view` request visible in browser DevTools
- [ ] Data appearing in Vercel Dashboard (may take a few minutes)

---

## 🐛 Troubleshooting

### Analytics not showing data?
1. Ensure Analytics is enabled in Vercel Dashboard
2. Verify deployment to Vercel (not localhost)
3. Check for `/_vercel/insights/view` request in Network tab
4. Wait a few minutes for data to appear
5. Disable ad blockers temporarily

### Script not loading?
1. Confirm correct import path for your framework
2. Verify component is actually rendered
3. Check browser console for errors
4. Ensure using Vercel-hosted domain

### Route tracking not working?
1. Use framework-specific import (not generic `@vercel/analytics`)
2. Check framework is supported for route tracking
3. Verify using router/navigation from your framework

---

## 📚 Additional Resources

### Official Documentation
- [Vercel Analytics Documentation](https://vercel.com/docs/analytics)
- [Vercel Analytics Package on npm](https://www.npmjs.com/package/@vercel/analytics)
- [Vercel Dashboard](https://vercel.com/dashboard)

### Pricing & Limits
- **Hobby (Free):** Up to 2,500 events/month
- **Pro:** Up to 100,000 events/month
- **Enterprise:** Custom limits + advanced features

[View detailed pricing](https://vercel.com/docs/analytics/limits-and-pricing)

### Support
- [Vercel Community Discussions](https://github.com/vercel/vercel/discussions)
- [Vercel Support](https://vercel.com/support)
- [Status Page](https://www.vercel-status.com/)

---

## 🤝 Contributing

Found an issue or want to improve the documentation? Please feel free to:
1. Open an issue describing the problem
2. Submit a pull request with improvements
3. Share feedback on what's missing or unclear

---

## 📄 License

This documentation is provided as-is for educational and implementation purposes.

Vercel Web Analytics and the `@vercel/analytics` package are provided by Vercel Inc.
See [Vercel's Terms of Service](https://vercel.com/legal/terms) for official licensing.

---

## 🎉 Get Started Now!

Choose your path:

1. **Comprehensive approach:** Start with [Complete Guide](VERCEL_WEB_ANALYTICS_GUIDE.md)
2. **Quick implementation:** Jump to [Quick Start](VERCEL_ANALYTICS_QUICK_START.md)
3. **Systematic approach:** Follow the [Checklist](VERCEL_ANALYTICS_IMPLEMENTATION_CHECKLIST.md)
4. **Just the code:** Copy from [Code Examples](VERCEL_ANALYTICS_CODE_EXAMPLES.md)

Happy tracking! 📊✨

---

**Last Updated:** January 2026  
**Package Version:** @vercel/analytics@latest  
**Documentation Version:** 1.0.0

# CardioThinkLab — Website Performance & Infrastructure Upgrade
### Project Presentation Deck

---

## SLIDE 1 — Title Slide

**CardioThinkLab**
Website Performance & Infrastructure Upgrade

*Transforming the Digital Foundation for a Leading Cardiovascular Science Platform*

Prepared by: [Your Team Name]
Date: March 2026

---

## SLIDE 2 — Agenda

1. Project Context
2. Where We Started — Initial Assessment
3. Our Approach
4. What We Delivered
5. Performance Results — Before & After
6. Multilingual Expansion
7. Ongoing Improvements
8. Summary & Next Steps

---

## SLIDE 3 — Project Context

### Background

- CardioThinkLab serves as a trusted scientific resource for healthcare professionals in the cardiovascular space
- As the platform's content library and audience grew, the underlying website infrastructure needed modernisation to match the platform's ambitions
- Our engagement focused on three pillars:

  **1. Performance** — Make the site fast and responsive
  **2. Stability** — Resolve technical issues and reduce risk
  **3. Scale** — Lay the groundwork for multilingual expansion and future growth

---

## SLIDE 4 — Where We Started — Initial Assessment

### Site Performance (November 2025 — GTmetrix Report)

| Metric | Value | Industry Target |
|---|---|---|
| Performance Score | 52 / 100 | 90+ |
| Largest Contentful Paint (LCP) | 12.4 sec | ≤ 2.5 sec |
| Time to First Byte (TTFB) | 10.1 sec | ≤ 0.6 sec |
| Fully Loaded Time | 18.4 sec | ≤ 3 sec |
| Total Page Size | 5.30 MB | ≤ 2 MB |
| Total Requests | 164 | ≤ 50 |
| Total Blocking Time | 140 ms | ≤ 200 ms |

### Key Observations

- Server response was delayed — the browser waited ~10 seconds before receiving any content
- Page weight and request count had grown significantly over time
- No caching layers (object cache or full-page cache) were in place
- Several legacy themes and plugins were adding overhead
- PHP version and WordPress core needed updates

> *These are common patterns in content-rich platforms that have scaled organically — the foundation simply needed to be strengthened to support the next phase of growth.*

---

## SLIDE 5 — Our Approach

### A Structured, Low-Risk Improvement Plan

We took a phased approach to minimise disruption while maximising impact:

**Phase 1 — Technical Cleanup**
- Remove inactive themes and unused plugins
- Update WordPress core, all plugins, and PHP version
- Resolve PHP errors, warnings, and notices

**Phase 2 — Performance Optimisation**
- Enable Memcached for object caching
- Enable Varnish for full-page caching
- Switch to asynchronous content loading
- Reduce duplicate database queries

**Phase 3 — Structural Improvements**
- Implement multilingual subdirectory URL architecture (WPML)
- Create proper sitemaps and hreflang configuration
- Build custom 404 error template
- Fix platform-specific issues (YouTube embeds on iOS)

**Phase 4 — Ongoing Refinement**
- UI refresh (in progress)
- Continued monitoring and optimisation

---

## SLIDE 6 — What We Delivered: Technical Cleanup

### A Leaner, More Secure Foundation

| Action | Impact |
|---|---|
| Removed inactive & broken themes | Reduced system clutter and potential conflicts |
| Cleaned unused plugins | Removed bloat, reduced attack surface |
| Updated WordPress core + all plugins | Latest security patches and compatibility |
| Upgraded to PHP 8.4 | Better performance, modern language features, long-term support |
| Fixed all PHP errors, warnings & notices | Clean error logs, fewer unexpected behaviours |

### Why This Matters

- A cleaner codebase is easier to maintain, faster to load, and more secure
- Plugin and theme bloat is one of the most common causes of WordPress performance degradation
- PHP 8.4 alone delivers measurable speed improvements over older versions

---

## SLIDE 7 — What We Delivered: Performance Optimisation

### Making Every Millisecond Count

**Memcached (Object Cache) — Enabled**
- Frequently accessed database results are now served from memory
- Eliminates redundant database queries on every page load

**Varnish Cache (Full Page Cache) — Enabled**
- Entire pages are served from cache without hitting the application server
- Dramatically reduces Time to First Byte (TTFB)

**Asynchronous Content Loading**
- Post tiles and non-critical content now load asynchronously
- Users see meaningful content faster while the rest loads in the background

**Database Query Optimisation**
- Identified and eliminated duplicate queries
- Results are cached using Memcached when available

**Additional Fixes**
- Fixed YouTube embed rendering on iOS devices
- Resolved deployment and infrastructure issues in collaboration with the Roche Infra Team

---

## SLIDE 8 — Performance Results: Before & After

### The Transformation

| Metric | BEFORE (Nov 2025) | AFTER — Desktop (Mar 2026) | Improvement |
|---|---|---|---|
| **Performance Score** | 52 / 100 | **98 / 100** | +88% |
| **LCP (Lab)** | 12.4 sec | **1.0 sec** | 92% faster |
| **TTFB** | 10.1 sec | **< 0.6 sec** | 94% faster |
| **Fully Loaded Time** | 18.4 sec | **~1–2 sec** | 90%+ faster |
| **Total Blocking Time** | 140 ms | **0 ms** | 100% reduction |
| **Page Size** | 5.30 MB | Significantly reduced | — |
| **Total Requests** | 164 | Significantly reduced | — |

### Mobile Performance (After — Mar 2026)

| Metric | Lab Value | Field Value (Real Users) |
|---|---|---|
| Performance Score | 83 / 100 | — |
| LCP | 3.9 sec | **2.4 sec** |
| FCP | 2.7 sec | **1.6 sec** |
| Total Blocking Time | 0 ms | — |
| CLS | 0 | 0.14 |

> *Desktop LCP improved from 12.4 seconds to 1.0 second — a 12x improvement that now comfortably meets Google's "Good" threshold of 2.5 seconds.*

---

## SLIDE 9 — What This Means in Practice

### For Healthcare Professionals Visiting CardioThinkLab

**Before:** A visitor would wait ~18 seconds for the page to fully load — with nothing visible on screen for the first 10 seconds.

**After:** The page loads in approximately 1 second on desktop. Content appears almost instantly.

### For Search Engine Visibility (SEO)

- Google uses Core Web Vitals (LCP, CLS, INP) as ranking signals
- Moving from "Poor" to "Good" LCP directly improves search discoverability
- Combined with proper multilingual sitemaps and hreflang tags, the site is now better positioned for organic reach across markets

### For Platform Reliability

- Clean error logs mean fewer unexpected issues
- Modern PHP and updated plugins reduce security vulnerabilities
- Caching layers protect the site during traffic spikes

---

## SLIDE 10 — Multilingual Expansion: WPML Live

### Building for a Global Audience

| Feature | Implementation |
|---|---|
| URL Structure | Subdirectory-based — cardiothinklab.com/ja/, /en/, /es/ |
| Sitemaps | Auto-generated per language (e.g., sitemap-ja.xml) |
| Hreflang Tags | Injected in `<head>` + included in sitemaps |
| Redirects | 301 redirects from query parameters (?lang=ja) to subdirectories (/ja/) |
| Translation Management | WPML String Translation (ready) + ACF integration (in progress) |

### What This Enables

- Clean, SEO-friendly subdirectory URLs for each language
- Search engines can correctly index and serve the right language version to users
- Scalable architecture — adding new languages is straightforward
- Japanese subdirectory is now live: cardiothinklab.com/ja/

---

## SLIDE 11 — Additional Quality Scores (After)

### Beyond Speed — A Healthier Website Overall

| Category | Desktop Score | Mobile Score |
|---|---|---|
| Performance | **98** | **83** |
| Accessibility | 85 | 84 |
| Best Practices | **92** | **96** |
| SEO | 85 | 85 |

### Areas Identified for Further Improvement

- **Accessibility:** Image alt attributes, link labels, colour contrast, ARIA roles
- **SEO:** Heading hierarchy, metadata refinements
- These are tracked and can be addressed in upcoming iterations

---

## SLIDE 12 — Ongoing & Next Steps

### In Progress

| Item | Status |
|---|---|
| UI Refresh — starting with the Home Page | In progress |
| Reported 404 issues (uploaded file URLs) | Fix to be determined |
| Unfixable PHP notices from third-party plugins | Reviewed — do not affect site function |
| DNS switch preparation | Completed with Roche Infra Team |

### Recommended Next Steps

- **Content & Editorial:** Centralised article repository, author page optimisation
- **Accessibility:** Address alt tags, contrast, ARIA labels to improve scores toward 90+
- **Monitoring:** Ongoing Core Web Vitals tracking as field data (CrUX) catches up to lab improvements
- **Content Delivery:** Consider Cloudflare caching layer for additional global performance gains

---

## SLIDE 13 — Summary

### At a Glance

| Area | Before | After | Impact |
|---|---|---|---|
| Performance Score | 52 | **98** | **+88%** |
| Page Load (Desktop) | 18.4s | **~1s** | **18x faster** |
| Largest Contentful Paint | 12.4s | **1.0s** | **12x faster** |
| Time to First Byte | 10.1s | **< 0.6s** | **17x faster** |
| PHP Version | Legacy | **8.4** | Latest LTS |
| Caching | None | **Memcached + Varnish** | Full stack |
| Multilingual | Not available | **WPML Live** | Subdirectory URLs (/ja/, /en/, /es/) |
| Error Logs | Multiple warnings | **Clean** | All resolved |

### Key Outcomes

- **Faster** — From an 18-second load to under 1 second on desktop; all Core Web Vitals now in Google's "Good" range
- **Cleaner** — Unused themes & plugins removed, all PHP errors resolved, modern tech stack (PHP 8.4)
- **Global-ready** — Multilingual infrastructure live with SEO-friendly subdirectory URLs, sitemaps, and hreflang tags
- **Resilient** — Dual caching layers (object + full-page) protect performance under traffic spikes
- **Future-proof** — Foundation in place for UI refresh, content expansion, and additional language rollouts

---

## SLIDE 14 — Thank You

**CardioThinkLab**
Website Performance & Infrastructure Upgrade

*Questions & Discussion*

[Your Team Name]
[Contact Information]

---

### APPENDIX — Detailed Metrics Reference

#### Before: GTmetrix Report (November 5, 2025)
- Test URL: prod.cardiothinklab.com
- Performance Score: 52%, Structure Score: 79%
- LCP: 12.4s, TBT: 140ms, CLS: 0.01
- Fully Loaded: 18.4s, Page Size: 5.30MB, Requests: 164
- Top Issues: Server response time (10.1s), render-blocking resources, enormous network payloads, critical request chaining

#### After: PageSpeed Insights — Desktop (March 19, 2026)
- Test URL: cardiothinklab.com
- Performance: 98, Accessibility: 85, Best Practices: 92, SEO: 85
- Lab — FCP: 0.7s, LCP: 1.0s, TBT: 0ms, Speed Index: 1.1s, CLS: 0.027
- Field (CrUX) — LCP: 3.4s, INP: 50ms, CLS: 0.11, FCP: 3.2s

#### After: PageSpeed Insights — Mobile (March 19, 2026)
- Performance: 83, Accessibility: 84, Best Practices: 96, SEO: 85
- Lab — FCP: 2.7s, LCP: 3.9s, TBT: 0ms, Speed Index: 2.9s, CLS: 0
- Field (CrUX) — LCP: 2.4s, INP: N/A, CLS: 0.14, FCP: 1.6s

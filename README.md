# Technical SEO Audit & Optimization Strategy

**Target Website:** https://easyask.liveblog365.com/wp/  
**Plugin Evaluated:** Yoast SEO (WordPress)  

---

## Audit Matrix

| Audit Metric | Status | Identified Technical Issue | Actionable Optimization Strategy | Yoast SEO / Plugin Implementation | Priority |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Website Assessment** | Action Required | Subdirectory path `/wp/` creates duplicate root path risk. | Canonicalize all `/wp/` URLs cleanly or migrate WordPress core to domain root. | Configure permanent site URLs in Yoast General Settings. | High |
| **Site Speed Optimization** | Needs Attention | High TTFB and uncompressed static assets on free hosting. | Minify CSS/JS files, leverage browser caching, convert images to WebP. | Integrate a lightweight caching plugin alongside Yoast. | High |
| **Mobile-Friendliness** | Passed | Responsive layout passes basic viewport scale checks. | Maintain touch target sizes above 48x48px for menu navigation. | Verify mobile viewports parse lightweight Yoast OpenGraph tags. | Medium |
| **Structured Data** | Action Required | Schema markup missing across main blog feeds and post items. | Implement explicit JSON-LD Schema (`WebSite`, `BlogPosting`). | Set up Organization and Default Post Schema in Yoast SEO > Settings > Schema. | High |
| **XML Sitemap Optimization** | Action Required | Missing default `sitemap_index.xml` file on default path. | Enable dynamic XML sitemap generation to ping crawlers automatically. | Toggle ON XML Sitemaps in Yoast SEO (`sitemap_index.xml`). | High |
| **Robots.txt Optimization** | Needs Attention | Missing customized `robots.txt` directive to block sensitive admin areas. | Add `Disallow: /wp/wp-admin/` while leaving `admin-ajax.php` accessible. | Create and edit `robots.txt` directly via Yoast SEO > Tools > File Editor. | High |
| **Canonicalization** | Action Required | Potential duplicate URL variations between HTTP/HTTPS and trailing slashes. | Implement self-referencing canonical tags on every page/post. | Yoast automatically handles self-referencing canonical tags on posts/pages. | High |
| **Dead & Broken Links** | Passed | No major broken links found on initial setup. | Set up periodic site crawling using Screaming Frog to catch 404s early. | Enable automatic redirect prompts when slugs change using Yoast. | Medium |
| **404 Error Page** | Needs Attention | Default 404 page lacks active site search or direct home navigation. | Customize `404.php` template with search bar and recent post links. | Ensure server responds with a hard 404 HTTP header on missing paths. | Medium |
| **301 & 302 Redirects** | Action Required | No redirect rules configured for old or deleted URL slugs. | Standardize all redirects to 301 (Permanent) to preserve link equity. | Manage 301 redirects directly through Yoast SEO Premium Redirect Manager. | High |
| **Code to Text Ratio** | Needs Attention | High code overhead relative to limited published post text. | Add rich content to posts to bring text-to-code ratio above 15%. | Write long-form post content directly in Gutenberg editor. | Low |

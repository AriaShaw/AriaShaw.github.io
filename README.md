# GitHub Pages → ariashaw.com Redirect Repository

This repository contains a minimal redirect site that permanently redirects all traffic from `ariashaw.github.io` to `ariashaw.com`.

## 🎯 Purpose

This redirect site ensures:
- **SEO weight transfer** from old domain to new domain
- **Seamless user experience** with instant redirects
- **Search engine compliance** using meta refresh + JavaScript redirects
- **Path preservation** - all URLs maintain their full paths on the new domain

## 📁 Repository Structure

```
github-pages-redirect/
├── index.html          # Homepage redirect
├── 404.html            # Wildcard redirect for all other pages
├── _config.yml         # Minimal Jekyll configuration
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## 🚀 Deployment Instructions

### Step 1: Rename Current Repository

1. Go to your current `ariashaw.github.io` repository on GitHub
2. Navigate to **Settings** → **General**
3. Scroll to **Repository name**
4. Rename to: `ariashaw-blog` (or any other name)
5. Click **Rename**

### Step 2: Create New Redirect Repository

1. On GitHub, click **New Repository**
2. Name it **exactly**: `ariashaw.github.io`
3. Set to **Public**
4. **DO NOT** initialize with README, .gitignore, or license
5. Click **Create repository**

### Step 3: Push Redirect Files

In your local terminal (in this folder):

```bash
# Initialize git repository
git init

# Add all files
git add .

# Commit
git commit -m "Initial redirect site setup"

# Add remote (replace with your actual GitHub username)
git remote add origin https://github.com/AriaShaw/ariashaw.github.io.git

# Push to main branch
git branch -M main
git push -u origin main
```

### Step 4: Enable GitHub Pages

1. Go to repository **Settings** → **Pages**
2. Under **Source**, select: **Deploy from a branch**
3. Branch: **main**, Folder: **/ (root)**
4. Click **Save**
5. Wait 1-2 minutes for deployment

### Step 5: Verify Redirects

Test the following URLs:

- `https://ariashaw.github.io/` → Should redirect to `https://ariashaw.com/`
- `https://ariashaw.github.io/odoo-backup-guide/` → Should redirect to `https://ariashaw.com/odoo-backup-guide/`
- `https://ariashaw.github.io/guides/deploy-odoo-ubuntu/` → Should redirect to `https://ariashaw.com/guides/deploy-odoo-ubuntu/`

## 📊 Google Search Console Migration

### Critical Step for SEO Weight Transfer

1. **Add New Property in Google Search Console**
   - Go to [Google Search Console](https://search.google.com/search-console)
   - Add property: `https://ariashaw.com`
   - Verify ownership

2. **Use Change of Address Tool**
   - In old property (`ariashaw.github.io`), go to **Settings** → **Change of Address**
   - Select new site: `ariashaw.com`
   - Submit the request
   - This tells Google to transfer rankings and index to the new domain

3. **Submit New Sitemap**
   - In `ariashaw.com` property, go to **Sitemaps**
   - Submit: `https://ariashaw.com/sitemap.xml`

4. **Monitor Transfer Progress**
   - Check **Coverage** report weekly
   - Monitor **Performance** to track ranking transfer
   - Expected timeline: 1-3 months for full transfer

## 🔍 How It Works

### Homepage Redirect (`index.html`)
- Uses `<link rel="canonical">` pointing to new domain
- Uses `<meta http-equiv="refresh">` for browser redirect
- Uses JavaScript `window.location.replace()` for instant redirect
- Includes `<meta name="robots" content="noindex, follow">` to tell search engines not to index this page

### Wildcard Redirect (`404.html`)
- Configured with Jekyll front matter: `permalink: /404.html`
- GitHub Pages serves this for any non-existent path
- JavaScript captures the full URL path and redirects to same path on `ariashaw.com`
- Preserves query parameters and URL fragments

### Example Flow:
```
User visits: https://ariashaw.github.io/guides/odoo-migration/
     ↓
GitHub Pages returns 404 (no such file)
     ↓
404.html is served
     ↓
JavaScript reads: window.location.pathname = "/guides/odoo-migration/"
     ↓
Redirects to: https://ariashaw.com/guides/odoo-migration/
```

## ⚠️ Important Notes

### SEO Considerations

- **Not true HTTP 301**: GitHub Pages doesn't support HTTP-level redirects
- **Google recognizes meta refresh**: As of 2024, Google treats well-implemented meta refresh + JavaScript redirects similarly to 301s for ranking transfer
- **Keep live for 6-12 months**: Maintain this redirect site for at least 6 months to ensure complete SEO weight transfer
- **Use Google Search Console Change of Address**: This is **critical** for fast ranking transfer

### Limitations

- **No HTTP 301**: This uses meta refresh + JavaScript, not server-level 301 redirects
- **JavaScript required**: Users with JavaScript disabled will see the fallback message
- **Not instantaneous**: SEO weight transfer takes 1-3 months even with optimal setup

### Alternatives (if you need true HTTP 301)

If you absolutely need HTTP 301 redirects, consider:
1. **Cloudflare Workers** (requires custom domain control)
2. **Netlify** (supports `_redirects` file with true 301s)
3. **Vercel** (supports redirects in `vercel.json`)

However, for `*.github.io` domains, you cannot use these services since you don't control the DNS.

## 📈 Expected SEO Timeline

Based on industry experience with Google Search Console Change of Address:

- **Week 1-2**: Google begins crawling redirect site
- **Week 2-4**: New domain starts appearing in search results
- **Month 1-2**: 50-70% of rankings transferred
- **Month 3-6**: 80-95% of rankings transferred
- **Month 6+**: Full transfer complete (99%+)

## 🛠️ Troubleshooting

### Redirect not working?
1. Check GitHub Pages deployment status in repository **Actions** tab
2. Verify files are in **root directory**, not a subfolder
3. Clear browser cache and try incognito mode
4. Check browser console for JavaScript errors

### Old URLs still showing in Google?
1. Verify Google Search Console Change of Address is submitted
2. Check that `ariashaw.com` has new sitemap submitted
3. Request indexing for key pages in new domain
4. Be patient - full transfer takes 1-3 months

### Getting 404 on GitHub Pages?
1. Check that repository name is **exactly** `ariashaw.github.io`
2. Verify GitHub Pages is enabled in Settings → Pages
3. Wait 2-3 minutes after pushing changes
4. Check repository is **Public**, not Private

## 📞 Support

If you encounter issues:
1. Check GitHub Pages [status page](https://www.githubstatus.com/)
2. Review GitHub Pages [documentation](https://docs.github.com/en/pages)
3. Test redirects in multiple browsers
4. Check JavaScript console for errors

## 📝 License

This redirect site is provided as-is for SEO migration purposes. Feel free to modify as needed.

---

**Last Updated**: 2025-10-25
**Migration Target**: https://ariashaw.com
**Repository**: https://github.com/AriaShaw/ariashaw.github.io

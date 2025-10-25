# Google Search Console Migration Checklist

This is a **critical step-by-step guide** for transferring SEO authority from `ariashaw.github.io` to `ariashaw.com` using Google Search Console's Change of Address tool.

## 🎯 Goal

Transfer **99% of SEO rankings and authority** from your old domain to your new domain in the fastest time possible (1-3 months instead of 6-12 months).

---

## 📋 Pre-Migration Checklist

Before starting the Google Search Console migration, ensure:

- [ ] ✅ New domain `ariashaw.com` is live and accessible
- [ ] ✅ All content from old site is available on new site
- [ ] ✅ URLs maintain the same structure (e.g., `/odoo-backup-guide/` → `/odoo-backup-guide/`)
- [ ] ✅ Redirect repository deployed to `ariashaw.github.io`
- [ ] ✅ Redirects are working (test 5-10 random URLs)

---

## 🚀 Step-by-Step Migration Process

### Phase 1: Verify Ownership of New Domain

#### Step 1.1: Add New Property to Google Search Console

1. Go to [Google Search Console](https://search.google.com/search-console)
2. Click the property selector (top left)
3. Click **+ Add Property**
4. Choose **URL prefix**: `https://ariashaw.com`
5. Click **Continue**

#### Step 1.2: Verify Ownership

Choose one of these verification methods:

**Option A: HTML File Upload (Recommended)**
1. Download the verification HTML file
2. Upload to your site root: `https://ariashaw.com/google[code].html`
3. Click **Verify**

**Option B: HTML Tag**
1. Copy the meta tag provided
2. Add to `<head>` section of your homepage
3. Deploy changes
4. Click **Verify**

**Option C: Google Analytics**
1. If you have Google Analytics installed on `ariashaw.com`
2. Select this option
3. Click **Verify**

#### Step 1.3: Confirm Verification
- ✅ You should see: "Ownership verified" message
- ✅ New property appears in your property list

---

### Phase 2: Submit New Sitemap

#### Step 2.1: Generate Sitemap (Already Done)

Your Jekyll site automatically generates `sitemap.xml` at:
```
https://ariashaw.com/sitemap.xml
```

Verify it's accessible by visiting this URL in your browser.

#### Step 2.2: Submit to Google Search Console

1. In Google Search Console, select **ariashaw.com** property
2. Navigate to **Sitemaps** (left sidebar)
3. Enter sitemap URL: `sitemap.xml`
4. Click **Submit**

#### Step 2.3: Monitor Sitemap Status
- Status should change to **Success** within 24 hours
- Check **Discovered URLs** count matches your site pages (~99+ pages)

---

### Phase 3: Use Change of Address Tool

⚠️ **This is the MOST IMPORTANT step for fast SEO transfer**

#### Step 3.1: Access Change of Address Tool

1. In Google Search Console, switch to **OLD property**: `ariashaw.github.io`
2. Navigate to **Settings** (gear icon, left sidebar)
3. Scroll to **Change of Address**
4. Click **Start the change of address**

#### Step 3.2: Complete the Change of Address Form

**Question 1: "Which site are you moving to?"**
- Select from dropdown: `https://ariashaw.com`
- (This only appears if you've verified ownership of the new domain)

**Question 2: "Is there a 301 redirect from the old site to the new site?"**
- ⚠️ Select **Yes** (even though it's meta refresh + JavaScript, not true 301)
- Google recognizes modern redirect methods

**Question 3: Confirmation**
- Review the migration details
- Click **Submit**

#### Step 3.3: Verify Submission
- ✅ You should see: "Change of address submitted"
- ✅ A banner appears at top of old property showing migration status

---

### Phase 4: Request Indexing for Key Pages

Speed up the transfer by manually requesting indexing for your most important pages.

#### Step 4.1: Identify Top 10-20 Pages

From your old Google Analytics or Search Console, identify:
- Homepage
- Top 5 blog posts by traffic
- Top 5 PSEO pages
- Key conversion pages (products, downloads)

#### Step 4.2: Request Indexing

For each important page:

1. In **ariashaw.com** property, go to **URL Inspection** (top search bar)
2. Enter the **new URL**: `https://ariashaw.com/odoo-backup-guide/`
3. Click **Test Live URL**
4. Wait for crawl to complete
5. Click **Request Indexing**
6. Repeat for other key pages

⚠️ **Limit**: You can request ~10 URLs per day

---

### Phase 5: Update External Links (Optional but Recommended)

#### Step 5.1: Find Backlinks

1. In old property (`ariashaw.github.io`), go to **Links** (left sidebar)
2. Click **External links**
3. Export the list of linking domains

#### Step 5.2: Contact High-Value Linkers

For top 10-20 linking sites:
1. Identify contact email (use Hunter.io or manual search)
2. Send polite email requesting link update:

**Email Template:**
```
Subject: Quick Update - Domain Migration to ariashaw.com

Hi [Name],

I noticed you linked to our guide on [Topic] at:
https://ariashaw.github.io/[page]

We recently migrated to a new domain for better performance.
Could you update the link to:
https://ariashaw.com/[page]

The old link still works (redirects automatically), but updating
helps ensure the best user experience.

Thanks!
[Your Name]
```

---

## 📊 Monitoring & Tracking

### Week 1-2: Initial Crawling

**What to Monitor:**
- [ ] Coverage Report (new domain): Pages being indexed
- [ ] Performance Report (old domain): Traffic starting to decline
- [ ] Performance Report (new domain): Impressions starting to appear

**Expected Behavior:**
- Old domain traffic: 100% → 95%
- New domain traffic: 0% → 5%

### Week 3-4: Transition Phase

**What to Monitor:**
- [ ] Coverage: New domain indexed pages increasing
- [ ] Performance: Clicks transitioning to new domain
- [ ] Search appearance: New domain URLs appearing in results

**Expected Behavior:**
- Old domain traffic: 95% → 70%
- New domain traffic: 5% → 30%

### Month 2-3: Active Transfer

**What to Monitor:**
- [ ] Performance comparison: Old vs new domain traffic
- [ ] Rankings: Track top keywords in new domain
- [ ] CTR: Should stabilize as new URLs replace old in SERPs

**Expected Behavior:**
- Old domain traffic: 70% → 30%
- New domain traffic: 30% → 70%

### Month 3-6: Final Transfer

**What to Monitor:**
- [ ] Final ranking stabilization
- [ ] Old domain nearly zero traffic
- [ ] New domain at full authority

**Expected Behavior:**
- Old domain traffic: 30% → 5%
- New domain traffic: 70% → 95%

---

## 🎯 Key Performance Indicators (KPIs)

### Track These Metrics Weekly

Create a spreadsheet with these columns:

| Date | Old Domain Clicks | New Domain Clicks | Total Clicks | Transfer % |
|------|-------------------|-------------------|--------------|------------|
| Oct 25 | 1000 | 0 | 1000 | 0% |
| Nov 1 | 950 | 50 | 1000 | 5% |
| Nov 8 | 850 | 150 | 1000 | 15% |
| ... | ... | ... | ... | ... |

**Formula for Transfer %:**
```
Transfer % = (New Domain Clicks / Total Clicks) × 100
```

**Success Benchmark:**
- Month 1: 20-30% transfer
- Month 2: 50-70% transfer
- Month 3: 80-95% transfer
- Month 6: 95-99% transfer

---

## ⚠️ Common Issues & Solutions

### Issue 1: "Change of Address option is greyed out"

**Cause:** New domain not verified or redirects not working

**Solution:**
1. Verify new domain ownership in GSC
2. Test redirects from old domain
3. Wait 24 hours after verification
4. Try again

### Issue 2: "Google says redirects not detected"

**Cause:** Google's crawler may not recognize meta refresh

**Solution:**
1. Ensure `<link rel="canonical">` points to new domain
2. Add `<meta name="robots" content="noindex, follow">`
3. Test redirects in incognito mode
4. Submit anyway - Google will still transfer (slower)

### Issue 3: "Traffic dropped significantly during migration"

**Cause:** Normal temporary fluctuation during domain change

**Solution:**
1. Don't panic - this is normal
2. Check Google Search Console for crawl errors
3. Ensure new sitemap is submitted
4. Request indexing for top pages
5. Wait - recovery typically takes 2-4 weeks

### Issue 4: "Old domain URLs still showing in Google after 2 months"

**Cause:** Google hasn't finished reindexing

**Solution:**
1. Check Change of Address status in GSC
2. Request indexing for pages still showing old URLs
3. Ensure redirects are still working
4. Be patient - can take 3-6 months for complete replacement

---

## 📅 Timeline Summary

| Timeframe | Action | Expected Result |
|-----------|--------|-----------------|
| **Day 1** | Deploy redirects + Submit Change of Address | Google acknowledges migration |
| **Week 1-2** | Submit sitemap + Request indexing | New domain starts appearing |
| **Week 3-4** | Monitor traffic shift | 20-30% traffic transferred |
| **Month 2** | Continue monitoring | 50-70% traffic transferred |
| **Month 3** | Check ranking parity | 80-95% traffic transferred |
| **Month 6** | Final audit | 95-99% complete transfer |
| **Month 12** | Optional: Remove old redirects | Migration complete |

---

## ✅ Post-Migration Checklist

After 6 months, verify:

- [ ] New domain receives 95%+ of previous traffic
- [ ] Top keywords rank equally or better on new domain
- [ ] Old domain traffic is <5%
- [ ] No significant ranking drops
- [ ] Backlinks updated (or still redirecting)
- [ ] Analytics tracking working correctly
- [ ] Conversion rates maintained or improved

---

## 📞 Need Help?

If you encounter issues:

1. **Google Search Console Help**: [https://support.google.com/webmasters](https://support.google.com/webmasters)
2. **Search Central Community**: [https://support.google.com/webmasters/community](https://support.google.com/webmasters/community)
3. **Check Migration Guide**: [Google's official site move guide](https://developers.google.com/search/docs/advanced/crawling/site-move-with-url-changes)

---

**Last Updated**: 2025-10-25
**Migration**: ariashaw.github.io → ariashaw.com
**Expected Completion**: February 2026 (3 months from start)

# GitHub Actions Workflows

This directory contains GitHub Actions workflows for automated testing and quality assurance.

## link-check.yml

**Purpose:** Validates all links in documentation previews on ReadTheDocs.

**Triggers:**
- Pull requests opened, synchronized, or reopened against `main` branch

**What it does:**
1. **Waits for ReadTheDocs Preview:** Monitors the ReadTheDocs build process and waits for the PR preview to become available
2. **Runs Link Checker:** Uses [muffet](https://github.com/raviqqe/muffet) to crawl all pages and validate both internal and external links
3. **Reports Results:** Comments on the PR with detailed results and uploads full logs as artifacts
4. **Fails PR if broken links found:** Prevents merging documentation with broken links

**Configuration:**
- **Timeout:** 15 minutes total (10 minutes to wait for ReadTheDocs + 5 minutes for link checking)
- **Excluded domains:** Social media sites (LinkedIn, Twitter/X, Facebook, Discord) that often block crawlers
- **Rate limiting:** 10 requests/second to be respectful to external sites
- **User agent:** Identifies as a link checker to external sites

**ReadTheDocs URL Pattern:**
The workflow constructs preview URLs using the pattern:
```
https://wafer-space--{PR_NUMBER}.org.readthedocs.build/en/{PR_NUMBER}/
```

**Artifacts:**
- Full muffet output is saved as workflow artifacts for 30 days
- Includes detailed information about any broken links found

**Benefits:**
- **Prevents broken links:** Catches broken links before they reach main branch
- **Validates external references:** Ensures external documentation links remain valid
- **Improves user experience:** Users won't encounter 404s in documentation
- **Automated quality assurance:** No manual link checking required

**Example Results:**
- ✅ **PASSED:** All links are valid, PR can be merged
- ❌ **FAILED:** Broken links found, detailed report provided in PR comment

**Troubleshooting:**
- If ReadTheDocs preview doesn't load within 10 minutes, check ReadTheDocs build status
- If external links fail intermittently, they may be temporarily unavailable or blocking crawlers
- Check the full muffet output in artifacts for detailed error information
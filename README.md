# GitHub Trending Repo Radar

## Purpose
Create a weekly, public-link-ready report of trending GitHub repositories, especially AI/agent/devtool/software-infrastructure repos, ranked by recent star growth and translated into practical recommendations for Alej's systems.

## Current prototype
- Live public URL: https://adsaver-labs.github.io/github-trending-repo-radar/
- Static source: `site/index.html`
- GitHub Pages published copy: `docs/index.html`
- Sample data: `data/weekly-2026-07-04-sample.json`
- Source used for prototype: GitHub Trending weekly public page.

## Public link strategy — free and non-expiring by default
Best options:

1. **GitHub Pages** — recommended first
   - Free for public repositories.
   - Stable URL: `https://<org-or-user>.github.io/<repo>/`
   - No expiry as long as the repo exists.
   - Good fit for public repo-radar archive pages.

2. **Cloudflare Pages** — recommended if we want nicer deploy flow/custom domain later
   - Free tier is enough for static pages.
   - Stable project URL plus optional custom domain.
   - Good fit once we want polished public reports.

3. **Agency website blog** — later
   - Good for SEO/content once the agency website is ready.
   - We can republish each weekly radar as a blog post, but keep GitHub Pages/Cloudflare as the canonical archive.

Avoid:
- Temporary share links that expire.
- Private local-only links if Alej needs access from phone/anywhere.
- Publishing to the agency site before the brand/site is ready.

## Weekly workflow
1. Fetch candidate repos from GitHub Trending + GitHub search/API where available.
2. Normalize fields: repo, URL, stars gained, total stars, language, topic, description.
3. Score by star velocity + relevance to Alej's systems + repo quality signals.
4. Produce a top 20 report; expand to 30/50 if the week has enough signal.
5. For each promising repo: classify as Watch / Study / Security Review / Sandbox Candidate / Adoption Proposal.
6. No repo code is installed or executed without SkillSpector/security gate and Alej approval.

## Self-education loop
This radar should become Dexter's weekly school subject:
- Learn: read public docs/README/release notes.
- Compare: map the repo against our current tools and workflows.
- Extract: save reusable patterns, UX ideas, architecture choices, prompts, and safety lessons.
- Apply carefully: propose changes; only implement after approval when production/infrastructure is affected.
- Remember: update project notes/skills/memory with durable lessons.

## Next milestones
- Build `scripts/build-weekly-radar.py` to generate JSON + HTML automatically.
- Add visual screenshots/logos where allowed.
- Create archive page by week.
- Decide publishing target: GitHub Pages vs Cloudflare Pages vs future agency blog.

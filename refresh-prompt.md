# FreeMoneyIQ.com — Content Refresh Instructions

This file contains the site-specific rules for refreshing FreeMoneyIQ calculator pages.
The Universal Content Refresh Agent reads this file each run.

---

## SITE CONTEXT

FreeMoneyIQ (https://freemoneyiq.com) is a free finance calculator hub with 6 tools:
Mortgage, Loan Payoff, Savings Goal, Freelancer Rate, Compound Interest, Tax Withholding.
Monetized via Google AdSense (finance niche, high CPC). SEO and Google AI Overview (AIO)
optimization is the primary goal of each refresh.

---

## RESEARCH STEP

Before rewriting anything, use web_search to find:
- Top Reddit, Quora, or social media questions about today's topic (e.g. "reddit mortgage questions 2026")
- Recent news or changes relevant to the topic (rate changes, tax law updates, Fed decisions, etc.)
- Common pain points or confusion users have around the topic
- "People Also Ask" (PAA) style questions from current Google search trends

---

## WHAT TO UPDATE EACH RUN

### 1. Quick Answer Blurb
Immediately after the opening `<div class="content-section">` tag, add or update a short
2–3 sentence paragraph:

```html
<p class="quick-answer" style="background:#f0f7ff; border-left:4px solid #1a6cf6; padding:12px 16px; border-radius:6px; font-size:0.95rem; margin-bottom:20px;">
  [Direct answer to the page's core question in plain language.]
</p>
```

Google AI Overviews pull these verbatim. Make them count.

### 2. Content Section Paragraphs
Rewrite the 3 educational paragraphs inside `.content-section`. Keep the HTML structure
identical — only update the text. Weave in current 2026 data, rate changes, or news.

### 3. FAQ Answers
Rewrite all 5 FAQ answers inside `.faq-item`. Format rules:
- 2–3 sentences max — "snackable" enough for AI Overviews and featured snippets to quote
- Lead with the direct answer first, explanation second
- Use specific numbers where possible (e.g. "4.5% APY", "$15,000 standard deduction")
- Each answer must be self-contained — readable without surrounding context

### 4. Sitemap lastmod
Update the `<lastmod>` date for this page in sitemap.xml to today's date (YYYY-MM-DD).

### 5. Subtitle
Update the visible subtitle inside `.calc-panel .subtitle` to include ` · Updated [Month YYYY]`
at the end (e.g. "Free Mortgage Calculator · Updated June 2026").

---

## GIT COMMIT FORMAT

```
Julie: refresh [page-file-name] content + AIO - [YYYY-MM-DD]
```

Example: `Julie: refresh mortgage-calculator.html content + AIO - 2026-06-01`

Only stage the updated page file and sitemap.xml:
```
git add [page].html sitemap.xml
```

---

## AIO OPTIMIZATION RULES

- Quick Answer blurb = 2–3 sentences, plain language, directly answers the #1 question
- FAQ answers are self-contained — readable as standalone snippets without surrounding context
- Use numbers and specifics wherever possible — AI Overviews prefer factual, specific answers
- Lead each FAQ answer with the direct answer first, explanation second
- Target current PAA (People Also Ask) questions from Google search trends

---

## WHAT NEVER CHANGES

- Calculator logic (JavaScript)
- Form inputs or calculator UI
- CSS styles
- Navigation or footer
- Structured data / schema JSON
- Number of content sections (always 3) or FAQs (always 5)
- The overall HTML structure — only update text inside existing tags

---

## FALLBACK

If web_search returns nothing useful, do a light rewrite using current financial best
practices for 2026. Don't skip the refresh — stale content is the enemy.

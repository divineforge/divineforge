# DivineForge Development Plan
**Last Updated:** 2024-11-20
**Owner:** William Cheong
**Purpose:** Strategic roadmap and implementation guide for DivineForge.com transformation

---

## 🎯 Mission & Vision

**Mission:** Build AI-powered products and tools while publicly documenting the journey from corporate IT architect to independent builder.

**Vision:** Create $5K/month in revenue by December 2025 through digital products, enabling reduced corporate dependence.

**Core Narrative:** "Software architect in Malaysia escaping corporate banking constraints by building revenue streams with AI assistance. Everything documented, open, and honest."

---

## 📊 Current State Assessment

### What Exists
- **Domain:** divineforge.com (live)
- **Tech Stack:** Hugo static site generator + Cloudflare Pages
- **Status:** Minimal content, poetic placeholder, zero revenue
- **Owner Identity:** William Weelau CHEONG (personal brand)

### What's Working
- Hugo + Cloudflare Pages = fast, free, reliable
- Git-based workflow = simple deployment
- Domain established with clear name

### What Needs Change
- Content strategy (portfolio → building in public)
- Site structure (add key sections)
- Value proposition (unclear → specific)
- Revenue mechanisms (none → multiple streams)
- Brand positioning (vague → precise)

---

## 🏗️ Technical Architecture

### Frontend (Keep As-Is)
```
Hugo Static Site Generator
├── Markdown content in Git
├── Fast build times (milliseconds)
├── Deployed via Cloudflare Pages
├── Auto-deploy on git push
└── Free hosting, global CDN, SSL included
```

**Decision:** DO NOT migrate to Astro/Next.js/other. Hugo works perfectly.

### Backend Services (Add AWS Serverless)
```
AWS Services (using available credits)
├── Lambda Functions
│   ├── Newsletter subscription handler
│   ├── Contact form processor
│   ├── Digital product delivery
│   └── Analytics/tracking
├── API Gateway (HTTP endpoints for Lambda)
├── DynamoDB (subscriber data, product keys)
├── SES (email automation, no third-party costs)
├── S3 (digital product file storage)
└── CloudWatch (monitoring, logs)
```

**Why AWS:** Have credits available, need backend services, serverless = minimal maintenance

**What NOT to use AWS for:** Static hosting (Cloudflare does this better and free)

### Content Pipeline
```
Obsidian Vault (ideation & drafting)
    ↓
Claude Chat (strategy, outlining, refinement)
    ↓
Claude Code (technical implementation, automation)
    ↓
Markdown files in Hugo repo
    ↓
Git push
    ↓
Cloudflare Pages auto-deploy (30 seconds)
    ↓
Live on divineforge.com
```

---

## 📐 Site Structure Redesign

### New Information Architecture

```
divineforge.com/
├── Home (/)
│   ├── Hero: "Escaping Corporate IT with AI"
│   ├── Current stats (MRR, projects, progress)
│   ├── Latest build/project spotlight
│   ├── Newsletter signup
│   └── Recent blog posts preview
│
├── Escape Plan (/escape-plan/)
│   ├── Origin story (corporate frustrations)
│   ├── The problem (organizational constraints)
│   ├── The solution (AI-powered product building)
│   ├── Transparent progress dashboard
│   ├── Current MRR and goal tracker
│   └── Newsletter CTA
│
├── Now (/now/)
│   ├── Derek Sivers "now page" format
│   ├── Current primary focus
│   ├── Active projects this month
│   ├── Learning/certifications in progress
│   ├── Experiments and side quests
│   └── Last updated date (manual monthly update)
│
├── Builds (/builds/)
│   ├── Technical projects portfolio
│   ├── "Watch me build X with Claude Code" series
│   ├── Open source repositories
│   ├── Video embeds + code snippets
│   ├── Problem → Solution → Outcome format
│   └── GitHub integration
│
├── Tools (/tools/)
│   ├── Digital products for sale
│   ├── Templates (AWS, Azure, Architecture)
│   ├── Starter kits and workflows
│   ├── Gumroad/Lemon Squeezy integration
│   ├── Product descriptions + pricing
│   └── Free samples/lead magnets
│
├── Writing (/blog/ or /writing/)
│   ├── Technical articles
│   ├── AI pair programming insights
│   ├── Enterprise IT patterns and anti-patterns
│   ├── Building in public updates
│   ├── Product launch retrospectives
│   └── SEO-optimized long-form content
│
├── About (/about/)
│   ├── Personal background (architect, Malaysia, journey)
│   ├── Tech stack transparency
│   ├── Work experience and expertise
│   ├── Why DivineForge exists
│   ├── Contact methods
│   └── Consulting inquiry form
│
└── GitHub (/github/)
    └── Redirect to github.com/divineforge
```

### Hugo Implementation Tasks

**Phase 1: Content Structure (Week 1)**
```bash
# New content files to create
hugo new escape-plan.md
hugo new now.md
hugo new about.md
hugo new builds/_index.md
hugo new tools/_index.md

# Update existing
# - content/_index.md (homepage)
# - config.toml (navigation menu)
```

**Navigation Menu (config.toml)**
```toml
[[menu.main]]
  name = "Escape Plan"
  url = "/escape-plan/"
  weight = 1

[[menu.main]]
  name = "Builds"
  url = "/builds/"
  weight = 2

[[menu.main]]
  name = "Tools"
  url = "/tools/"
  weight = 3

[[menu.main]]
  name = "Writing"
  url = "/blog/"
  weight = 4

[[menu.main]]
  name = "Now"
  url = "/now/"
  weight = 5

[[menu.main]]
  name = "About"
  url = "/about/"
  weight = 6
```

---

## 🚀 Implementation Roadmap

### Phase 1: Foundation (Week 1-2)
**Goal:** Establish new content structure and brand positioning

**Tasks:**
- [ ] Audit current Hugo theme and capabilities
- [ ] Create new content sections (escape-plan, now, builds, tools)
- [ ] Rewrite homepage with new hero section
- [ ] Update site navigation menu
- [ ] Add newsletter signup form (frontend only, connects later)
- [ ] Deploy and verify on Cloudflare Pages
- [ ] Write first "Now" page update
- [ ] Draft "Escape Plan" origin story

**Success Criteria:**
- Site builds without errors
- All new sections accessible
- Navigation works correctly
- Visual consistency maintained
- Mobile responsive

### Phase 2: AWS Backend Services (Week 3-4)
**Goal:** Add serverless backend for newsletter and contact forms

**Newsletter System:**
```
Frontend form → API Gateway → Lambda → DynamoDB + SES
```

**Implementation:**
```bash
# AWS SAM or Terraform
- Lambda function: newsletter-subscribe
- DynamoDB table: divineforge-subscribers
- SES verified sender: william@divineforge.com
- API Gateway endpoint: POST /api/subscribe
```

**Contact Form:**
```
Frontend form → API Gateway → Lambda → SES
```

**Tasks:**
- [ ] Set up AWS SAM or Terraform IaC
- [ ] Create Lambda functions (Python or Node.js)
- [ ] Configure DynamoDB table
- [ ] Set up SES and verify domain
- [ ] Create API Gateway endpoints
- [ ] Update Hugo site with working form endpoints
- [ ] Test end-to-end flow
- [ ] Add confirmation emails via SES

**Success Criteria:**
- Email subscriptions work end-to-end
- Emails stored in DynamoDB
- Confirmation emails sent via SES
- Contact form delivers to inbox
- Error handling works
- Costs under $2/month

### Phase 3: Content Creation Engine (Week 5-6)
**Goal:** Establish consistent publishing cadence

**First Content Series:** "Building DivineForge with Claude Code"

**Articles to Write:**
1. "Why I'm Escaping Corporate Banking (Slowly)"
   - The corporate frustration story
   - What's broken in enterprise IT
   - The plan forward

2. "Building a Hugo Site with Claude Code"
   - Static site setup process
   - AWS backend integration
   - Cost breakdown ($0-5/mo)
   - Code walkthrough

3. "Newsletter System Without ConvertKit"
   - AWS Lambda + SES + DynamoDB
   - Avoiding $29/mo subscription
   - DIY vs. buy decision framework

4. "First Product: Corporate Escape Starter Kit"
   - What's included
   - How it was built
   - Lessons learned
   - Transparent revenue numbers

**Tasks:**
- [ ] Write and publish 4 articles (1 per week)
- [ ] Create accompanying code repositories
- [ ] Record videos for YouTube (optional but valuable)
- [ ] Share on relevant communities (Reddit, HN, Twitter)
- [ ] Engage with readers/subscribers

**Success Criteria:**
- 4 articles published
- Newsletter has 50+ subscribers
- At least 1 article gets traction (>100 views)
- GitHub repos linked and documented
- Feedback collected from readers

### Phase 4: First Product Launch (Week 7-8)
**Goal:** Ship "Corporate Escape Starter Kit" and make first dollar

**Product: Corporate Escape Starter Kit - $49**

**What's Included:**
1. AWS Infrastructure Templates
   - Static site deployment (Terraform/SAM)
   - Email automation (SES + Lambda)
   - Serverless API patterns
   - Cost optimization guide

2. AI Workflow Library
   - Claude prompts for content creation
   - Code generation patterns with Claude Code
   - Product ideation frameworks
   - Productivity workflows

3. Side Business Playbook
   - Time management with 5-10 hrs/week
   - Revenue validation checklist
   - MVP scoping templates
   - Launch timeline template

4. Tech Stack Decision Matrix
   - Free/cheap tools that work
   - What NOT to build yourself
   - When to DIY vs. buy
   - Cost projections by scenario

**Delivery Method:**
- GitHub private repo access OR
- Downloadable zip from S3 (signed URL)
- Notion workspace with playbook
- Video walkthrough (30-45 min)

**Technical Setup:**
- [ ] Create Gumroad or Lemon Squeezy account
- [ ] Set up product listing with sales page
- [ ] Configure webhook → Lambda → delivery automation
- [ ] Create delivery Lambda function
- [ ] Store product files in S3
- [ ] Test purchase-to-delivery flow
- [ ] Write launch email sequence
- [ ] Create sales page on /tools/

**Launch Strategy:**
- Email list announcement (Week 8, Friday)
- Twitter/LinkedIn posts
- Reddit (r/SideProject, r/EntrepreneurRideAlong)
- Hacker News (Show HN)
- Indie Hackers post
- Personal network outreach

**Success Criteria:**
- Product launched by end of Week 8
- At least 1 sale in first week (validation)
- Delivery automation works flawlessly
- Positive feedback from first customers
- Revenue: $50-500 (realistic first launch)

### Phase 5: Content Flywheel (Week 9-12)
**Goal:** Establish sustainable publishing rhythm

**Content Calendar:**
- **Weekly:** 1 technical article or build log
- **Bi-weekly:** 1 video (building process, tutorial)
- **Monthly:** "Now" page update
- **Monthly:** Revenue/progress report (transparent numbers)

**Content Themes:**
- AI-assisted development workflows
- AWS serverless patterns
- Corporate IT escape tactics
- Product building in public
- Honest retrospectives (failures + successes)

**Tasks:**
- [ ] Create content calendar in Notion/Obsidian
- [ ] Batch ideation sessions (monthly)
- [ ] Use Claude for drafting/outlining
- [ ] Use Claude Code for technical implementation
- [ ] Repurpose: Article → Thread → Video → Newsletter
- [ ] Build email list to 100+ subscribers
- [ ] Engage consistently with audience

**Success Criteria:**
- Published 4+ articles
- Email list 100+ subscribers
- 2-4 videos on YouTube
- Consistent traffic growth
- Community engagement (comments, DMs)

---

## 📈 Success Metrics

### Primary Metrics (Revenue-Focused)
- **MRR (Monthly Recurring Revenue):** $0 → $500 (Q1 2025) → $5,000 (Q4 2025)
- **Product Sales:** First dollar by Week 8, $1K total by end of Q1 2025
- **Email Subscribers:** 100 by Week 12, 500 by Q2 2025
- **Consulting Inquiries:** 1-2 per month by Q2 2025

### Secondary Metrics (Leading Indicators)
- **Content Published:** 1 article/week minimum
- **GitHub Activity:** Public commits, repos, stars
- **Site Traffic:** 500 unique visitors/month by Q1 2025
- **Social Engagement:** Twitter followers, LinkedIn connections
- **YouTube Subscribers:** 100 by Q2 2025 (if pursuing video)

### Health Metrics (Sustainability)
- **Weekly Time Investment:** 10 hours maximum (sustainable)
- **Build Quality:** Ships working, useful products
- **Audience Feedback:** Positive sentiment, actual use cases
- **Personal Energy:** Not burning out, still enjoying process

---

## 💰 Revenue Model

### Revenue Streams (Prioritized)

**1. Digital Products (Primary - Fastest to Revenue)**
- Corporate Escape Starter Kit: $49
- AWS Architecture Templates: $29-99
- AI Workflow Bundles: $39
- Notion/Obsidian Templates: $19

**Target:** $500-1,000/month by Q2 2025

**2. Consulting/Fractional Architect (High Leverage)**
- AWS/Azure architecture reviews: $2,000-5,000/project
- GenAI implementation consulting: $150-250/hour
- Fractional CTO/Architect: $3,000-8,000/month

**Target:** 1-2 clients by Q2 2025

**3. Content/Community (Long-term)**
- Sponsored content: $500-2,000/post (later)
- YouTube ad revenue: Minimal but grows
- Paid newsletter tier: $10/month (when valuable enough)
- Course/cohort-based learning: $299-999 (Q3 2025+)

**4. Affiliate Revenue (Passive)**
- AWS/Azure credits referrals
- Tool recommendations (ConvertKit alternatives, etc.)
- Book recommendations (technical, business)

**Target:** $50-200/month passive

### What NOT to Pursue
❌ Freelancing on Upwork/Fiverr (time for money trap)
❌ Low-ticket products under $19 (too much support overhead)
❌ Building SaaS initially (too complex, slow to revenue)
❌ Agency model (want solo lifestyle business)
❌ Ads on site (ruins UX, minimal revenue at small scale)

---

## 🎮 Related Projects (Context)

### Game Development Projects
**Status:** Planned, not active yet
**Focus:** Philosophical adventure games (Godot + Flutter)
**Revenue:** Steam, itch.io, mobile app stores
**Relationship:** Shares DivineForge tech infrastructure
**Timeline:** Start after DivineForge generates $500+/month

### Creative Writing Projects
**Status:** Planned, not active yet
**Focus:** Personal storytelling and philosophical writings
**Revenue:** Patreon, affiliate, eventual books
**Relationship:** AI-assisted creative outlet
**Timeline:** Start after DivineForge generates $1,000+/month

**Strategic Note:** DivineForge gets 100% focus until it generates sustainable revenue. Other projects are validated ideas but must wait.

---

## 🛠️ Technical Specifications

### Hugo Theme Requirements
- Modern, clean design (2024 aesthetics)
- Fast page loads (<1s)
- Mobile-responsive
- Dark mode support (nice-to-have)
- Good typography for reading
- Code syntax highlighting
- Easy customization

**Options if current theme insufficient:**
- Hugo Blowfish (feature-rich, modern)
- Hugo PaperMod (minimal, fast, popular)
- Custom theme (if specific needs)

### AWS Infrastructure as Code

**Tool Choice:** AWS SAM (Serverless Application Model)
- Simpler than Terraform for serverless
- Built for Lambda + API Gateway
- Good local testing with `sam local`
- Easy CI/CD integration

**Alternative:** Terraform if more complex infrastructure needed later

**Repository Structure:**
```
divineforge-infrastructure/
├── template.yaml (SAM template)
├── functions/
│   ├── newsletter-subscribe/
│   ├── contact-form/
│   └── product-delivery/
├── tests/
└── README.md
```

### Monitoring & Analytics

**Site Analytics:** Cloudflare Web Analytics (free, privacy-first)
- No cookies needed
- GDPR compliant
- Basic metrics sufficient

**AWS Monitoring:** CloudWatch (included)
- Lambda logs and metrics
- Error alerting
- DynamoDB metrics

**Email Metrics:** SES + custom logging
- Open rates (if needed)
- Bounce handling
- Unsubscribe tracking

---

## 📝 Content Templates

### Blog Post Structure
```markdown
---
title: "Article Title"
date: 2024-11-20
tags: [aws, serverless, ai, building-in-public]
description: "One-sentence hook"
---

## The Problem
[What pain point this addresses]

## The Solution
[What you built, how it works]

## The Process
[Step-by-step with code snippets]

## The Results
[Metrics, outcomes, lessons learned]

## What's Next
[Future improvements, related topics]

---

**Want to follow along?** [Newsletter signup]
**Questions?** [Contact or comment]
```

### "Now" Page Template
```markdown
---
title: "What I'm Building Now"
date: 2024-11-20
layout: now
---

# What I'm Building Now

**Primary Focus:** [Main project this month]
[2-3 sentence description of what and why]

**Secondary Projects:**
- [Project 2]: [Status/progress]
- [Project 3]: [Status/progress]

**Learning:**
- [Certification/skill]: [Progress]
- [Book/course]: [Insight]

**Experiments:**
- [Side quest 1]
- [Side quest 2]

**Stats:**
- MRR: $X
- Email subscribers: X
- Published: X articles, X videos

---
*Last updated: [date]*
*Inspired by Derek Sivers' [now page movement](https://nownownow.com/)*
```

---

## 🚨 Common Pitfalls to Avoid

### Development Traps
❌ Perfectionism (ship functional over perfect)
❌ Over-engineering (YAGNI principle)
❌ Technology tourism (stick with Hugo + AWS)
❌ Building without validating (talk to users first)
❌ Analysis paralysis (bias toward action)

### Content Traps
❌ Inconsistent publishing (set realistic cadence)
❌ Writing for everyone (niche down to frustrated architects)
❌ Not promoting work (share everywhere relevant)
❌ Ignoring SEO completely (basic optimization matters)
❌ Hiding failures (be transparent about what doesn't work)

### Business Traps
❌ Free consulting (time = limited resource)
❌ Underpricing (charge what it's worth)
❌ Building without selling (validate before building)
❌ Ignoring feedback (listen to early customers)
❌ Burning out (sustainable pace over sprint)

---

## 🤝 Working with Claude Code

### How to Use This Document

**When starting a new task:**
```bash
claude-code

# Then say:
"Read PLANS.md from the divineforge repo. I want to implement
[specific phase/task]. Let's start by [first action]."
```

**For context-aware development:**
```bash
"According to PLANS.md, we're in Phase 2: AWS Backend Services.
Help me build the newsletter subscription Lambda function."
```

**For consistency checks:**
```bash
"Does this implementation align with the architecture defined
in PLANS.md Section: Technical Architecture?"
```

### Context Refresh Prompts

If Claude Code seems to lose context:
```
"Reminder: DivineForge uses Hugo + Cloudflare Pages for frontend,
AWS serverless for backend. Current phase: [X]. Current task: [Y].
Refer to PLANS.md for full context."
```

### Update This Document

**When completing major milestones:**
- Update "Current State Assessment"
- Mark tasks as completed with [x]
- Add "Completed" dates to phases
- Document lessons learned in new section

**When pivoting strategy:**
- Update with date and reasoning
- Keep old decisions for context
- Note what changed and why

---

## 📞 Support & Resources

### Key Links
- **Site:** https://divineforge.com
- **GitHub:** https://github.com/divineforge
- **Email:** william@divineforge.com (once SES configured)

### External Documentation
- Hugo Docs: https://gohugo.io/documentation/
- AWS SAM Docs: https://docs.aws.amazon.com/serverless-application-model/
- Cloudflare Pages: https://developers.cloudflare.com/pages/

### Communities for Sharing
- r/SideProject
- r/EntrepreneurRideAlong
- Indie Hackers
- Hacker News (Show HN)
- Twitter #BuildInPublic

---

## ✅ Quick Start Checklist

**Today (Next 2 Hours):**
- [x] Clone/navigate to divineforge Hugo repo
- [x] Create PLANS.md in repo root (this file)
- [x] Open Claude Code and reference this file
- [ ] Audit current Hugo structure
- [ ] Create first new content file (escape-plan.md)

**This Week:**
- [ ] Complete Phase 1 content restructure
- [ ] Deploy to Cloudflare Pages
- [ ] Write "Escape Plan" origin story
- [ ] Update "Now" page
- [ ] Share progress on Twitter/LinkedIn

**This Month:**
- [ ] Complete AWS backend setup (Phase 2)
- [ ] Publish 4 technical articles (Phase 3)
- [ ] Build email list to 50+ subscribers
- [ ] Prepare first product (Phase 4 prep)

---

**Remember:** This is a marathon, not a sprint. Sustainable progress over heroic bursts. Ship functional, iterate based on feedback, stay focused on revenue-generating activities.

**The goal:** $5K/month by December 2025. Every decision should move toward this north star.

---

*This document is a living guide. Update it as you learn, pivot as needed, but always stay focused on the mission: building revenue and freedom through AI-assisted product development.*

---
title: "Builds"
description: "Technical projects and build logs - Watch me build with Claude Code"
layout: "list"
---

# What I'm Building

This is where I document the technical projects I'm building with AI pair programming. Each build includes the problem, solution, implementation process, and results—code, lessons, and honest retrospectives.

**Philosophy:** Ship functional, iterate based on feedback, document everything.

---

## Active Builds

### 🏗️ DivineForge.com Infrastructure (November 2024)
**Status:** In Progress - Phase 1
**Stack:** Hugo, Cloudflare Pages, AWS Serverless

Building this site from scratch with a focus on simplicity, performance, and zero operational overhead. The goal is to create a platform for building in public while keeping costs under $5/month.

**What's Included:**
- Static site generation with Hugo + PaperMod theme
- Cloudflare Pages deployment (free, fast, global CDN)
- AWS serverless backend (Lambda + API Gateway + DynamoDB + SES)
- Newsletter subscription system (DIY, avoiding $29/month ConvertKit)
- Contact form automation
- Digital product delivery pipeline

**Build Log:** Coming soon
**Code:** GitHub repository (will be open sourced)

---

### 🚀 AWS Newsletter System (Coming in Phase 2)
**Status:** Planned - Week 3-4
**Stack:** Lambda, DynamoDB, SES, API Gateway

Building a complete newsletter subscription system with AWS serverless—no third-party subscriptions, no monthly fees, full control.

**The Challenge:**
- ConvertKit: $29/month
- Mailchimp: $20/month
- Substack: Takes 10% of revenue

**The Solution:**
- AWS Lambda: Form processing
- DynamoDB: Subscriber storage
- SES: Email delivery (first 62,000 emails/month free)
- API Gateway: HTTP endpoints
- Total cost: ~$0-2/month

**Features:**
- Double opt-in confirmation
- Unsubscribe automation
- Email templates
- Analytics dashboard
- GDPR compliant

**Build Log:** Will document the entire process
**Code:** Will be open sourced as a template

---

### 📦 Corporate Escape Starter Kit (Phase 4 - Week 7-8)
**Status:** Planning
**Product Type:** Digital product ($49)

The first revenue-generating product—everything I'm using to build my escape from corporate IT.

**What's Included:**
1. AWS Infrastructure Templates
   - Static site deployment (SAM/Terraform)
   - Newsletter system (complete setup)
   - Serverless API patterns
   - Cost optimization guide

2. AI Workflow Library
   - Claude Code development patterns
   - Content generation prompts
   - Product ideation frameworks
   - Automation workflows

3. Side Business Playbook
   - Time management (5-10 hrs/week strategies)
   - Revenue validation checklist
   - MVP scoping templates
   - Launch timeline

4. Tech Stack Decision Matrix
   - Free vs. paid tools comparison
   - DIY vs. buy decision framework
   - Cost projections by scenario

**Build Log:** Will document the creation process
**Launch:** Q4 2024 / Q1 2025

---

## Upcoming Builds

### 🔐 Contact Form with AWS Lambda
**Timeline:** Phase 2
**Purpose:** Replace third-party contact forms with custom AWS solution

### 📊 Simple Analytics Dashboard
**Timeline:** Phase 3
**Purpose:** Track subscriber growth, page views, product sales

### 🎨 Product Delivery Automation
**Timeline:** Phase 4
**Purpose:** Automated digital product delivery via S3 + Lambda

---

## Completed Builds

### ✅ Hugo Site Structure (November 2024)
**What:** Transformed portfolio site into building-in-public platform
**Stack:** Hugo, PaperMod theme
**Result:** Clean, fast, maintainable site structure
**Deployment:** Cloudflare Pages

**Lessons Learned:**
- PaperMod is excellent for technical blogs (keep it simple)
- Hugo's speed is unmatched (builds in milliseconds)
- Git-based deployment is reliable and predictable
- Content structure matters more than visual polish initially

---

## Build Series: "Watch Me Build X with Claude Code"

This is where I'll publish detailed build logs showing the process of building products with AI pair programming.

**Format:**
- **The Problem:** What pain point am I solving?
- **The Solution:** What am I building and why?
- **The Process:** Step-by-step with code snippets, AI conversations, decisions
- **The Results:** What shipped, metrics, lessons learned, what's next

**Coming Soon:**
1. "Building a Hugo Site with Claude Code" (this site)
2. "Newsletter System Without ConvertKit" (AWS serverless)
3. "Shipping My First Product in 2 Weeks" (Corporate Escape Starter Kit)

---

## Open Source Contributions

As builds mature and prove valuable, selected components will be open sourced as templates and starter kits for others to use.

**Planned Releases:**
- DivineForge Hugo Template (this site structure)
- AWS Newsletter Starter (complete serverless setup)
- Serverless Contact Form Template
- Digital Product Delivery System

**GitHub:** [github.com/divineforge](https://github.com/divineforge)

---

## Behind the Scenes

**Development Environment:**
- **Editor:** VS Code + Claude Code
- **Planning:** Obsidian (markdown-based notes)
- **Strategy:** Claude Chat (brainstorming, refinement)
- **Implementation:** Claude Code (actual development)
- **Version Control:** Git + GitHub
- **Deployment:** Automated via Cloudflare Pages

**Development Workflow:**
```
Idea (Obsidian)
  ↓
Strategy (Claude Chat)
  ↓
Implementation (Claude Code)
  ↓
Code Review (Human + AI)
  ↓
Git Commit & Push
  ↓
Auto-Deploy (Cloudflare Pages)
  ↓
Monitor & Iterate
```

---

## Want to Follow Along?

- **Newsletter:** Coming soon (Phase 2)
- **Twitter/X:** [@divineforge](https://x.com/divineforge) - Build updates
- **GitHub:** [github.com/divineforge](https://github.com/divineforge) - Code repositories
- **Now Page:** [/now/](/now/) - Monthly progress updates

**Questions? Suggestions?** Reach out on [Twitter/X](https://x.com/divineforge) or [LinkedIn](https://linkedin.com/in/cheongweelau)

---

*This page is updated as new builds are started and completed. Last update: November 20, 2024*

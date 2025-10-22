# Topics Directory

Organization of emails by subject matter, project type, and business function for thematic navigation.

## Structure

```
topics/
├── campaigns/           # Campaign planning and execution
├── strategy/            # Strategic discussions and planning
├── reporting/           # Performance reports and analytics
├── contracts/           # Proposals, contracts, and agreements
└── feedback/            # Client feedback and reviews
```

## Topic Categories

### Campaigns (~28% of volume - 3,958 emails)
Campaign planning, execution, and coordination emails.

**Subcategories:**
- `product-launches/` - New product and service launches
- `seasonal-campaigns/` - Holiday, seasonal, and time-based campaigns
- `email-campaigns/` - Email marketing and automation
- `social-media/` - Social media campaigns and content
- `paid-advertising/` - PPC, display, and paid media campaigns
- `content-marketing/` - Blog, video, and content initiatives
- `influencer-marketing/` - Influencer partnerships and collaborations
- `event-marketing/` - Virtual and in-person events

**Common Email Types:**
- Campaign briefs and planning
- Creative reviews and feedback
- Launch coordination
- Budget discussions
- Performance updates

### Strategy (~22% of volume - 3,110 emails)
High-level strategic planning and business development discussions.

**Subcategories:**
- `brand-strategy/` - Brand positioning and messaging
- `growth-strategy/` - Growth marketing and scaling
- `market-research/` - Market analysis and competitive intelligence
- `annual-planning/` - Yearly and quarterly planning
- `channel-strategy/` - Multi-channel marketing approaches
- `customer-journey/` - Customer experience and lifecycle
- `digital-transformation/` - Digital strategy and transformation

**Common Email Types:**
- Strategic proposals
- Market analysis discussions
- Long-term planning
- Framework development
- Opportunity assessments

### Reporting (~18% of volume - 2,544 emails)
Performance reports, analytics, and results communication.

**Subcategories:**
- `monthly-reports/` - Regular monthly performance reports
- `campaign-results/` - Specific campaign performance analysis
- `analytics-insights/` - Data analysis and insights
- `roi-analysis/` - Return on investment calculations
- `competitive-analysis/` - Competitive performance tracking
- `quarterly-reviews/` - Quarterly business reviews
- `annual-summaries/` - Year-end performance summaries

**Common Email Types:**
- Performance dashboards
- Results presentations
- Data insights
- Recommendations based on analytics
- Success stories and case studies

### Contracts (~10% of volume - 1,414 emails)
Proposals, contracts, agreements, and legal/financial correspondence.

**Subcategories:**
- `proposals/` - New business proposals and pitches
- `statements-of-work/` - SOWs and project scopes
- `contracts-agreements/` - Legal agreements and terms
- `renewals/` - Contract renewals and extensions
- `amendments/` - Contract modifications
- `invoicing-billing/` - Financial and billing communications
- `negotiations/` - Terms and pricing negotiations

**Common Email Types:**
- Proposal submissions
- Contract reviews
- Scope discussions
- Pricing negotiations
- Legal clarifications
- Renewal discussions

### Feedback (~15% of volume - 2,120 emails)
Client feedback, reviews, testimonials, and relationship management.

**Subcategories:**
- `client-satisfaction/` - Feedback and satisfaction surveys
- `testimonials/` - Client testimonials and reviews
- `concerns-issues/` - Problem resolution and support
- `suggestions/` - Client suggestions and requests
- `relationship-management/` - Check-ins and relationship building
- `success-stories/` - Wins and positive outcomes

**Common Email Types:**
- Feedback requests
- Client concerns
- Thank you notes
- Relationship check-ins
- Testimonial requests
- Issue resolution

### General Correspondence (~7% of volume - 990 emails)
Miscellaneous communications that don't fit other categories.

**Subcategories:**
- `introductions/` - New client introductions
- `meetings-calls/` - Meeting coordination
- `administrative/` - Admin and logistics
- `internal/` - Team communications
- `networking/` - Professional networking

## Usage

### Finding Emails by Topic

1. **Navigate by category:**
   ```
   topics/[category]/[subcategory]/
   ```

2. **Browse topic index:**
   Each topic folder contains an `index.md` with:
   - Topic overview
   - Complete email list
   - Related topics
   - Key trends and insights

3. **Search by tag:**
   Use GitHub search:
   ```bash
   grep -r "Tags:.*campaign-planning" .
   ```

### Cross-Referencing

Emails often span multiple topics. For example:
- A campaign planning email → `campaigns/` AND `strategy/`
- A performance report with renewal discussion → `reporting/` AND `contracts/`

Use symbolic links or reference related emails in the metadata.

## Most Common Topics

| Topic | Count | % of Total |
|-------|-------|------------|
| Campaign Planning | 3,958 | 28% |
| Strategy Discussion | 3,110 | 22% |
| Performance Reports | 2,544 | 18% |
| Client Feedback | 2,120 | 15% |
| Contracts & Proposals | 1,414 | 10% |
| General | 990 | 7% |

## Topic Tags

When tagging emails, use these consistent topic tags:

**Campaign Tags:**
- `campaign-planning`
- `product-launch`
- `email-campaign`
- `social-media`
- `paid-advertising`
- `influencer-marketing`
- `content-marketing`
- `event-marketing`

**Strategy Tags:**
- `strategy-discussion`
- `brand-strategy`
- `growth-strategy`
- `market-research`
- `annual-planning`
- `channel-strategy`

**Reporting Tags:**
- `performance-report`
- `analytics-insights`
- `roi-analysis`
- `campaign-results`
- `monthly-report`
- `quarterly-review`

**Contract Tags:**
- `proposal-contract`
- `statement-of-work`
- `contract-renewal`
- `billing-invoice`
- `negotiation`

**Feedback Tags:**
- `client-feedback`
- `testimonial`
- `issue-resolution`
- `satisfaction-survey`
- `relationship-management`

## Creating Topic Folders

When organizing emails by topic:

1. Create subfolder in appropriate category:
   ```
   topics/[category]/[specific-topic]/
   ```

2. Add `index.md` with topic overview

3. Link relevant emails:
   ```bash
   ln -s ../../../archives/YYYY/MM/email.md .
   ```

4. Update topic index with new category

## Topic Evolution Over Time

### 2018-2019: Foundation Building
- Heavy focus on campaigns (32%)
- Client acquisition proposals (15%)
- Basic reporting structures

### 2020-2021: Strategic Shift
- Strategy discussions increased (25%)
- COVID-19 pivot communications
- Digital transformation focus
- Enhanced analytics and reporting

### 2022-2023: Maturation
- Sophisticated campaign strategies
- Data-driven decision making
- Long-term client relationships
- Performance optimization

### 2024-2025: Innovation
- AI and automation topics emerging
- Advanced multi-channel strategies
- Influencer marketing growth
- Podcast and audio advertising

---

*This directory enables subject-based navigation and thematic analysis of communications.*
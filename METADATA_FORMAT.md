# Email Metadata Format Specification

## Overview

This document defines the standardized Markdown format for converting email messages into archival documents with complete metadata preservation.

## Core Principles

1. **Human Readable**: Markdown format for universal accessibility
2. **Machine Parseable**: YAML frontmatter for automated indexing
3. **Complete Context**: All metadata fields preserved
4. **Searchable**: Optimized for text search and filtering
5. **Future-Proof**: Standard formats for long-term viability

## File Naming Convention

### Format
```
YYYY-MM-DD-NNN-subject-slug.md
```

### Components
- `YYYY`: Four-digit year
- `MM`: Two-digit month (01-12)
- `DD`: Two-digit day (01-31)
- `NNN`: Three-digit sequence number for that day (001-999)
- `subject-slug`: Kebab-case subject line (max 50 chars)

### Examples
```
2024-03-15-001-q2-campaign-strategy-discussion.md
2024-03-15-002-budget-approval-request.md
2023-12-20-003-year-end-performance-report.md
```

## Metadata Structure

### Required Fields

All emails MUST include these fields in YAML frontmatter:

```yaml
---
Email-ID: "2024-03-15-001"
Date: "2024-03-15 14:32:00 PST"
From: "john.doe@techstartup.com"
From-Name: "John Doe"
To: "marketing@kissagency.com"
To-Name: "KISS Marketing Team"
Subject: "Q2 Campaign Strategy Discussion"
Thread-ID: "thread-2024-03-techstartup-q2"
Importance: "High"
Tags: ["campaign-planning", "tech-startup", "q2-2024", "strategy"]
---
```

### Optional Fields

Include when applicable:

```yaml
CC: "manager@kissagency.com, ceo@techstartup.com"
CC-Names: "Sarah Manager, Alex CEO"
BCC: "archive@kissagency.com"
BCC-Names: "Archive System"
Reply-To: "john.doe@techstartup.com"
In-Reply-To: "2024-03-14-002"
References: ["2024-03-10-001", "2024-03-12-003"]
Attachments: ["Q2-Strategy-Draft.pdf", "Budget-Proposal.xlsx"]
Attachment-URLs: ["../attachments/2024/03/Q2-Strategy-Draft.pdf"]
Client: "TechStartup Inc"
Client-Category: "tech-startups"
Project: "Q2 2024 Campaign"
Project-ID: "PRJ-2024-Q2-TS"
Campaign: "Spring Product Launch"
Status: "Active"
Follow-Up-Date: "2024-03-20"
Billing: "Billable"
Contract: "CNT-2024-001"
Confidential: false
Notes: "Initial strategy discussion, follow-up needed"
Archived-Date: "2025-10-22"
Archived-By: "William Matthiessen"
Last-Modified: "2025-10-22"
```

## Field Definitions

### Core Identification

**Email-ID**
- Format: `YYYY-MM-DD-NNN`
- Unique identifier for each email
- Used for cross-referencing

**Date**
- Format: `YYYY-MM-DD HH:MM:SS TZ`
- Original send/receive timestamp
- Include timezone

**Thread-ID**
- Format: `thread-YYYY-MM-client-topic`
- Groups related conversations
- Enables conversation threading

### People Fields

**From / From-Name**
- Sender email and display name
- Required for all emails

**To / To-Name**
- Primary recipient(s)
- Comma-separated for multiple

**CC / CC-Names**
- Carbon copy recipients
- Optional, include if present

**BCC / BCC-Names**
- Blind carbon copy
- Include only if you were BCC recipient

### Content Fields

**Subject**
- Original subject line
- Preserve exactly as written
- No truncation

**Importance**
- Values: `High`, `Normal`, `Low`
- Based on original email flags
- Default: `Normal`

**Tags**
- Array of lowercase-kebab-case strings
- 3-8 tags per email recommended
- Use consistent taxonomy (see Tagging Guidelines)

### Relationship Fields

**In-Reply-To**
- Email-ID of message being replied to
- Direct parent in conversation

**References**
- Array of related Email-IDs
- All messages in thread
- Chronological order

### Attachment Fields

**Attachments**
- Original filenames
- Array format
- Include all attachments

**Attachment-URLs**
- Relative paths to stored files
- Format: `../attachments/YYYY/MM/filename.ext`
- Store attachments separately

### Business Context

**Client / Client-Category**
- Client name and industry category
- Enables client-based filtering
- Use standardized client names

**Project / Project-ID**
- Specific project or campaign
- Use consistent project naming
- Link to project documentation

**Campaign**
- Marketing campaign name
- More specific than project
- Optional

**Status**
- Values: `Active`, `Completed`, `Pending`, `Archived`
- Current state of discussion
- Update as needed

**Billing**
- Values: `Billable`, `Non-Billable`, `Internal`
- For time tracking
- Optional

### Archive Metadata

**Archived-Date**
- When email was added to repository
- Format: `YYYY-MM-DD`

**Archived-By**
- Person who archived the email
- Full name

**Last-Modified**
- Last update to archived version
- Format: `YYYY-MM-DD`

**Notes**
- Archive-specific notes
- Context for future reference
- Clarifications or summaries

## Body Content Format

### Structure

```markdown
---
[YAML Frontmatter]
---

# [Subject Line]

## Email Header

**From:** [From-Name] <[email]>  
**To:** [To-Name] <[email]>  
**Date:** [Full Date and Time]  
**Subject:** [Subject]

---

## Message Content

[Email body converted to Markdown]

### Quoted Sections

> Previous email quoted text appears in blockquotes
> With proper attribution

---

## Signature

[Email signature if present]

---

## Attachments

- [Attachment 1 Name](../attachments/2024/03/file1.pdf) - Description
- [Attachment 2 Name](../attachments/2024/03/file2.xlsx) - Description

---

## Archive Notes

*Archived on [Date] by [Name]*

**Context:** [Any additional context needed]

**Related Emails:**
- [Email-ID]: [Subject]
- [Email-ID]: [Subject]

**Action Items:**
- [ ] Follow-up scheduled for [date]
- [ ] Waiting for client response
```

### Content Formatting Guidelines

1. **Preserve Structure**
   - Maintain paragraph breaks
   - Keep bullet points and numbering
   - Preserve emphasis (bold, italic)

2. **Convert HTML**
   - Transform HTML emails to clean Markdown
   - Remove unnecessary styling
   - Keep semantic meaning

3. **Quote Attribution**
   - Use blockquotes for replies
   - Include attribution line
   - Nest quotes appropriately

4. **Links**
   - Convert to Markdown links: `[text](url)`
   - Preserve all URLs
   - Note if link is broken

5. **Images**
   - Reference stored images: `![alt](../images/...)`
   - Store in separate images folder
   - Include alt text

6. **Tables**
   - Convert to Markdown tables
   - Or use code blocks for complex data
   - Preserve data accuracy

## Tagging Guidelines

### Tag Categories

**Business Function** (1-2 tags)
- `campaign-planning`
- `strategy-discussion`
- `performance-report`
- `client-feedback`
- `proposal-contract`
- `billing-invoice`
- `general-correspondence`

**Client Category** (1 tag)
- `tech-startup`
- `ecommerce`
- `professional-services`
- `healthcare-wellness`
- `education`
- `real-estate`

**Time Period** (1 tag)
- `q1-2024`, `q2-2024`, etc.
- `year-2024`, `year-2023`, etc.
- `month-2024-03`, etc.

**Priority/Status** (0-1 tags)
- `urgent`
- `follow-up-needed`
- `decision-required`
- `completed`
- `archived`

**Project-Specific** (1-3 tags)
- `product-launch`
- `brand-refresh`
- `email-campaign`
- `social-media`
- `seo-optimization`
- `content-strategy`

**Special Markers** (0-1 tags)
- `high-value-client`
- `long-term-relationship`
- `new-client`
- `contract-renewal`
- `issue-resolution`

### Tag Format Rules

1. All lowercase
2. Use hyphens for spaces
3. No special characters
4. 2-4 words maximum
5. Consistent terminology
6. 3-8 tags per email (sweet spot: 5)

## Examples

### Example 1: Client Strategy Discussion

```markdown
---
Email-ID: "2024-03-15-001"
Date: "2024-03-15 14:32:00 PST"
From: "john.doe@techstartup.com"
From-Name: "John Doe"
To: "william@kissagency.com"
To-Name: "William Matthiessen"
Subject: "Q2 Campaign Strategy - Mobile App Launch"
Thread-ID: "thread-2024-03-techstartup-q2"
Importance: "High"
Tags: ["campaign-planning", "tech-startup", "q2-2024", "mobile-app", "strategy"]
Client: "TechStartup Inc"
Client-Category: "tech-startups"
Project: "Mobile App Launch Q2 2024"
Project-ID: "PRJ-2024-Q2-TS-APP"
Status: "Active"
Follow-Up-Date: "2024-03-20"
Billing: "Billable"
Attachments: ["App-Launch-Strategy-v2.pdf", "Q2-Budget-Breakdown.xlsx"]
Attachment-URLs: ["../attachments/2024/03/App-Launch-Strategy-v2.pdf", "../attachments/2024/03/Q2-Budget-Breakdown.xlsx"]
Archived-Date: "2025-10-22"
Archived-By: "William Matthiessen"
Notes: "Initial strategy session for major Q2 campaign. Client approved budget of $85K."
---

# Q2 Campaign Strategy - Mobile App Launch

## Email Header

**From:** John Doe <john.doe@techstartup.com>  
**To:** William Matthiessen <william@kissagency.com>  
**Date:** March 15, 2024, 2:32 PM PST  
**Subject:** Q2 Campaign Strategy - Mobile App Launch

---

## Message Content

Hi William,

Thank you for the comprehensive strategy document you sent over last week. The team reviewed it and we're very excited about the proposed approach for our Q2 mobile app launch.

### Key Points We Love:

1. **Phased Launch Approach** - The idea of beta testing with our existing customer base first is brilliant
2. **Influencer Strategy** - The micro-influencer focus aligns perfectly with our brand values
3. **Content Calendar** - The 90-day runway gives us enough time to build momentum

### Questions and Adjustments:

**Budget Allocation:**
We'd like to shift more budget toward the influencer program (from $25K to $35K) and reduce the paid social budget accordingly. Can you revise the breakdown?

**Timeline Concern:**
Our product team just informed me that the app won't be ready until April 15 instead of April 1. This pushes our soft launch back two weeks. Can we adjust the campaign calendar?

**Additional Channel:**
We're also considering a podcast sponsorship component. Do you have experience with podcast advertising for app launches?

### Next Steps:

I've attached:
- Updated strategy doc with our notes (v2)
- Revised budget breakdown based on internal discussions

Could we schedule a call early next week to align on these changes? I'm available:
- Monday, March 18: 2-4 PM PST
- Tuesday, March 19: 10 AM - 12 PM PST
- Wednesday, March 20: 1-5 PM PST

Looking forward to moving this forward!

---

## Signature

Best regards,

**John Doe**  
Head of Marketing  
TechStartup Inc  
john.doe@techstartup.com  
(555) 123-4567

---

## Attachments

- [App-Launch-Strategy-v2.pdf](../attachments/2024/03/App-Launch-Strategy-v2.pdf) - Annotated strategy document with team feedback
- [Q2-Budget-Breakdown.xlsx](../attachments/2024/03/Q2-Budget-Breakdown.xlsx) - Proposed budget reallocation

---

## Archive Notes

*Archived on October 22, 2025 by William Matthiessen*

**Context:** This email kicked off one of our most successful campaigns in 2024. Client ended up approving $85K total budget. Campaign resulted in 50K+ app downloads in first month.

**Related Emails:**
- 2024-03-08-001: Initial strategy proposal
- 2024-03-20-002: Follow-up call notes and revised timeline
- 2024-04-15-001: Campaign launch confirmation
- 2024-05-20-003: Final performance report

**Outcome:** Campaign exceeded KPIs by 40%. Client renewed annual contract.
```

### Example 2: Quick Client Update

```markdown
---
Email-ID: "2024-06-10-003"
Date: "2024-06-10 09:15:00 PST"
From: "william@kissagency.com"
From-Name: "William Matthiessen"
To: "sara.johnson@ecommercebrand.com"
To-Name: "Sara Johnson"
Subject: "Quick Update: Email Campaign Performance"
Thread-ID: "thread-2024-06-ecommerce-email"
Importance: "Normal"
Tags: ["performance-report", "ecommerce", "email-campaign", "quick-update"]
Client: "EcommerceBrand Co"
Client-Category: "ecommerce"
Project: "Summer Sale Email Campaign"
Status: "Completed"
Billing: "Billable"
Archived-Date: "2025-10-22"
Archived-By: "William Matthiessen"
---

# Quick Update: Email Campaign Performance

## Email Header

**From:** William Matthiessen <william@kissagency.com>  
**To:** Sara Johnson <sara.johnson@ecommercebrand.com>  
**Date:** June 10, 2024, 9:15 AM PST  
**Subject:** Quick Update: Email Campaign Performance

---

## Message Content

Hi Sara,

Just a quick update on the Summer Sale email campaign that launched last Friday:

**Key Metrics (48 hours):**
- Open Rate: 28.3% (vs. 22% average)
- Click Rate: 4.7% (vs. 3.2% average)
- Conversion Rate: 2.1% (vs. 1.5% average)
- Revenue: $47,300

**Winner:** The "24-Hour Flash Sale" subject line outperformed by 35%!

Full report coming Friday. Great results so far! 🎉

---

## Signature

Best,

**William Matthiessen**  
KISS Marketing Agency  
william@kissagency.com

---

## Archive Notes

*Archived on October 22, 2025 by William Matthiessen*

**Context:** Quick win email. Campaign ended up generating $125K total revenue over 5-day sale period.
```

## Validation Checklist

Before archiving, verify:

- [ ] Email-ID follows format: YYYY-MM-DD-NNN
- [ ] Date includes timestamp and timezone
- [ ] All required metadata fields present
- [ ] Tags follow naming conventions (3-8 tags)
- [ ] Content properly formatted as Markdown
- [ ] Quotes and replies properly attributed
- [ ] Attachments listed and stored separately
- [ ] Links converted to Markdown format
- [ ] Sensitive information redacted if needed
- [ ] Archive notes include context
- [ ] Related emails cross-referenced
- [ ] File saved in correct directory structure

## Tools and Automation

### Recommended Tools

**Email Extraction:**
- Thunderbird (MBOX export)
- Apple Mail (Save as plaintext)
- Gmail (Google Takeout)
- Outlook (MSG to EML conversion)

**Conversion:**
- Python script for MBOX → Markdown
- Pandoc for HTML → Markdown
- Custom scripts for metadata extraction

**Validation:**
- YAML linters for frontmatter
- Markdown linters for formatting
- Git pre-commit hooks

### Automation Scripts (Future)

```bash
# Planned automation tools
./scripts/convert-email.py --input email.eml --output archives/
./scripts/extract-metadata.py --mbox-file archive.mbox
./scripts/generate-index.py --year 2024 --month 03
./scripts/validate-metadata.py --file email.md
```

## Version History

- **v1.0** (2025-10-22): Initial metadata format specification
- Future versions will be tracked here

---

*This specification is subject to refinement based on practical experience during the archiving process.*
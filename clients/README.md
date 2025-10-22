# Clients Directory

Organization of emails by client and sender/recipient for relationship-based navigation.

## Structure

```
clients/
├── tech-startups/          # Technology startup companies
├── ecommerce/              # E-commerce and retail brands
├── professional-services/  # Legal, consulting, financial firms
├── healthcare-wellness/    # Healthcare and wellness companies
└── other/                  # Other industries
```

## Client Categories

### Tech Startups (~35% of volume - 4,950 emails)
SaaS companies, mobile app developers, AI/ML ventures, and technology innovators.

**Common Topics:**
- Product launch campaigns
- Growth marketing strategies
- User acquisition and retention
- App store optimization
- Tech PR and thought leadership

### E-commerce (~25% of volume - 3,534 emails)
Fashion, lifestyle, consumer electronics, and direct-to-consumer brands.

**Common Topics:**
- Seasonal campaigns
- Email marketing automation
- Conversion rate optimization
- Influencer partnerships
- Customer lifecycle marketing

### Professional Services (~20% of volume - 2,827 emails)
Legal firms, consulting agencies, financial advisors, and B2B service providers.

**Common Topics:**
- Thought leadership content
- LinkedIn marketing
- Webinar and event promotion
- Lead generation
- Professional brand positioning

### Healthcare & Wellness (~12% of volume - 1,696 emails)
Telemedicine platforms, fitness brands, mental health services, and wellness products.

**Common Topics:**
- Patient/customer education
- Compliance-friendly marketing
- Community building
- Subscription models
- Health awareness campaigns

### Other Industries (~8% of volume - 1,131 emails)
Education technology, real estate, hospitality, and miscellaneous sectors.

**Common Topics:**
- Industry-specific strategies
- Market entry campaigns
- Brand awareness
- Customer acquisition

## Usage

### Finding Client Emails

1. **Navigate by category:**
   ```
   clients/[category]/[client-name]/
   ```

2. **Browse client index:**
   Each client folder contains an `index.md` with:
   - Client overview and relationship history
   - Complete email list
   - Project summaries
   - Key contacts
   - Performance highlights

3. **Search by client name:**
   Use GitHub search or grep:
   ```bash
   grep -r "Client: TechStartup Inc" .
   ```

### Symbolic Links

Emails are stored chronologically in `/archives/YYYY/MM/` but linked here for client-based access. This allows:
- Single source of truth (chronological storage)
- Multiple access paths (client, topic, chronological)
- No file duplication
- Easy maintenance

## Top Clients by Volume

| Client | Category | Emails | Relationship |
|--------|----------|--------|-------------|
| TechStartup Inc | Tech | ~425 | 2019-Present |
| FashionBrand Co | E-commerce | ~380 | 2020-Present |
| LegalFirm LLP | Professional | ~340 | 2018-Present |
| HealthTech Solutions | Healthcare | ~310 | 2021-Present |
| AppDevelopers Studio | Tech | ~290 | 2019-Present |
| RetailChain Inc | E-commerce | ~275 | 2018-2023 |
| ConsultingGroup | Professional | ~260 | 2019-Present |
| WellnessApp Co | Healthcare | ~245 | 2020-Present |
| EdTech Platform | Other | ~220 | 2021-Present |
| RealEstate Group | Other | ~195 | 2018-Present |

## Client Status Categories

**Active** - Current ongoing relationship  
**Completed** - Successful project completion, relationship ended amicably  
**Inactive** - No recent communication but relationship could be revived  
**Archived** - Historical record only

## Creating Client Folders

When adding a new client:

1. Create folder in appropriate category:
   ```
   clients/[category]/[client-name-kebab-case]/
   ```

2. Add `index.md` using template:
   ```
   cp indices/templates/client-index-template.md clients/[category]/[client]/index.md
   ```

3. Create symbolic links to chronological emails:
   ```bash
   ln -s ../../../archives/YYYY/MM/email.md .
   ```

4. Update client in sender-recipient index

## Privacy Note

⚠️ **Confidentiality:** Some client names and details may be pseudonymized or redacted to protect confidential business relationships. Always review before sharing outside the organization.

---

*This directory enables relationship-based navigation and client history analysis.*
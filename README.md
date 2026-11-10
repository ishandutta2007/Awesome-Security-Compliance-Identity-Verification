# Awesome-Security-Compliance-Identity-Verification

# Awesome Security, Compliance & Identity Verification

> A curated list of top Security, Compliance and Identity Verification platforms — both SaaS/Hosted commercial solutions and open-source alternatives for automating compliance evidence and verifying user identities.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Vanta](#vanta)
  - [Drata](#drata)
  - [Secureframe](#secureframe)
  - [Persona](#persona)
  - [Trulioo](#trulioo)
  - [Jumio](#jumio)
  - [Onfido (Entrust)](#onfido-entrust)
  - [Veriff](#veriff)
- [Open-Source Software](#-open-source-software)
  - [ComplianceOS](#complianceos)
  - [django-camera-kit](#django-camera-kit)
  - [CompliEdge](#compliedge)
  - [compliancekit](#compliancekit)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Security, Compliance and Identity Verification platforms. These are not open-source but are included as reference points for feature comparison.

### Vanta
**Type:** Agentic trust management and compliance automation
Vanta positions itself as an "agentic trust platform" with tiered plans from Essentials (one compliance framework) through Plus (questionnaire automation, 25/year) to Professional (advanced Trust Center, risk management) and Enterprise . Its Trust Center is included from the Essentials tier, with advanced capabilities (custom domains, AI chatbot for buyers, granular document access) at higher levels . Vanta emphasizes automated evidence collection, continuous control monitoring, and an auditor network, with AI agents handling policy generation, evidence checks, and SLA tracking [citation:8].
**Best for:** Organizations wanting a mature compliance automation platform with Trust Center capabilities bundled from entry tiers and a strong AI roadmap.

### Drata
**Type:** GRC platform with SafeBase-powered Trust Center
Drata now bundles its Trust Center through the SafeBase acquisition, with Foundation, Advanced, and Enterprise platform tiers plus separate SafeBase Trust Center + AIQA packages . Foundation covers up to 50 FTE with one framework and includes SafeBase Trust Center Standard plus AI Questionnaire Assistance Standard (10 questionnaires) . Drata emphasizes compliance as code, custom controls, and vendor risk management, with the Trust Center deeply integrated into its GRC program [citation:9].
**Best for:** Organizations wanting a unified GRC and Trust Center platform, particularly those already using SafeBase for questionnaire automation.

### Secureframe
**Type:** Compliance automation with Trust Center
Secureframe's Fundamentals plan starts at $7,500/year and includes a Trust Center, evidence collection, policy management, and continuous control monitoring . The Complete tier adds advanced Trust Center features (custom domains, automated NDA workflow), advanced questionnaire automation (15,000 questions/year), and SSO/SCIM . Secureframe offers 300+ native integrations and a Comply AI layer for policies and remediation [citation:10].
**Best for:** Mid-market organizations wanting a comprehensive compliance platform with a Trust Center included from the entry tier.

### Persona
**Type:** Configurable identity verification platform
Persona provides a configurable identity platform with tiered pricing: Essential starts at $250/month (12-month minimum) with templated verification flows, Growth adds KYB and advanced fraud tools, and Enterprise is fully tailored . Verification types span Government ID, Selfie, phone/email, authoritative databases (US and non-US), business registries, watchlists/sanctions, adverse media, and more . The platform supports dynamic flow logic, case management, and SOC 2 Type 2 / GDPR compliance . A Startup Program offers up to 12 months free with 500 monthly verifications [citation:3][citation:15].
**Best for:** Startups and enterprises needing a flexible, developer-friendly identity verification platform with granular pricing and KYB capabilities.

### Trulioo
**Type:** Global identity verification marketplace
Trulioo GlobalGateway pools data from multiple sources for AML/KYC checks, with facial recognition, dynamic routing of ID documents, and PEP/sanctions screening . Pricing starts at $99/month, making it one of the more accessible entry points among commercial identity platforms . It serves financial services, eCommerce, healthcare, and government sectors [citation:4].
**Best for:** Businesses needing cost-effective global identity verification with AML/KYC compliance and multi-source data coverage.

### Jumio
**Type:** Enterprise KYX platform
Jumio's KYX Platform covers ID verification, document verification, biometric authentication, AML screening (sanctions/PEP/adverse media), ongoing monitoring, and risk signals . Pricing is per-verification (custom-quoted) with a monthly minimum commit, plus add-ons for AML lookups, ongoing monitoring, and extended retention . SDKs are available for web, iOS, Android, React Native, Flutter, Cordova, Java, and .NET [citation:5].
**Best for:** Enterprises needing comprehensive KYX (Know Your Everything) capabilities with flexible SDK options and ongoing AML monitoring.

### Onfido (Entrust)
**Type:** Identity verification with document and biometric checks
Onfido (now Entrust IDV) provides end-to-end identity verification for KYC compliance, with document checks, selfie matching, and fraud prevention . G2 reviewers rate it 4.4/5 across 157 reviews, praising the intuitive platform and ability to build complex flows, while noting cost and occasional support delays as drawbacks . Pricing is custom-quoted [citation:6].
**Best for:** Organizations wanting a proven identity verification solution with strong document and biometric capabilities, accepting higher enterprise pricing.

### Veriff
**Type:** Identity verification with hybrid decision engine
Veriff uses a hybrid verification model combining AI-based decisions with manual specialist fallback for speed and accuracy . Enterprise pricing is volume-based via order form, with no setup fees and pay-per-decision (not per-attempt) billing for IDV . Certifications include SOC 2 Type II, ISO 27001:2022, GDPR, and ISO 30107-3 Levels 1 and 2 for liveness . Usage caps apply (15 sessions/minute, 10,000 sessions/month) unless an order form is signed [citation:7].
**Best for:** Organizations in highly regulated or high-fraud-risk industries needing certified liveness detection and volume-based pricing.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Security, Compliance and Identity Verification tools. The open-source ecosystem is **fragmented** across compliance scanners, identity verification libraries, and GRC platforms rather than unified Vanta/Persona equivalents.

### ComplianceOS
**Stack:** Python | **License:** Apache-2.0
ComplianceOS is an open-source compliance automation tool that **scans, remediates, and generates audit-ready evidence** for SOC 2, ISO 27001, GDPR, HIPAA, and PCI DSS . Unlike Vanta and Drata which collect evidence, ComplianceOS claims to **fix compliance issues**: it scans codebases for hardcoded secrets, SQL injection, XSS, and missing CI/CD protections; scans infrastructure for public buckets, disabled encryption, and overly permissive IAM; and scans configuration for missing policies and risk registers . The `complianceos fix` command auto-applies remediations, and `complianceos evidence` packages audit-ready reports. An MCP server is included for AI assistant integration, with no signup, no API key, and no data leaving the machine [citation:2].
**Best for:** Engineering teams wanting a CLI-driven compliance scanner that identifies and **fixes** violations in code and infrastructure, rather than just collecting evidence.

### django-camera-kit
**Stack:** Python / Django / PostgreSQL (pgvector) | **License:** Open Source (per PyPI)
django-camera-kit provides document scanning and **KYC face verification widgets** for Django applications . It drops a real document scanner (live edge detection, manual corner adjustment, multi-page → PDF) into any `FileField`, and includes a KYC module for selfie/ID capture with server-side face matching via YuNet and insightface embeddings, plus a head-movement liveness challenge . Matching only happens server-side using pgvector for embedding comparison. **Limitations:** The KYC module is an MVP; anti-deepfake hardening (server-verified liveness, passive scoring, multiple challenge types) is still on the roadmap [citation:1].
**Best for:** Django developers wanting to embed document scanning and basic KYC face verification directly into their application without a third-party identity vendor.

### CompliEdge
**Stack:** Python / Django / PostgreSQL | **License:** Open Source (per PyPI)
CompliEdge is an enterprise-grade **GRC management system** built with Django, covering governance policies, risk management, compliance frameworks with automated checklists, dashboards, and AI-driven risk prediction . It includes multi-role user management (Admin, Manager, Employee, Auditor), workflow management for policy and risk approvals, two-factor authentication, comprehensive audit logs, and collaboration tools . It provides the internal governance foundation that compliance programs depend on, though it does not include identity verification capabilities [citation:12].
**Best for:** Organizations wanting a self-hosted Django-based GRC platform for policy and risk management, with the option to build identity verification on top.

### compliancekit
**Stack:** Go | **License:** Open Source (per Go Packages)
compliancekit is an open-source compliance and security scanner for cloud and Linux infrastructure, generating **audit-ready evidence packs** for SOC 2, ISO 27001, and CIS benchmarks . It runs Collectors to populate a ResourceGraph, then drives a check Registry to produce Findings, which are assembled into an audit-ready folder by the evidence package . It supports DigitalOcean and Linux (via SSH) collectors, with framework definitions loaded from embedded YAML [citation:14].
**Best for:** Infrastructure teams wanting a Go-based scanner that produces audit-ready evidence for cloud and Linux environments, particularly for SOC 2 and ISO 27001 preparation.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Compliance Automation | Identity Verification | Self-Hosted | Best For |
|----------|---------|-------|----------------------|----------------------|-------------|----------|
| **Vanta** | Proprietary | Cloud | ✅ Agentic | ❌ | ❌ | Mature compliance + Trust Center |
| **Drata** | Proprietary | Cloud | ✅ + SafeBase | ❌ | ❌ | Unified GRC + Trust Center |
| **Secureframe** | Proprietary | Cloud | ✅ ($7,500/yr) | ❌ | ❌ | Mid-market compliance |
| **Persona** | Proprietary | Cloud | ❌ | ✅ Configurable | ❌ | Flexible IDV + KYB |
| **Trulioo** | Proprietary | Cloud | ❌ | ✅ Global marketplace | ❌ | Cost-effective global KYC |
| **Jumio** | Proprietary | Cloud | ❌ | ✅ KYX platform | ❌ | Enterprise KYX |
| **Veriff** | Proprietary | Cloud | ❌ | ✅ Hybrid decision | ❌ | Regulated liveness |
| **ComplianceOS** | Apache-2.0 | Python | ✅ Scan + **fix** | ❌ | ✅ | CLI compliance remediation |
| **django-camera-kit** | Open Source | Django | ❌ | ✅ Doc scan + face | ✅ | Django embedded KYC |
| **CompliEdge** | Open Source | Django | ✅ GRC | ❌ | ✅ | Internal GRC foundation |
| **compliancekit** | Open Source | Go | ✅ Evidence packs | ❌ | ✅ | Infrastructure compliance scanning |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Security, Compliance or Identity Verification tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem **splits** sharply between **compliance automation** (ComplianceOS for CLI-driven scan-and-fix, compliancekit for infrastructure evidence, CompliEdge for GRC) and **identity verification** (django-camera-kit for embedded Django KYC). There is **no open-source equivalent** to the combined compliance + identity verification breadth of commercial platforms like Vanta or Persona. ComplianceOS is notable for its "fix, not just collect" philosophy [citation:2], while django-camera-kit is the only open-source option found for embedding KYC directly into a web application [citation:1].

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐

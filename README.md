<div align="center">

# 🌸 GlowBot — AI-Powered Skincare Assistant

![GlowBot](https://img.shields.io/badge/Built%20with-Salesforce%20Agentforce-00A1E0?style=for-the-badge&logo=salesforce)
![Status](https://img.shields.io/badge/Status-Live-brightgreen?style=for-the-badge)
![AI](https://img.shields.io/badge/AI-Powered-FF6B9D?style=for-the-badge)
![Experience Cloud](https://img.shields.io/badge/Experience%20Cloud-Deployed-9B35A0?style=for-the-badge)

### An intelligent AI skincare assistant built on Salesforce Agentforce
### that helps customers find their perfect skincare routine!

[🌐 Live Demo](#) • [📸 Screenshots](#screenshots) • [🏗️ Architecture](#architecture) • [🚀 Setup](#setup)

</div>

---

## 🌟 Project Overview

**GlowBot** is a fully deployed AI-powered skincare assistant built on **Salesforce Agentforce**. 
Customers describe their skin concerns and GlowBot:

- 🧴 **Identifies** their skin type (oily, dry, combination, sensitive)
- ✨ **Recommends** personalized skincare products
- ⚗️ **Explains** key ingredients (retinol, niacinamide, hyaluronic acid)
- 🛡️ **Creates** support cases when needed
- 👥 **Escalates** to human agents for complex queries

---

## 🏗️ Architecture
```
Customer visits GlowBot Portal
           ↓
  Experience Cloud Website
           ↓
    GlowBot Chat Widget
           ↓
   Agentforce AI Agent
           ↓
  ┌────────────────────────────┐
  │        7 Topics            │
  │  ├── Skin Type Assessment  │
  │  ├── Product Recommendations│
  │  ├── Ingredient Guidance   │
  │  ├── Case Management       │
  │  ├── General FAQ           │
  │  ├── Escalation            │
  │  └── Order Inquiries       │
  └────────────────────────────┘
           ↓
  Knowledge Base (10 Articles)
           ↓
     Custom Data Model
  ┌──────────────────────────┐
  │  Skin_Profile__c         │
  │  Product__c              │
  │  Recommendation__c       │
  └──────────────────────────┘
```

---

## 📦 Tech Stack

| Technology | Purpose |
|---|---|
| **Salesforce Agentforce** | AI Agent Brain & Configuration |
| **Einstein AI** | Natural Language Processing |
| **Experience Cloud** | Customer-Facing Portal |
| **Salesforce Knowledge** | Knowledge Base Articles |
| **Screen Flow** | No-Code Automation |
| **Custom Objects** | Data Model Design |
| **Embedded Messaging** | Chat Widget |

---

## 🗄️ Data Model

### Custom Objects

#### Skin_Profile__c
| Field | Type | Purpose |
|---|---|---|
| Skin Type | Picklist | Oily/Dry/Combination/Sensitive |
| Concerns | Multi-Select Picklist | Acne/Aging/Dryness/etc |
| Allergies | Long Text Area | Ingredients to avoid |

#### Product__c
| Field | Type | Purpose |
|---|---|---|
| Product Name | Text | Product identifier |
| Price | Currency | Product cost |
| Skin Type Compatibility | Multi-Select Picklist | Which skin types it suits |
| Targets Concern | Multi-Select Picklist | Which concerns it addresses |
| Ingredients | Long Text Area | Product ingredients list |

#### Recommendation__c (Junction Object)
| Field | Type | Purpose |
|---|---|---|
| Skin Profile | Lookup | Links to Skin_Profile__c |
| Product | Lookup | Links to Product__c |

### Relationship Diagram
```
Skin_Profile__c ←──── Recommendation__c ────→ Product__c
    (One)                 (Junction)              (One)
                            (Many)
```

---

## 📚 Knowledge Base

### 10 Published Articles

#### 🧴 Skin Types (4 articles)
- Oily Skin — What You Need to Know
- Dry Skin — What You Need to Know
- Combination Skin — What You Need to Know
- Sensitive Skin — What You Need to Know

#### ⚗️ Key Ingredients (3 articles)
- Niacinamide — Benefits & Usage
- Retinol — Benefits & Usage
- Hyaluronic Acid — Benefits & Usage

#### ✨ Product Recommendations (3 articles)
- Best Products for Acne Prone Skin
- Best Products for Anti-Aging
- Best Products for Dry & Dehydrated Skin

---

## 🤖 Agentforce Configuration

### Agent Details
- **Name:** GlowBot
- **Type:** Agentforce Service Agent
- **Status:** Active ✅

### Topics Configured (7)

| Topic | Purpose | Actions |
|---|---|---|
| Skin Type Assessment | Identifies skin type | Answer Questions with Knowledge, Create Case |
| Skin Care Product Recommendations | Suggests products | Answer Questions with Knowledge, Create Case |
| Skin Care Ingredient Guidance | Explains ingredients | Answer Questions with Knowledge, Create Case |
| Case Management | Handles support cases | Create Case, Close Case |
| General FAQ | General questions | Answer Questions with Knowledge |
| Escalation | Transfers to humans | Escalate to Agent |
| Order Inquiries | Order questions | Query Order Status |

---

## ⚡ Flow Automation

### GlowBot Skin Profile Flow
**Type:** Screen Flow  
**Status:** Active ✅

#### Flow Steps:
```
Step 1: Screen — Skin Profile Assessment
        ├── What is your skin type? (Picklist)
        ├── What are your skin concerns? (Multi-Select)
        └── Any allergies to avoid? (Text Area)
            ↓
Step 2: Create Records — Skin Profile
        ├── Maps Skin Type from screen
        ├── Maps Concerns from screen
        └── Maps Allergies from screen
            ↓
Step 3: Create Records — Recommendation
        └── Links to newly created Skin Profile ID
```

---

## 📸 Screenshots

### GlowBot Portal Homepage
![Homepage](screenshots/homepage.png)

### GlowBot AI Chat Demo
![Chat Demo](screenshots/chat-demo.png)

### Agentforce Builder — Topics
![Agent Builder](screenshots/agent-builder.png)

### Knowledge Base Articles
![Knowledge Base](screenshots/knowledge-base.png)

### Screen Flow Canvas
![Flow](screenshots/flow.png)

### Custom Data Model
![Data Model](screenshots/data-model.png)
![Data Model](screenshots/data-model-2.png)
![Data Model](screenshots/data-model-3.png)

---

## 🚀 How to Reproduce

### Prerequisites
- Salesforce Developer Edition org
- Agentforce enabled
- Experience Cloud enabled

### Steps

#### 1. Setup Org
```
- Sign up at developer.salesforce.com
- Enable Agentforce: Setup → Einstein → Agentforce
- Enable Einstein features
```

#### 2. Create Data Model
```
- Create Skin_Profile__c with fields
- Create Product__c with fields  
- Create Recommendation__c with lookup fields
```

#### 3. Build Knowledge Base
```
- Enable Salesforce Knowledge
- Create 10 articles (4 skin types, 3 ingredients, 3 recommendations)
- Publish all articles
```

#### 4. Configure GlowBot Agent
```
- Go to Setup → Agentforce Agents → New
- Select Agentforce Service Agent template
- Name it GlowBot
- Add 7 topics with actions
- Activate agent
```

#### 5. Build Screen Flow
```
- Setup → Flows → New Screen Flow
- Add skin profile assessment screen
- Add Create Records steps
- Activate flow
```

#### 6. Deploy Experience Cloud
```
- Enable Digital Experiences
- Create new site → GlowBot Portal
- Add Embedded Messaging component
- Configure AI Experiences → Select GlowBot
- Publish site
```

---

## 🎯 Portfolio Value

This project demonstrates:

| Skill | Details |
|---|---|
| ✅ **Agentforce Configuration** | Built AI agent with 7 custom topics |
| ✅ **Custom Object Design** | Created junction object data model |
| ✅ **Knowledge Base Integration** | 10 published articles |
| ✅ **Experience Cloud** | Customer portal with chat widget |
| ✅ **Flow Automation** | No-code screen flow |
| ✅ **Einstein AI** | Leveraged Salesforce AI capabilities |
| ✅ **Data Modeling** | Many-to-many relationships |
| ✅ **Declarative Development** | Built without code |

---

## 🌐 Live Demo

**Portal URL:** `https://orgfarm-5ae2fe6f42-dev-ed.develop.my.site.com/glowbot`

> Note: Login required for security. Demo credentials available on request.

---

## 👩‍💻 About The Developer

**Padmini Biswal**
Salesforce Developer | Agentforce Enthusiast | AI Explorer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin)](YOUR_LINKEDIN_URL)
[![Salesforce](https://img.shields.io/badge/Trailhead-Profile-00A1E0?style=for-the-badge&logo=salesforce)](YOUR_TRAILHEAD_URL)

---

## 📝 License

MIT License — Feel free to use this as inspiration for your own Agentforce projects!

---

<div align="center">
Made with 🌸 and Salesforce Agentforce
</div>
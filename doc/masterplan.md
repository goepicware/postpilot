## masterplan.md

### 🚀 30-Second Elevator Pitch

**PostPilot** is an AI-powered social media scheduling platform built for small business owners, marketers, and creators. It helps users generate on-brand content fast, schedule posts smartly, and grow consistently—without burnout.

---

### 🧩 Problem & Mission

#### Problem:
Most small teams and solo creators struggle to post consistently on social media. They’re short on time, short on inspiration, and often post too little—or all at once.

#### Mission:
Make it effortless to plan, create, and publish social content that aligns with a brand’s voice and audience—without guesswork or overload.

---

### 🎯 Target Audience

- **Solo founders and SMB owners** managing their own marketing
- **Small marketing teams** juggling multiple platforms and clients
- **Creators/influencers** building personal brands without a social media manager

---

### 🧰 Core Features

- **AI Post Generator**
  - Generate posts from prompts, events, or product blurbs
  - Adjust tone (e.g., witty, professional) and intent (e.g., promo, educational)
  - Platform-specific previews

- **Brand Profile**
  - Custom fields: name, description, industry, tone, interests
  - Used by AI to tailor content suggestions and maintain consistency

- **Smart Scheduling Calendar**
  - Drag-and-drop post planning
  - Filters: platform, author, status
  - Auto-suggested times based on past engagement
  - Weekly performance summary

- **Post Approval Flow**
  - Optional review/approval step with comments and status

- **Auth & Integrations**
  - Email + OAuth login (LinkedIn, Facebook, Instagram)
  - Platform posting via API integrations

---

### 🛠 High-Level Tech Stack

- **Frontend:** React.js (w/ Vite) + TypeScript  
  → Fast dev, snappy UI, and scalable component structure

- **Styling:** Tailwind CSS + shadcn/ui  
  → Clean utility-first design, reusable UI primitives

- **Backend:** Node.js + Express  
  → Flexible REST API foundation with clean route handling

- **Database:** PostgreSQL (via Supabase or hosted)  
  → Secure, relational data for users, posts, and brands

- **Auth:** NextAuth.js or Passport.js  
  → OAuth + email/password with secure session management

- **AI:** OpenAI API + optional News API  
  → Smart content gen, trend detection, and contextual relevance

---

### 🧮 Conceptual Data Model (ERD in words)

- **User**
  - id, name, email, auth_provider
  - linked_social_accounts

- **BrandProfile**
  - user_id (FK), brand_name, description
  - tone, content_themes[], industry

- **Post**
  - id, brand_id, text, platform, status (draft, scheduled, sent), scheduled_time

- **Analytics**
  - post_id (FK), likes, comments, shares, reach, CTR

- **Approval**
  - post_id (FK), reviewer_id, status (pending, approved, rejected), comment

---

### 🎨 UI Design Principles

- **“Don’t Make Me Think”**: Content creation should feel guided, not overwhelming
- **Whitespace + Simplicity**: Minimalist dashboards, card-based layouts, soft grays + primary accents
- **Mobile-First**: Prioritize touch-friendly layouts and clear CTAs
- **AI Transparency**: Show how/why suggestions were made (pulling from Brand Profile)

---

### 🔐 Security & Compliance Notes

- OAuth with secure scopes (platform-specific)
- Rate-limiting & auth middleware on API routes
- Store tokens encrypted (JWT or Supabase)
- GDPR-compliant user data storage + deletion flow
- Secure-by-default Supabase policies (row-level auth)

---

### 🗺 Phased Roadmap

#### MVP (Now)
- Brand Profile
- AI Post Generator
- Content Calendar
- Basic Scheduling
- Auth + Integrations (manual posting or mock data)

#### V1
- Smart Scheduling (based on engagement)
- Full OAuth publishing (LinkedIn, FB, IG APIs)
- Approval workflow
- Platform-specific previews

#### V2
- Multi-user teams
- Collaboration tools (draft + comment threads)
- Deeper analytics (CTR trends, A/B testing)
- Trending topic detection via News API
- AI Assistant Chatbot

---

### ⚠️ Risks & Mitigations

- **Risk:** API limits or changes on social platforms  
  **Fix:** Fallback to manual copy + post or use buffer-like integrations

- **Risk:** AI generates off-brand or inaccurate posts  
  **Fix:** Require Brand Profile; show post history to improve accuracy; use tone selector

- **Risk:** Users overwhelmed by AI options  
  **Fix:** Pre-filled starter prompts, onboarding with examples, simple UI

---

### 🌱 Future Expansion Ideas

- Multi-brand dashboard for agencies
- Templates + post libraries
- Competitor benchmarking
- White-label version for coaches/agencies
- Mobile app for on-the-go scheduling

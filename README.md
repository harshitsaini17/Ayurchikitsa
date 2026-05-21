# AyurChikitsa

A **Next.js-based Ayurvedic telemedicine platform** connecting patients with Ayurvedic healthcare practitioners. Features a modern landing page, AI-powered skin analysis dashboard, real-time chat via Stream, and admin tools for patient engagement.

## What It Does

AyurChikitsa (Sanskrit: "Ayurvedic Treatment") bridges traditional Ayurvedic medicine with modern technology by providing:
- An engaging landing page for patient acquisition
- A patient dashboard with AI-assisted skin and health analysis
- Real-time chat integration with doctors
- Newsletter subscription and content scheduling tools

## Features

| Feature | Description |
|---------|-------------|
| 🏠 **Landing Page** | Hero section, demo, how-it-works, FAQ, CTA |
| 🤖 **AI Skin Analysis** | Upload facial images for automated Ayurvedic skin assessment |
| 💬 **Doctor Chat** | Real-time messaging powered by Stream (GetStream.io) |
| 📅 **Content Scheduler** | Admin tool for planning and scheduling content |
| 📧 **Newsletter** | Email subscription capture with server actions |
| 🔐 **Clerk Auth** | Secure authentication with SSO support |
| 🎨 **Framer Motion** | Smooth scroll-triggered animations |

## Tech Stack

| Layer | Technology |
|-------|------------|
| Framework | Next.js 15 (App Router) |
| Language | TypeScript |
| Styling | Tailwind CSS v4 |
| UI | shadcn/ui + Radix primitives |
| Animation | Framer Motion |
| Auth | Clerk |
| Chat | Stream Chat |
| Fonts | Inter |

## Project Structure

```
Ayurchikitsa/
├── src/
│   ├── app/
│   │   ├── page.tsx                        # Landing page
│   │   ├── about/page.tsx                  # About page
│   │   ├── contact/page.tsx              # Contact form
│   │   ├── dashboard/
│   │   │   ├── page.tsx                    # Patient dashboard
│   │   │   ├── analysis/page.tsx           # AI skin analysis
│   │   │   ├── chat/page.tsx               # Doctor chat (Stream)
│   │   │   ├── layout.tsx                  # Dashboard sidebar + navbar
│   │   │   └── components/
│   │   │       ├── Analysis.tsx
│   │   │       ├── Chat.tsx
│   │   │       └── Navbar.tsx
│   │   ├── api/
│   │   │   ├── get-stream-token/route.ts # Stream token generation
│   │   │   └── image/route.ts              # Image processing API
│   │   ├── sso-callback/page.tsx           # Clerk SSO handler
│   │   ├── components/
│   │   │   ├── contact-form.tsx
│   │   │   ├── how-it-works.tsx
│   │   │   ├── system-architecture.tsx
│   │   │   └── tech-stack.tsx
│   │   └── layout.tsx
│   ├── components/
│   │   ├── Navbar.tsx
│   │   ├── Hero.tsx
│   │   ├── DemoSection.tsx
│   │   ├── FeaturesSection2.tsx
│   │   ├── HowItWorks2.tsx
│   │   ├── FAQSection.tsx
│   │   ├── ContentScheduler.tsx
│   │   └── BouncingBallsLoader.tsx
│   └── actions/
│       ├── index.ts
│       └── subscribeUser.ts
├── public/
└── package.json
```

## Key Screens

### Landing Page (`/`)
- Animated hero with call-to-action
- Demo section (video/image showcase)
- How-it-works explainer
- FAQ accordion
- Final CTA banner

### Dashboard (`/dashboard`)
- Sidebar navigation
- Stats overview
- Quick actions

### AI Analysis (`/dashboard/analysis`)
- Upload facial image
- AI-powered skin assessment
- Ayurvedic dosha insights

### Doctor Chat (`/dashboard/chat`)
- Real-time messaging with Stream
- WebRTC-ready for video calls

## Getting Started

```bash
npm install

# Set environment variables
cp .env.example .env
# Add Clerk keys, Stream API credentials

npm run dev
# → http://localhost:3000
```

### Required Environment Variables

```env
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_...
CLERK_SECRET_KEY=sk_test_...
NEXT_PUBLIC_STREAM_KEY=...
STREAM_SECRET=...
```

## Server Actions

```typescript
// Subscribe to newsletter
async function subscribeUser(formData: FormData) {
  const email = formData.get('email');
  // Simulate API call
}
```

## Design

- Warm orange and white color palette (Ayurveda-inspired)
- Large rounded corners (2rem on desktop)
- Clean Inter typography
- Mobile-first responsive breakpoints

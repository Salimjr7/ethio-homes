<div align="center">

# 🇪🇹 Habesha Home (EthioHome)
### Full-Stack Ethiopian Home Rental Marketplace — Web & Mobile

[![Next.js](https://img.shields.io/badge/Next.js-15.2-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-38B2AC?style=for-the-badge&logo=tailwind-css)](https://tailwindcss.com/)
[![Prisma](https://img.shields.io/badge/Prisma-6-2D3748?style=for-the-badge&logo=prisma)](https://www.prisma.io/)
[![Capacitor](https://img.shields.io/badge/Capacitor-8-119EFF?style=for-the-badge&logo=capacitor)](https://capacitorjs.com/)

A production-grade vacation rental and residential marketplace crafted specifically for the Ethiopian ecosystem. Unifying premier web experiences with native mobile capabilities and localized payment rails.

[Explore Architecture](docs/ARCHITECTURE.md) • [Quick Start](#-quick-start) • [Demo Accounts](#-demo-accounts) • [Mobile App](#-mobile-app-capacitor-8)

</div>

---

## ⚡ Highlights & Ethiopian Context

- 💳 **Localized Financial Infrastructure:** Native payment processing with **Chapa** (Cards, CBEBirr, Awash, Dashen) & **Telebirr** mobile money.
- 💡 **Habesha Living Assurances:** Verified badges for **24/7 Standby Generator**, **Water Reservoir Tank**, and **High-Speed Fiber Internet**.
- 📱 **Cross-Platform Parity:** Responsive Web App + Native Android & iOS app powered by Capacitor 8.
- 🔒 **Financial Ledger & Escrow:** Immutable transaction logs with automated host payouts and audit trails.
- ⚡ **Atomic Booking Engine:** Zero double-booking concurrency guarantees with deterministic server-side pricing & 15% Ethiopian VAT breakdown.

---

## 🏗️ Architecture & Tech Stack

| Layer | Technologies |
|---|---|
| **Frontend & Web** | Next.js 15 (App Router, Server Components & Server Actions), React 19, Framer Motion, Lucide Icons |
| **Mobile Runtime** | Capacitor 8 (`@capacitor/android`, `@capacitor/haptics`, `@capacitor/network`, `@capacitor/status-bar`) |
| **Styling** | Tailwind CSS v4, Warm Ethiopian Gold design system, Light & Dark themes |
| **Backend & Database** | PostgreSQL (Neon Serverless), Prisma ORM v6, REST Route Handlers |
| **Auth & Security** | Better-Auth (sessions, cookies), CASL.js isomorphic RBAC (`GUEST`, `RENTER`, `OWNER`, `ADMIN`), Zod |
| **Payments** | Chapa API & Telebirr Mobile Money abstraction layers with sandbox simulator |

> 📖 **Deep Dive:** For full architectural diagrams and data flow specs, refer to [**`docs/ARCHITECTURE.md`**](docs/ARCHITECTURE.md).

---

## 🚀 Quick Start

### 1. Prerequisites
- Node.js `20.x` or `22.x`
- PostgreSQL instance (e.g. [Neon](https://neon.tech))

### 2. Clone & Install
```bash
git clone https://github.com/Salimjr7/habesha-home.git
cd habesha-home
npm install --legacy-peer-deps
```

### 3. Environment Variables
Create a `.env` file in the project root:
```env
DATABASE_URL="postgresql://user:password@ep-host.neon.tech/neondb?sslmode=require"
DIRECT_URL="postgresql://user:password@ep-host.neon.tech/neondb?sslmode=require"

BETTER_AUTH_SECRET="your-32-char-random-secret"
BETTER_AUTH_URL="http://localhost:3000"
NEXT_PUBLIC_APP_URL="http://localhost:3000"

CHAPA_PUBLIC_KEY="CHAPUBK_TEST-sample_public_key"
CHAPA_SECRET_KEY="CHASECK_TEST-sample_secret_key"
TELEBIRR_APP_ID="sample_telebirr_app_id"
TELEBIRR_APP_KEY="sample_telebirr_app_key"
```

### 4. Database Setup & Seeding
```bash
npx prisma db push
npx prisma generate
npm run db:seed
```

### 5. Start Development Server
```bash
npm run dev
```
Visit **[http://localhost:3000](http://localhost:3000)** in your browser.

---

## 📱 Mobile App (Capacitor 8)

The project includes an Android application inside `./android`.

### Run / Build Android App:
```bash
# Sync web assets and plugins to Android project
npx cap sync android

# Open in Android Studio
npx cap open android
```

Pre-built debug APKs are available:
- [`EthioHome-fixed.apk`](EthioHome-fixed.apk)
- [`EthioHome-debug.apk`](EthioHome-debug.apk)

---

## 👥 Demo Accounts

The database seed provides ready-to-test accounts:

| Role | Email | Password | Capabilities |
|---|---|---|---|
| **Renter** | `renter@habeshahome.et` | `Password123!` | Explore, book stays, simulated Chapa/Telebirr checkout, leave reviews |
| **Host / Owner** | `dawit@habeshahome.et` | `Password123!` | Host Hub, property management, pricing calendar, wallet withdrawals |
| **Admin** | `admin@habeshahome.et` | `Password123!` | System metrics, financial audit logs, property & payout verification |

---

## 📄 License & Credits

Developed by **[Salim](https://github.com/Salimjr7)**.

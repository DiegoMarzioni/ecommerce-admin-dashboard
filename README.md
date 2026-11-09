<div align="center">
  <h1>E-commerce Admin Dashboard</h1>

  <p>Back-office for an online store: manage products, brands, categories and orders, with sales metrics.</p>

  <img src="https://img.shields.io/badge/Next.js_16-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js"/>
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript"/>
  <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind"/>
  <img src="https://img.shields.io/badge/NestJS_11-E0234E?style=flat-square&logo=nestjs&logoColor=white" alt="NestJS"/>
  <img src="https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma&logoColor=white" alt="Prisma"/>
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
</div>

---

## Features

- 🔐 Admin sign up and login with JWT, stored in cookies
- 📦 CRUD for **products**, **brands** and **categories**
- 🧾 **Orders** management, with customers, order items and status history
- 📊 **Dashboard** with sales, earnings and statistics views, with charts (Recharts)
- 🧾 Forms with validation (Formik + Yup) and toast notifications
- 🌱 Seed scripts to populate the database with admins and sample orders

## Tech stack

| Layer | Technologies |
|---|---|
| Frontend | Next.js 16 (App Router), React, TypeScript, Tailwind CSS, Radix UI, Recharts, Formik, Yup |
| Backend | NestJS 11, Prisma ORM, JWT authentication |
| Database | PostgreSQL |

## Data model

`User` (admins) · `Category` · `Brand` · `Product` · `Customer` · `Order` · `OrderItem` · `OrderHistory`

## Architecture

```
ecommerce-admin-dashboard/
├── back/                  # NestJS API
│   ├── prisma/            # Schema, migrations and seeds
│   └── src/
│       ├── auth/
│       ├── products/
│       ├── brands/
│       ├── categories/
│       ├── orders/
│       ├── dashboard/     # Metrics endpoints
│       └── seeds/
└── front/                 # Next.js App Router
    └── src/
        ├── app/           # login, register, dashboard
        ├── lib/           # cookies and helpers
        └── services/      # API clients
```

## Getting started

**Requirements:** Node.js 18+ and a PostgreSQL database.

```bash
git clone https://github.com/DiegoMarzioni/ecommerce-admin-dashboard.git
cd ecommerce-admin-dashboard

# Backend
cd back
cp .env.example .env          # DATABASE_URL, JWT_SECRET, JWT_EXPIRES_IN, PORT
npm install
npx prisma migrate deploy
npm run start:dev

# Frontend (in another terminal)
cd front
cp .env.local.example .env.local   # NEXT_PUBLIC_API_URL and Cloudinary settings
npm install
npm run dev
```

## History

This repository unifies three earlier repositories (the original monorepo plus separate frontend and backend repos used for deployment), keeping the full commit history of each.

## Author

**Diego Marzioni** · [LinkedIn](https://www.linkedin.com/in/diego-marzioni/) · [GitHub](https://github.com/DiegoMarzioni)

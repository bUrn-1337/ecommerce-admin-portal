# 🛒ECommerce-Admin-Portal — Server-Rendered E-Commerce Admin Portal

**ECommerce-Admin-Portal** is a robust, server-side rendered (SSR) administrative dashboard designed to manage e-commerce inventory and sales performance. Built for scalability and production readiness, this application allows store administrators to control multiple aspects of an online store via a headless architecture.

## 🎯 Objective

The primary objective was to architect a production-grade CMS that ensures:
* **Production Readiness** — Fully containerized with Docker for consistent deployment on any infrastructure.
* **Headless Architecture** — Serves as a central API provider for customer-facing storefronts.
* **Secure Administration** — Protected routes and robust authentication for store managers.

The application is containerized using **Docker** for consistent deployment and hosts its database on **PostgreSQL**. It is currently deployed on an **Azure Virtual Machine** using Nginx as a reverse proxy.

## ✨ Key Features

* **Dashboard Analytics:** Visual overview of total revenue, sales count, and stock levels.
* **Product Management:** Create, update, and delete products with rich text descriptions.
* **Image Management:** Seamless image uploads and hosting via **Cloudinary**.
* **Category & Billboard Management:** Organize products into specific categories and marketing billboards.
* **Authentication:** Secure admin login using **NextAuth.js**.
* **API Support:** Auto-generated API endpoints to serve data to a customer-facing storefront (Headless CMS architecture).
* **Dark Mode:** Built-in UI adaptability.

## 🛠️ Tech Stack

**Frontend & Framework**
* [Next.js](https://nextjs.org/) (App Router)
* [React](https://reactjs.org/)
* [Tailwind CSS](https://tailwindcss.com/) (Styling)
* [TypeScript](https://www.typescriptlang.org/)

**Backend & Database**
* [PostgreSQL](https://www.postgresql.org/) (Database)
* [Prisma](https://www.prisma.io/) (ORM)
* [NextAuth.js](https://next-auth.js.org/) (Authentication)

**Infrastructure & DevOps**
* [Docker](https://www.docker.com/) & Docker Compose
* [Microsoft Azure](https://azure.microsoft.com/) (VM Hosting)
* [Nginx](https://www.nginx.com/) (Reverse Proxy)
* [Cloudinary](https://cloudinary.com/) (Image CDN)

## 🚀 Setup Instructions

### Prerequisites
* Node.js (v18+)
* Docker & Docker Compose
* Git
## ⚡ Setup & Installation

### 1. Clone the Repository
```bash
git clone [https://github.com/bUrn-1337/ecommerce-admin-portal](https://github.com/bUrn-1337/ecommerce-admin-portal)
cd ecommerce-admin-portal
```
### 2. Environment Configuration
Create a .env file in the project root:

Code snippet
```env
DATABASE_URL="postgresql://postgres:password123@localhost:5432/ecommerce_db?schema=public"
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME="your_cloud_name"
NEXTAUTH_SECRET="your_secret_key"
NEXTAUTH_URL="http://localhost:3000"
```
### 3. Run with Docker (Recommended)
Since this project is containerized, you can spin it up instantly:

```bash
docker compose up -d --build
```
### 4. Database Initialization
the dockerisation takes care of this, by running the seed script 


### 5. Access the Dashboard
Open http://localhost:3000 to access the application.
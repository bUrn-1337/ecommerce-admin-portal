# 🛒ECommerce-Admin-Portal — Server-Rendered E-Commerce Admin Portal

**ECommerce-Admin-Portal** is a robust, server-side rendered (SSR) administrative dashboard designed to manage e-commerce inventory and sales performance. Built for scalability and production readiness, this application allows store administrators to control multiple aspects of an online store via a headless architecture.

## 🎯 Objective

The primary objective was to architect a production-grade CMS that ensures:
* **Production Readiness** — Fully containerized with Docker for consistent deployment on any infrastructure.
* **Headless Architecture** — Serves as a central API provider for customer-facing storefronts.
* **Secure Administration** — Protected routes and robust authentication for store managers.

## 🚀 Key Features

### ⚡ Server-Side Rendering (SSR)
Utilizes **Next.js App Router** to fetch data securely on the server, ensuring optimal performance and SEO-friendly content delivery.

### 📦 Headless CMS Capabilities
Acts as a centralized backend, exposing public **API endpoints** for Products, Categories, and Billboards that can be consumed by any frontend client.

### 📊 Real-Time Analytics
Interactive dashboard visualizing total revenue, sales count, and stock levels to provide immediate business insights.

### 🖼️ Cloud-Native Media
Integrated **Cloudinary** support for optimized image uploading, storage, and delivery, replacing traditional local file storage.

### 🔐 Secure Authentication
Implemented **NextAuth.js** to handle secure admin sessions, protecting sensitive routes and database mutations.

### 🐳 Fully Containerized
Wrapped in **Docker** with a custom Nginx reverse proxy configuration, deployed live on a **Microsoft Azure Virtual Machine**.

## 🛠️ Tech Stack

| Component | Technology | Description |
| :--- | :--- | :--- |
| **Framework** | Next.js 14 | App Router & Server Actions |
| **Language** | TypeScript | Type safety & maintainability |
| **Database** | PostgreSQL | Relational data storage |
| **ORM** | Prisma | Schema management & type-safe queries |
| **DevOps** | Docker | Containerization & Orchestration |
| **Cloud** | Azure VM | Hosting infrastructure |
| **Storage** | Cloudinary | CDN for product images |
| **Styling** | Tailwind CSS | Utility-first responsive design |

## 🔄 Application Workflow

1.  **Request** — Nginx Proxy receives the request and forwards it to the Next.js container.
2.  **Auth Check** — NextAuth middleware validates the admin session.
3.  **SSR Fetch** — Server retrieves live inventory data from PostgreSQL.
4.  **Render** — Fully populated HTML is sent to the browser.
5.  **API Response** — External storefronts consume JSON data via `/api/products`.
6.  **Mutation** — Server Actions process updates (e.g., changing stock) and revalidate the cache.

## ⚡ Setup & Installation

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/nexus-commerce.git](https://github.com/your-username/nexus-commerce.git)
cd nexus-commerce
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
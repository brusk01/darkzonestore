# Darkzonestore - Gaming Accounts Marketplace

A comprehensive e-commerce platform for buying and selling gaming accounts (Steam, Xbox, PlayStation, Epic Games, etc.) with secure transactions and escrow system.

## 🚀 Features

### User Roles
- **Buyer**: Browse, purchase, review accounts
- **Seller**: List accounts, manage sales, track earnings
- **Admin**: Full system control, user management, dispute resolution
- **Moderator**: Content moderation, account approval

### Core Features
- ✅ Secure authentication (Email, Social Login, 2FA)
- ✅ Multi-platform support (Steam, Xbox, PS, Epic, etc.)
- ✅ Escrow payment system (Stripe, PayPal)
- ✅ Real-time chat between buyers and sellers
- ✅ Rating and review system
- ✅ Dispute management
- ✅ Advanced search and filters
- ✅ Wishlist functionality
- ✅ Notification system (Email, In-app)
- ✅ Admin dashboard with analytics
- ✅ Multilingual support (Kurdish, Arabic, English)
- ✅ Responsive design (Mobile-first)
- ✅ Image upload and gallery
- ✅ SEO optimized

## 📋 Prerequisites

Before you begin, ensure you have:
- **Node.js** (v18.0.0 or higher)
- **npm** (v9.0.0 or higher)
- **Supabase Account** (for database and authentication)
- **Stripe Account** (for payments)
- **PayPal Developer Account** (for PayPal payments)

## 🛠️ Installation

### 1. Install Node.js
Download and install Node.js from: https://nodejs.org/

### 2. Install Dependencies
```bash
cd darkzonestore
npm install
```

### 3. Set Up Environment Variables
Copy `.env.example` to `.env`:
```bash
copy .env.example .env
```

Edit `.env` and fill in your credentials:

```env
# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key

# Stripe
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret

# PayPal
NEXT_PUBLIC_PAYPAL_CLIENT_ID=your_paypal_client_id
PAYPAL_CLIENT_SECRET=your_paypal_client_secret
```

### 4. Set Up Supabase Database

1. Create a new Supabase project at https://supabase.com
2. Go to the SQL Editor in your Supabase dashboard
3. Copy the content from `supabase/schema.sql`
4. Run the SQL to create all tables and relationships

### 5. Run Development Server
```bash
npm run dev
```

Visit `http://localhost:3000` to see your application.

## 📁 Project Structure

```
darkzonestore/
├── app/                      # Next.js 14 app directory
│   ├── (auth)/              # Authentication pages
│   ├── (buyer)/             # Buyer dashboard
│   ├── (seller)/            # Seller panel
│   ├── (admin)/             # Admin panel
│   ├── browse/              # Browse accounts
│   ├── account/[id]/        # Account details
│   ├── api/                 # API routes
│   ├── layout.tsx           # Root layout
│   ├── page.tsx             # Homepage
│   └── globals.css          # Global styles
├── components/              # Reusable components
│   ├── ui/                  # UI components (Button, Input, etc.)
│   ├── layout/              # Layout components (Header, Footer)
│   ├── auth/                # Auth components
│   ├── account/             # Account components
│   └── providers.tsx        # App providers
├── lib/                     # Utility libraries
│   ├── supabase/            # Supabase clients
│   ├── utils.ts             # Helper functions
│   └── validations.ts       # Zod schemas
├── types/                   # TypeScript types
│   ├── database.types.ts    # Database types
│   └── index.ts             # Common types
├── supabase/               # Supabase files
│   └── schema.sql          # Database schema
├── public/                 # Static assets
├── package.json            # Dependencies
├── tsconfig.json           # TypeScript config
├── tailwind.config.ts      # Tailwind config
└── next.config.js          # Next.js config
```

## 🗄️ Database Schema

The application uses PostgreSQL (via Supabase) with the following main tables:

- **users** - User accounts and profiles
- **platforms** - Gaming platforms (Steam, Xbox, etc.)
- **accounts** - Listed gaming accounts for sale
- **account_images** - Account screenshots and images
- **transactions** - Purchase transactions with escrow
- **reviews** - Buyer reviews for sellers
- **disputes** - Dispute management system
- **wishlists** - User saved accounts
- **notifications** - In-app notifications
- **chat_messages** - Real-time messaging
- **blog_posts** - Content management
- **settings** - App configuration
- **activity_logs** - Admin audit logs

## 🔐 Authentication Flow

1. **Registration**: Email + Password or Social Login (Google/Facebook)
2. **Email Verification**: Sent automatically upon registration
3. **Login**: JWT-based authentication with Supabase
4. **2FA** (Optional): TOTP-based two-factor authentication
5. **Password Reset**: Email-based password recovery

## 💰 Payment Flow

1. Buyer selects account and proceeds to checkout
2. Payment processed via Stripe or PayPal
3. Funds held in escrow
4. Seller receives notification
5. Buyer receives account details
6. Buyer confirms delivery (or auto-confirm after 3 days)
7. Payment released to seller (minus commission)

## 🎨 Tech Stack

- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Database**: PostgreSQL (Supabase)
- **Authentication**: Supabase Auth
- **Payments**: Stripe, PayPal
- **State Management**: Zustand
- **Forms**: React Hook Form + Zod
- **UI Components**: Custom components + Radix UI
- **Notifications**: React Hot Toast
- **Icons**: Lucide React
- **Image Slider**: Swiper
- **Charts**: Recharts

## 📱 Pages Overview

### Public Pages
- Homepage - Hero, features, platforms
- Browse Accounts - Search, filter, pagination
- Account Details - Gallery, specs, seller info
- How It Works - Process explanation
- About, FAQ, Contact - Information pages

### Buyer Pages
- Dashboard - Overview, recent activity
- Purchase History - Past transactions
- Wishlist - Saved accounts
- Profile Settings - Personal info

### Seller Pages
- Dashboard - Stats, earnings, charts
- My Accounts - Active/Pending/Sold listings
- Add New Account - Listing creation form
- Sales History - Transaction history
- Earnings - Revenue and payouts

### Admin Pages
- Dashboard - System overview, statistics
- Users Management - User CRUD operations
- Accounts Management - Approve/Reject listings
- Transactions - Payment oversight
- Disputes - Conflict resolution
- Reports & Analytics - Business intelligence
- Settings - System configuration

## 🔧 Development Commands

```bash
# Development server
npm run dev

# Build for production
npm run build

# Start production server
npm start

# Type checking
npm run type-check

# Linting
npm run lint
```

## 🚀 Deployment

### Deploy to Vercel (Recommended)

1. Push your code to GitHub
2. Import project in Vercel
3. Add environment variables
4. Deploy

### Environment Variables for Production

Make sure to add all environment variables from `.env.example` to your hosting platform.

## 🔒 Security Features

- SQL Injection protection (Parameterized queries)
- XSS protection (React built-in)
- CSRF protection (SameSite cookies)
- Rate limiting (API routes)
- Input validation (Zod schemas)
- Row Level Security (RLS) on Supabase
- Encrypted sensitive data
- Secure payment processing (PCI compliant)

## 📝 Next Steps

1. **Install Node.js** if not already installed
2. **Run `npm install`** to install dependencies
3. **Set up Supabase** project and database
4. **Configure environment variables**
5. **Set up Stripe** and PayPal accounts
6. **Run `npm run dev`** to start development

## 🆘 Support

For issues and questions:
- Check the FAQ section
- Review the documentation
- Contact support team

## 📄 License

All rights reserved - Darkzonestore 2024

---

**Built with ❤️ for the gaming community**

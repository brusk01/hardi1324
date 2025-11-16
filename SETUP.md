# DarkZoneStore - Setup Guide

## 🚀 Quick Start

### 1. Install Dependencies

```bash
npm install
```

### 2. Set Up Supabase

1. Create a new project at [supabase.com](https://supabase.com)
2. Go to SQL Editor and run the migration file: `supabase/migrations/001_initial_schema.sql`
3. Enable Storage and create a bucket named `account-images` with public access
4. Copy your Supabase URL and keys

### 3. Configure Environment Variables

Create a `.env.local` file in the root directory:

```env
# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key

# Stripe (Optional - for payments)
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
STRIPE_SECRET_KEY=your_stripe_secret_key

# PayPal (Optional - for payments)
PAYPAL_CLIENT_ID=your_paypal_client_id
PAYPAL_CLIENT_SECRET=your_paypal_client_secret

# App URL
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

### 4. Run Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 📁 Project Structure

```
darkzonestore/
├── app/
│   ├── (admin)/          # Admin panel pages
│   │   ├── dashboard/
│   │   ├── users/
│   │   ├── accounts/
│   │   ├── transactions/
│   │   ├── disputes/
│   │   └── settings/
│   ├── (auth)/           # Authentication pages
│   │   └── login/
│   ├── (buyer)/          # Buyer dashboard (to be implemented)
│   ├── (main)/           # Public pages
│   │   ├── page.tsx      # Homepage
│   │   └── accounts/
│   ├── (seller)/         # Seller panel
│   │   ├── dashboard/
│   │   └── accounts/
│   ├── api/              # API routes
│   │   └── accounts/
│   ├── layout.tsx
│   └── globals.css
├── components/
│   ├── admin/            # Admin components
│   ├── seller/           # Seller components
│   ├── accounts/         # Account-related components
│   └── layout/           # Layout components
├── lib/
│   ├── supabase/         # Supabase clients
│   └── utils.ts          # Utility functions
├── supabase/
│   └── migrations/        # Database migrations
└── types/
    └── database.ts       # TypeScript types
```

## 🎯 Features Implemented

### ✅ Completed

- [x] Project setup with Next.js 14, TypeScript, Tailwind CSS
- [x] Database schema and migrations
- [x] Admin panel with full management features:
  - Dashboard with stats
  - Users management
  - Accounts management
  - Transactions management
  - Disputes management
  - Settings (General, Payment, Security, Email, Design)
- [x] Seller panel:
  - Dashboard
  - Add new account form
  - Sales history
  - Earnings tracking
- [x] Public pages:
  - Homepage
  - Browse accounts page
  - Account details page
- [x] Layout components (Header, Footer)
- [x] API routes for accounts

### 🚧 To Be Implemented

- [ ] Authentication system (JWT, email verification, social login)
- [ ] Payment integration (Stripe, PayPal) with Escrow
- [ ] Buyer dashboard
- [ ] Search and filter functionality (backend integration)
- [ ] Rating & review system
- [ ] Chat system
- [ ] Notification system
- [ ] Image upload with Supabase Storage
- [ ] SEO optimization
- [ ] Multilingual support (Kurdish, Arabic, English)

## 🔐 Default Admin Account

After running the migration, you can log in with:
- Email: `admin@darkzonestore.com`
- Password: (needs to be set via Supabase Auth)

**Important:** Change the default admin password immediately after first login!

## 📝 Next Steps

1. **Set up Authentication:**
   - Configure Supabase Auth
   - Implement login/register pages
   - Add protected routes middleware

2. **Payment Integration:**
   - Set up Stripe account
   - Implement payment processing
   - Add Escrow system

3. **Complete Buyer Dashboard:**
   - Purchase history
   - Wishlist
   - Profile settings

4. **Add Real-time Features:**
   - Chat system (Socket.io or Supabase Realtime)
   - Notifications

5. **Deploy:**
   - Deploy to Vercel
   - Set up production environment variables
   - Configure custom domain

## 🛠️ Development Commands

```bash
# Development
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

## 📚 Documentation

- [Next.js Documentation](https://nextjs.org/docs)
- [Supabase Documentation](https://supabase.com/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [TypeScript Documentation](https://www.typescriptlang.org/docs)

## 🐛 Troubleshooting

### Database Connection Issues
- Verify Supabase credentials in `.env.local`
- Check if migration was run successfully
- Ensure Supabase project is active

### Image Upload Issues
- Create `account-images` bucket in Supabase Storage
- Set bucket to public access
- Check storage policies

### Build Errors
- Clear `.next` folder: `rm -rf .next`
- Reinstall dependencies: `rm -rf node_modules && npm install`
- Check TypeScript errors: `npm run type-check`

## 📄 License

MIT


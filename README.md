# DarkZoneStore

A complete e-commerce platform for buying and selling online gaming accounts (Steam, Xbox, PlayStation, Epic Games, etc.)

## Features

- **Multi-role System**: Buyers, Sellers, Admins, and Moderators
- **Account Marketplace**: Browse, search, and filter gaming accounts
- **Secure Payments**: Stripe and PayPal integration with Escrow system
- **Rating & Reviews**: Verified buyer reviews
- **Real-time Chat**: Communication between buyers, sellers, and support
- **Admin Panel**: Complete management system
- **Responsive Design**: Works on all devices
- **Multilingual**: Kurdish, Arabic, English support

## Tech Stack

- **Frontend**: Next.js 14, React, TypeScript, Tailwind CSS
- **Backend**: Supabase (PostgreSQL, Auth, Storage)
- **Payments**: Stripe, PayPal
- **Real-time**: WebSocket (Socket.io)
- **State Management**: Zustand
- **Forms**: React Hook Form + Zod

## Getting Started

1. Install dependencies:
```bash
npm install
```

2. Set up environment variables:
```bash
cp .env.example .env.local
```

3. Run the development server:
```bash
npm run dev
```

4. Open [http://localhost:3000](http://localhost:3000) in your browser.

## Environment Variables

```env
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_service_role_key
STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
STRIPE_SECRET_KEY=your_stripe_secret_key
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

## Project Structure

```
├── app/                    # Next.js app directory
│   ├── (auth)/            # Authentication pages
│   ├── (buyer)/           # Buyer dashboard
│   ├── (seller)/          # Seller panel
│   ├── (admin)/           # Admin panel
│   └── api/               # API routes
├── components/            # React components
├── lib/                   # Utilities and helpers
├── hooks/                 # Custom React hooks
├── store/                 # Zustand stores
├── types/                 # TypeScript types
└── supabase/             # Supabase migrations and config
```

## License

MIT


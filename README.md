# JS FASHION

A colourful girls-fashion storefront starter built with Next.js and Supabase.

## Included
- Trendy colourful storefront (responsive)
- INR pricing
- Product listing from Supabase `products` table
- Add-to-bag interaction (browser session only)
- No payment gateway enabled

## Supabase setup
1. In Supabase, open **Project Settings → API** (or API Keys).
2. Copy the **Project URL** and the **publishable/anon key**. Never use or share the `service_role` / secret key in browser code.
3. Create `.env.local` in the project root using `.env.example` as a guide:

```env
NEXT_PUBLIC_SUPABASE_URL=https://YOUR_PROJECT_ID.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=YOUR_PUBLISHABLE_OR_ANON_KEY
```

4. The storefront currently expects `public.products` to have at least: `id`, `name`, `price`, `is_active`, and optionally `description`, `image_url`, `created_at`. If your table uses different column names, adjust `app/page.tsx` to match your actual schema before deploying.
5. Ensure the public SELECT RLS policy allows visitors to read active products. Product images can be stored in the `product-images` public bucket.

## Run locally

```bash
npm install
npm run dev
```

Open http://localhost:3000.

## Important
This is the storefront starter, not the complete production store yet. Admin dashboard, checkout/order saving, and payment integration are not included. Do not add Supabase service-role keys to `NEXT_PUBLIC_` variables or commit secrets to GitHub.

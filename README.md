# Luxury Editorial Store + Admin Room

This project recreates the overall visual language and flow of the supplied reference video as a real Next.js storefront, then adds a private admin room for product management.

## Included

- Editorial/luxury homepage with large typography and cinematic image blocks
- Product listing and product detail pages
- FAQ and contact pages
- Scroll reveal animations with Framer Motion
- Shopping bag drawer stored in localStorage
- Admin login with signed HTTP-only cookie
- Admin dashboard
- Add / edit / delete products
- Publish / draft and featured controls
- Postgres + Prisma data model
- Seed script with demo products

## Setup

1. Install Node.js 20+.
2. Copy `.env.example` to `.env.local`.
3. Set `DATABASE_URL` to a Postgres database.
4. Set `AUTH_SECRET` to a long random value.
5. Set `ADMIN_EMAIL`.
6. Generate a bcrypt hash and set `ADMIN_PASSWORD_HASH`.
7. Run:

```bash
npm install
npx prisma generate
npx prisma db push
npm run db:seed
npm run dev
```

Open `http://localhost:3000` for the store and `http://localhost:3000/admin` for the admin room.

For local development only, if `ADMIN_PASSWORD_HASH` is omitted, the fallback password is `admin123`. Do not use that in production.

## Image uploads

The current admin form accepts image URLs so the project stays storage-provider agnostic. For production, the next step is adding Vercel Blob/S3 upload and saving those URLs into `imageUrl` and `gallery`.

## Important

The video was recorded from a screen, so exact copy, image assets, product names and some micro-interactions cannot be recovered with certainty. The structure, visual direction, typography, spacing, large editorial imagery, product flow and motion are implemented as a working base that can be tuned against the original reference.

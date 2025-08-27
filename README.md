This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.


## Install and Run

### Preferred (lockfile exact versions)
```bash
cd ref-better-auth-tut
npm ci
```

### Fresh install (without using the lockfile)
- **Dependencies**
```bash
npm i next@15.3.1 react@19 react-dom@19 better-auth@1.2.7 @prisma/client@6.7.0 @node-rs/argon2 @radix-ui/react-label @radix-ui/react-slot class-variance-authority clsx lucide-react next-themes nodemailer sonner tailwind-merge
```

- **Dev dependencies**
```bash
npm i -D prisma@6.7.0 typescript @types/node @types/react @types/react-dom eslint@^9 eslint-config-next@15.3.1 @eslint/eslintrc @tailwindcss/postcss@^4 tailwindcss@^4 tw-animate-css
```

### Database and Prisma
Ensure `.env` includes a valid Postgres connection string, then generate and migrate:
```bash
# .env must include DATABASE_URL, e.g.:
# DATABASE_URL="postgresql://USER:PASSWORD@HOST:PORT/DB_NAME?schema=public"

npx prisma generate
npx prisma migrate dev --name init
```

### Development
```bash
npm run dev
```

### Build and start
```bash
npm run build
npm start
```

### Optional lint
```bash
npm run lint
```

## Environment Variables
Add these variables to your `.env`:

- `DATABASE_URL`
- `ADMIN_EMAILS`
- `GOOGLE_CLIENT_ID`
- `GOOGLE_CLIENT_SECRET`
- `GITHUB_CLIENT_ID`
- `GITHUB_CLIENT_SECRET`
- `NODEMAILER_USER`
- `NODEMAILER_APP_PASSWORD`
- `NEXT_PUBLIC_API_URL`
- `NODE_ENV`

Example `.env` template:
```env
DATABASE_URL=
ADMIN_EMAILS=
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
GITHUB_CLIENT_ID=
GITHUB_CLIENT_SECRET=
NODEMAILER_USER=
NODEMAILER_APP_PASSWORD=
NEXT_PUBLIC_API_URL=http://localhost:3000/api/auth
NODE_ENV=development
```

Notes:
- **DATABASE_URL** is required for Prisma/PostgreSQL.
- **NEXT_PUBLIC_API_URL** is used by the Better Auth client (e.g., `http://localhost:3000/api/auth` in dev).
- OAuth providers require the corresponding **GOOGLE_*** and/or **GITHUB_*** values.
- Email sending requires **NODEMAILER_USER** and **NODEMAILER_APP_PASSWORD** (Gmail app password if using Gmail SMTP).
- **ADMIN_EMAILS** is optional; use a semi-colon separated list for auto-assigning the ADMIN role.


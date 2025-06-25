# Tube - YouTube Clone

A modern YouTube clone built with Next.js, featuring video upload, streaming, user authentication, and more.

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ 
- npm/yarn/pnpm
- PostgreSQL database (we recommend [Neon](https://neon.tech))

### Installation

1. **Clone and install dependencies:**
   \`\`\`bash
   git clone <your-repo>
   cd tube-main
   npm install
   \`\`\`

2. **Set up environment variables:**
   \`\`\`bash
   cp .env.example .env.local
   \`\`\`
   
   Fill in your actual values in `.env.local` (see setup guide below).

3. **Run database migrations:**
   \`\`\`bash
   npm run db:push
   \`\`\`

4. **Seed the database:**
   \`\`\`bash
   npm run db:seed
   \`\`\`

5. **Start the development server:**
   \`\`\`bash
   npm run dev
   \`\`\`

## 🔧 Environment Setup Guide

### 1. Database (Neon)
- Sign up at [Neon](https://neon.tech)
- Create a new project
- Copy the connection string to `DATABASE_URL`

### 2. Authentication (Clerk)
- Sign up at [Clerk](https://clerk.com)
- Create a new application
- Go to [API Keys](https://dashboard.clerk.com/last-active?path=api-keys)
- Copy `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY` and `CLERK_SECRET_KEY`
- Set up webhooks pointing to `your-domain.com/api/users/webhook`

### 3. Video Processing (Mux)
- Sign up at [Mux](https://mux.com)
- Go to Settings > Access Tokens
- Create a new token and copy `MUX_TOKEN_ID` and `MUX_TOKEN_SECRET`
- Set up webhooks pointing to `your-domain.com/api/videos/webhook`

### 4. File Storage (UploadThing)
- Sign up at [UploadThing](https://uploadthing.com)
- Create a new app
- Copy `UPLOADTHING_SECRET` and `UPLOADTHING_APP_ID`

### 5. Redis & QStash (Upstash)
- Sign up at [Upstash](https://upstash.com)
- Create a Redis database and copy the REST URL and token
- Create a QStash project and copy the token

## 📁 Project Structure

\`\`\`
src/
├── app/                 # Next.js App Router
├── components/          # Reusable UI components
├── modules/            # Feature modules
│   ├── auth/           # Authentication
│   ├── videos/         # Video management
│   ├── users/          # User profiles
│   └── ...
├── lib/                # Utilities and configurations
└── trpc/               # tRPC setup
\`\`\`

## 🛠 Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run db:push` - Push database schema
- `npm run db:seed` - Seed database with categories

## 🔒 Security Notes

- Never commit `.env.local` to version control
- Use strong, unique secrets for production
- Set up proper CORS and webhook security
- Enable rate limiting in production

## 📝 License

This project is licensed under the MIT License.

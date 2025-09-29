# 🚀 Compliance-as-Code – Install Guide

## Requirements
- Node.js 20+
- pnpm (enabled with `corepack enable`)
- Docker (for Postgres)

## Setup
```bash
# Clone repo
git clone git@github.com:YOURUSER/compliance-as-code.git
cd compliance-as-code

# Install dependencies
pnpm install

# Start Postgres
pnpm db:up

# Setup API
cp apps/cac-api/.env.example apps/cac-api/.env
pnpm --filter @cac/api prisma:gen
pnpm --filter @cac/api prisma:push
pnpm --filter @cac/api dev

# Setup Web
cd apps/cac-web
pnpm dev

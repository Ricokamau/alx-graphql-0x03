# ALX GraphQL 0x03 – Error Boundaries + Monitoring

This project adds an `ErrorBoundary` to a Next.js + Apollo Client app and integrates Sentry for error monitoring.

## Tasks

### 0) Create ErrorBoundary
- File: `components/ErrorBoundary.tsx`
- Class component with `getDerivedStateFromError`, `componentDidCatch`, and a fallback UI.

### 1) Wrap the App
- File: `pages/_app.tsx`
- Wrap `<Component />` with `<ErrorBoundary>` (inside `ApolloProvider`).

### 2) Test the Boundary
- File: `components/ErrorProneComponent.tsx` (throws in render)
- Temporarily render it in `pages/index.tsx` to verify fallback UI.

### 3) Monitor & Log Errors (Sentry)
- Install: `npm install @sentry/react @sentry/nextjs`
- Init files: `sentry.client.config.ts`, `sentry.server.config.ts`
- Add DSNs in `.env.local`:
  - `NEXT_PUBLIC_SENTRY_DSN=...`
  - `SENTRY_DSN=...`
- In `ErrorBoundary`, call `Sentry.captureException(error, { extra: errorInfo })`.

## Run
```bash
npm install
npm run dev
# open http://localhost:3000

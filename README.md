# CaseConnect

A consultation booking prototype for finding a professional, managing appointments and credits, and joining video calls.

## What it does

- Uses Clerk for sign-up, sign-in, and protected routes.
- Stores users, availability, appointments, credit transactions, and payout requests in PostgreSQL through Prisma.
- Provides professional verification and payout administration screens.
- Creates Vonage video sessions for booked appointments.
- Allocates credits from Clerk subscription plans and deducts two credits per appointment.

## Project status

The interface is being adapted for lawyer consultations, while the database, actions, and routes still use doctor/patient names. Some pages retain healthcare wording, and the homepage links to `/Lawyers` while directory routes use `/doctors`. Treat it as an unfinished consultation prototype.

## Built with

Next.js 15, React 19, Tailwind CSS 4, Prisma, PostgreSQL, Clerk, and Vonage Video API.

## How it works

Clerk identifies the signed-in user. Next.js server actions use Prisma to read availability, reserve appointments, and update the credit balance. A booked appointment can open a Vonage video session. Verification and payout requests have separate administrator screens.

## Getting started

The application lives in `main/`. Use Node.js and npm compatible with its Next.js dependencies, a development PostgreSQL database, and Clerk/Vonage accounts.

Before installing, create `main/.env` with `DATABASE_URL` pointing to your development database. Configure Clerk's application keys for the app, and the video credentials read by `actions/appointments.js`:

```dotenv
DATABASE_URL=postgresql://USER:PASSWORD@localhost:5432/caseconnect
NEXT_PUBLIC_VONAGE_APPLICATION_ID=your_vonage_application_id
VONAGE_PRIVATE_KEY=your_vonage_private_key
```

Use the private-key format supplied by Vonage. Keep credentials out of version control. The repository has no complete environment template or service provisioning guide.

```bash
cd main
npm install
npx prisma db push
npm run dev
```

Installation generates the Prisma client through the existing `postinstall` script. `prisma db push` changes the selected database schema; use a fresh development database. Open `http://localhost:3000` after Next.js starts.

## Local workflow

Sign in through Clerk, complete onboarding, and explore the professional directory and appointment pages. Appointment booking requires a verified professional, configured availability, enough credits, and working Vonage credentials. Clerk credit plans use the identifiers `free_user`, `standard`, and `premium`. Admin role provisioning and external account setup must be completed separately.

Payouts are recorded as requests for an administrator to process; the source does not send PayPal transfers. Clerk and Vonage service usage may incur charges.

## Structure

| Path | Purpose |
| --- | --- |
| `main/app/` | Pages, onboarding, dashboards, and video UI |
| `main/actions/` | Booking, credits, verification, and payouts |
| `main/prisma/schema.prisma` | Database models |
| `main/lib/` | Prisma connection and shared helpers |
| `main/components/` | UI components |

## Available checks

From `main/`, `npm run build` creates a production build and `npm run lint` invokes Next.js linting. `npm start` serves a completed build. No automated test script is defined.

## License

No license file is included.

# CaseConnect

CaseConnect is a modern web platform that facilitates seamless connections between lawyers and clients. Built with Next.js and leveraging modern web technologies, CaseConnect streamlines the process of finding legal representation and managing legal consultations.

## Features

- **User Authentication**: Secure sign-up and sign-in functionality for both lawyers and clients
- **Lawyer Directory**: Browse and search for lawyers by specialty
- **Online Appointments**: Schedule and manage virtual consultations
- **Video Consultations**: Built-in video calling feature for remote meetings
- **Credit System**: Flexible payment system for consultations
- **Admin Dashboard**: Comprehensive admin panel for platform management
- **Lawyer Verification**: Professional verification system for lawyers
- **Availability Management**: Lawyers can set and manage their availability
- **Secure Payments**: Integrated payout system for lawyers

## Tech Stack

- **Frontend**: Next.js 14, React, Tailwind CSS
- **Backend**: Next.js API Routes
- **Database**: PostgreSQL with Prisma ORM
- **Authentication**: Next-Auth
- **Real-time Communication**: WebRTC for video calls
- **UI Components**: Shadcn/ui
- **State Management**: React Hooks
- **Deployment**: Vercel

## Getting Started

1. Clone the repository:
```bash
git clone https://github.com/yourusername/case-connect.git
cd case-connect
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
Create a `.env` file in the root directory and add the following:
```env
DATABASE_URL="postgresql://..."
NEXTAUTH_SECRET="your-secret"
NEXTAUTH_URL="http://localhost:3000"
```

4. Run database migrations:
```bash
npx prisma migrate dev
```

5. Start the development server:
```bash
npm run dev
```

The application will be available at `http://localhost:3000`

## Project Structure

- `/app` - Next.js app router pages and layouts
- `/components` - Reusable React components
- `/actions` - Server actions for data mutations
- `/lib` - Utility functions and configurations
- `/prisma` - Database schema and migrations
- `/public` - Static assets

## Contributing

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature`
5. Submit a pull request


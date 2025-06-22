# Replit.md - Immunization Monitoring System

## Overview

This is a full-stack immunization monitoring system built for tracking children's vaccination records in Central Lombok Regency, Indonesia. The application provides comprehensive management of immunization data, SMS notifications, QR code scanning, reporting, and user management with role-based access control.

## System Architecture

The application follows a modern full-stack architecture with clear separation between frontend and backend:

- **Frontend**: React with TypeScript, using Vite for development and building
- **Backend**: Express.js with TypeScript running on Node.js
- **Database**: PostgreSQL with Drizzle ORM for type-safe database operations
- **Authentication**: Passport.js with local strategy and session-based authentication
- **UI Framework**: Tailwind CSS with shadcn/ui components
- **Deployment**: Configured for Replit with autoscale deployment

## Key Components

### Database Schema
The system uses a PostgreSQL database with the following main entities:
- **Users**: Admin, staff, and client roles with authentication
- **Children**: Child records with NIK (Indonesian ID), demographics, and parent info
- **Immunizations**: Vaccination records linked to children and administered by users
- **SMS Logs**: Message tracking with delivery status
- **Satisfaction Surveys**: Customer feedback collection
- **Reports**: Generated report metadata
- **Files**: File upload and management records

### Authentication & Authorization
- Role-based access control (admin, staff, client)
- Session-based authentication using connect-pg-simple
- Password hashing with scrypt for security

### Frontend Architecture
- Component-based React architecture with TypeScript
- React Query for server state management
- Wouter for client-side routing
- React Hook Form with Zod validation
- Responsive design with mobile support

### Backend Architecture
- RESTful API design with Express.js
- Modular route handlers
- Middleware for authentication and logging
- File upload support with Multer
- Type-safe database operations with Drizzle ORM

## Data Flow

1. **User Authentication**: Users log in through the auth page, credentials are validated against the database
2. **Dashboard**: Authenticated users see role-appropriate dashboard with statistics and quick actions
3. **Data Management**: CRUD operations for children, immunizations, and other entities
4. **SMS Integration**: Automated and manual SMS sending with template support
5. **QR Code Processing**: Scan QR codes to retrieve child immunization records
6. **File Management**: Upload and manage Excel, CSV, and PDF files
7. **Reporting**: Generate various reports based on immunization data

## External Dependencies

### Core Framework Dependencies
- React 18 with TypeScript
- Express.js for backend API
- PostgreSQL with Neon serverless
- Drizzle ORM for database operations

### UI and Styling
- Tailwind CSS for styling
- shadcn/ui component library
- Radix UI primitives for accessibility

### Authentication & Security
- Passport.js for authentication
- bcrypt/scrypt for password hashing
- Express sessions with PostgreSQL store

### File Processing
- Multer for file uploads
- Support for Excel, CSV, and PDF files

### Development Tools
- Vite for development server and building
- TSX for TypeScript execution
- ESBuild for server bundling

## Deployment Strategy

The application is configured for deployment on Replit with the following setup:

### Development
- Run `npm run dev` to start both frontend and backend in development mode
- Frontend served by Vite dev server with HMR
- Backend runs with TSX for TypeScript execution
- Database migrations with `npm run db:push`

### Production
- Build process: `npm run build` creates optimized frontend bundle and server build
- Frontend assets built to `dist/public` directory
- Server code bundled to `dist/index.js` with ESBuild
- Production start with `npm run start`

### Environment Configuration
- Database URL required for PostgreSQL connection
- Session secret required for authentication
- File upload directory created automatically

## Changelog

```
Changelog:
- June 22, 2025. Initial setup
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```
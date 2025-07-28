# REST Express AI Assistant System

## Overview

This is a full-stack web application called "TOBI TECH AI Assistant System" - a comprehensive marketing automation platform that provides AI-powered content generation, multi-platform social media management, email campaigns, and data synchronization capabilities. The application features a modern React frontend with a Node.js/Express backend, utilizing PostgreSQL for data persistence and integrating with various external services.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

The application follows a monorepo structure with clear separation between client, server, and shared components:

**Frontend Architecture:**
- React 18 with TypeScript for type safety
- Vite as the build tool and development server
- Wouter for client-side routing (lightweight alternative to React Router)
- TanStack Query for server state management and caching
- Tailwind CSS with shadcn/ui components for styling
- Dark theme design system with CSS custom properties

**Backend Architecture:**
- Node.js with Express.js REST API
- TypeScript throughout for consistency
- Modular service architecture with separated concerns
- In-memory storage with interface for easy database migration
- Middleware for request logging and error handling

**Build and Development:**
- ESM modules throughout the application
- Vite for frontend bundling and development
- esbuild for backend production builds
- TypeScript compilation with strict mode enabled

## Key Components

**Database Schema (shared/schema.ts):**
- Users: Authentication and user management
- Campaigns: Email and social media campaigns
- Social Posts: Platform-specific content management
- Email Senders: Multi-sender email configuration
- Automation Settings: System automation preferences
- API Integrations: External service configurations

**Core Services:**
- **OpenAI Service**: AI content generation using GPT-4o model
- **Telegram Service**: Automated posting to Telegram channels
- **Email Service**: Multi-sender email campaigns with rotation
- **Google Sheets Service**: Data synchronization and export

**Frontend Pages:**
- Dashboard: System overview with stats and activity feed
- Telegram Posts: Automated Telegram content management
- Email Campaigns: Multi-sender email marketing
- Social Media: Cross-platform content generation
- Google Sheets: Data synchronization
- Analytics: Performance metrics and insights
- Settings: API configuration and automation settings

**UI Components:**
- Comprehensive shadcn/ui component library
- Custom dashboard components (stats cards, activity feeds)
- Responsive layout with sidebar navigation
- Dark theme with consistent design tokens

## Data Flow

1. **Content Generation**: Users request AI-generated content through OpenAI integration
2. **Campaign Management**: Content is saved as campaigns or social posts
3. **Multi-Platform Distribution**: Content is distributed to various platforms (Telegram, social media, email)
4. **Data Synchronization**: Campaign data can be exported to Google Sheets
5. **Analytics**: Performance data is collected and displayed in analytics dashboard

**State Management:**
- TanStack Query handles server state with automatic caching
- Local component state for form data and UI interactions
- No global state management needed due to server-driven architecture

## External Dependencies

**Core Framework Dependencies:**
- React 18 with TypeScript
- Express.js with TypeScript
- Drizzle ORM for database operations
- Neon Database serverless PostgreSQL

**UI and Styling:**
- Tailwind CSS for utility-first styling
- Radix UI primitives for accessible components
- Lucide React for icons
- shadcn/ui component system

**External Service Integrations:**
- OpenAI API for content generation
- Telegram Bot API for automated posting
- Google Sheets API for data synchronization
- Nodemailer for email sending capabilities

**Development Tools:**
- Vite for development and building
- ESBuild for backend bundling
- TSX for TypeScript execution
- PostCSS for CSS processing

## Deployment Strategy

**Development Environment:**
- Vite dev server for frontend with HMR
- TSX for running TypeScript backend directly
- Environment variables for API keys and configurations

**Production Build:**
- Frontend: Vite builds static assets to `dist/public`
- Backend: ESBuild bundles server code to `dist/index.js`
- Single deployment artifact with both frontend and backend

**Database:**
- PostgreSQL via Neon Database (serverless)
- Drizzle migrations in `migrations/` directory
- Schema defined in shared TypeScript files

**Environment Configuration:**
- Database URL for PostgreSQL connection
- API keys for external services (OpenAI, Telegram, Google)
- Service account JSON for Google Sheets integration

**Scaling Considerations:**
- Stateless backend design enables horizontal scaling
- In-memory storage can be easily replaced with persistent database
- Service-oriented architecture allows for microservice migration
- API-first design enables mobile app development
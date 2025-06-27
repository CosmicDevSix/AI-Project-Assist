# AI Project Assist - Replit Configuration

## Overview

AI Project Assist is a full-stack web application designed to help developers and freelancers manage projects with AI-powered assistance. The application provides project tracking, margin analysis, and intelligent chat support for project management tasks.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query (React Query) for server state management
- **Styling**: Tailwind CSS with shadcn/ui component library
- **Form Handling**: React Hook Form with Zod validation
- **Build Tool**: Vite with custom configuration for development and production

### Backend Architecture
- **Runtime**: Node.js with TypeScript
- **Framework**: Express.js for REST API
- **Database ORM**: Drizzle ORM with PostgreSQL dialect
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Session Management**: connect-pg-simple for PostgreSQL session storage
- **AI Integration**: OpenAI GPT-4o for intelligent project assistance

### Development Setup
- **Monorepo Structure**: Shared schema and types between client and server
- **Development Server**: Vite dev server with HMR for frontend, tsx for backend hot reload
- **Build Process**: Vite for frontend bundling, esbuild for backend compilation

## Key Components

### Database Schema
The application uses a PostgreSQL database with two main tables:
- **Projects**: Stores project information including estimates vs actuals for time, budget, and resources
- **Chat Messages**: Stores AI conversation history linked to specific projects

### API Structure
REST API endpoints organized around:
- Project CRUD operations (`/api/projects`)
- Statistics aggregation (`/api/stats`)
- AI chat functionality (`/api/chat`)

### Frontend Components
- **Dashboard**: Main project overview with statistics and project grid
- **Project Cards**: Individual project display with margin calculations
- **Project Modal**: Tabbed interface for project creation/editing
- **AI Assistant**: Floating chat interface with OpenAI integration
- **Stats Overview**: Key performance indicators dashboard

## Data Flow

1. **Project Management**: Users create and manage projects through modal forms
2. **Margin Tracking**: System calculates time, budget, and resource margins in real-time
3. **AI Assistance**: Users can ask questions about projects, receiving contextual responses
4. **Statistics**: Dashboard aggregates project data for overview metrics

## External Dependencies

### Core Dependencies
- **Database**: Neon Database (PostgreSQL-compatible serverless database)
- **AI Service**: OpenAI API for chat completions
- **UI Components**: Radix UI primitives via shadcn/ui
- **Styling**: Tailwind CSS with custom design system

### Development Dependencies
- **Replit Integration**: Vite plugins for Replit-specific features
- **Error Handling**: Runtime error overlay for development
- **Code Mapping**: Source map support for debugging

## Deployment Strategy

### Build Process
1. Frontend builds to `dist/public` directory
2. Backend compiles to `dist/index.js` as ESM bundle
3. Static assets served by Express in production

### Environment Variables
- `DATABASE_URL`: PostgreSQL connection string (required)
- `OPENAI_API_KEY` or `OPENAI_KEY`: OpenAI API key for AI features
- `NODE_ENV`: Environment mode (development/production)

### Production Deployment
- Single Node.js process serving both API and static files
- Database migrations handled via Drizzle Kit
- Session storage backed by PostgreSQL

## Changelog

```
Changelog:
- June 27, 2025. Initial setup
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```
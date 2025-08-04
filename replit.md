# Producer Hub

## Overview

Producer Hub is a comprehensive music production resource platform designed to help producers discover software, tutorials, samples, and tools for music creation. The application serves as a centralized hub for music production resources with a dark, gothic-themed interface that caters to modern producers looking for both free and premium resources.

The platform features a single-page application with dedicated sections for DAW software, tutorial libraries, sample collections, and essential production tools. It includes community integration features and a search functionality to help users find specific resources quickly.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript for type safety and modern development practices
- **Routing**: Wouter for lightweight client-side routing
- **UI Components**: Shadcn/ui component library built on Radix UI primitives for accessible, customizable components
- **Styling**: Tailwind CSS with custom CSS variables for theming, including a gothic dark theme with red accent colors
- **Fonts**: Google Fonts integration (Cinzel family for headings, Inter for body text) to create a distinctive visual identity
- **State Management**: TanStack Query (React Query) for server state management and data fetching
- **Build Tool**: Vite for fast development and optimized production builds

### Backend Architecture
- **Runtime**: Node.js with Express.js framework for RESTful API endpoints
- **Language**: TypeScript for full-stack type safety
- **Database**: PostgreSQL with Drizzle ORM for type-safe database operations
- **Session Management**: Connect-pg-simple for PostgreSQL-backed session storage
- **Development**: Memory storage implementation for development/testing with seeded data

### Data Storage
- **ORM**: Drizzle ORM with PostgreSQL dialect for production deployments
- **Schema**: Shared schema definitions between frontend and backend using Drizzle-Zod for validation
- **Database Models**: Users table for authentication and resources table for content management with categories, subcategories, and metadata

### API Structure
- **Resources API**: RESTful endpoints for CRUD operations on music production resources
  - GET /api/resources - Retrieve all resources
  - GET /api/resources/category/:category - Filter by category
  - GET /api/resources/search?q= - Search functionality
  - POST /api/resources - Create new resources
- **Validation**: Zod schemas for request/response validation
- **Error Handling**: Centralized error handling middleware

### Authentication & Authorization
- Session-based authentication planned (schema includes users table)
- Password hashing and user management infrastructure ready for implementation
- Currently using memory storage for development

### Development Environment
- **Hot Reload**: Vite HMR for instant frontend updates
- **Development Server**: Express with Vite middleware integration
- **TypeScript**: Strict type checking across the entire codebase
- **Path Aliases**: Configured for clean imports (@/, @shared/, @assets/)

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: Neon PostgreSQL serverless driver for cloud database connectivity
- **drizzle-orm & drizzle-kit**: Modern TypeScript ORM with migration support
- **@tanstack/react-query**: Server state management and caching
- **express**: Web application framework for Node.js
- **wouter**: Lightweight React router

### UI & Styling
- **@radix-ui/***: Comprehensive set of accessible UI primitives (accordion, dialog, dropdown, etc.)
- **tailwindcss**: Utility-first CSS framework
- **class-variance-authority**: For creating component variants
- **lucide-react**: Modern icon library
- **react-icons**: Additional icon sets (Discord, Reddit, YouTube)

### Development Tools
- **vite**: Build tool and development server
- **typescript**: Type checking and compilation
- **tsx**: TypeScript execution for development
- **esbuild**: Fast bundling for production builds

### Validation & Forms
- **zod**: Schema validation library
- **@hookform/resolvers**: React Hook Form integration with Zod
- **react-hook-form**: Form state management (infrastructure ready)

### Database & Storage
- **connect-pg-simple**: PostgreSQL session store for Express sessions
- **nanoid**: Unique ID generation for resources and sessions

The application is structured as a full-stack TypeScript application with clear separation between client, server, and shared code, making it maintainable and scalable for future development.
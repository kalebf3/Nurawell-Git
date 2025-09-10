# Overview

NuraWell is a mental health chatbot application built as a full-stack TypeScript application. It provides AI-powered mental health support through a conversational interface, allowing users to engage in therapeutic conversations and track their mood over time. The application features a modern, responsive UI with glassmorphic design elements and integrates with Replit's authentication system for user management.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture

The client is built using **React 18** with **TypeScript** and follows a component-based architecture:

- **State Management**: Uses React Query (@tanstack/react-query) for server state management and caching
- **Routing**: Implements wouter for lightweight client-side routing
- **UI Framework**: Built with Radix UI primitives and shadcn/ui components for accessibility and consistency
- **Styling**: Uses Tailwind CSS with custom CSS variables for theming and glassmorphic design effects
- **Build Tool**: Vite for fast development and optimized production builds

The frontend follows a clean separation of concerns with dedicated folders for components, hooks, pages, and utilities. The UI features a three-panel layout: sidebar for navigation, main chat interface, and right panel for mood tracking and crisis resources.

## Backend Architecture

The server is built with **Express.js** and follows a RESTful API design:

- **Framework**: Express.js with TypeScript for type safety
- **Session Management**: Uses express-session with PostgreSQL session storage
- **Authentication**: Integrates with Replit's OpenID Connect (OIDC) authentication system
- **API Design**: RESTful endpoints for conversations, messages, mood tracking, and user management
- **Error Handling**: Centralized error handling middleware with proper HTTP status codes

The backend implements a clean separation between routes, storage layer, and authentication middleware.

## Data Storage Solutions

**Database**: PostgreSQL with Drizzle ORM for type-safe database operations

- **Schema Design**: Relational schema with tables for users, conversations, messages, mood entries, and sessions
- **ORM**: Drizzle ORM provides type-safe queries and migrations
- **Connection**: Uses Neon serverless PostgreSQL with connection pooling
- **Migrations**: Database schema versioning through Drizzle Kit

The schema includes proper foreign key relationships and cascade deletions to maintain data integrity.

## Authentication and Authorization

**Authentication**: Replit OpenID Connect (OIDC) integration

- **Provider**: Uses Replit's OIDC service for user authentication
- **Session Management**: Server-side sessions stored in PostgreSQL
- **Authorization**: Route-level middleware protection for authenticated endpoints
- **User Management**: Automatic user creation/updates on authentication

The authentication system is designed specifically for Replit's ecosystem and handles user profile information automatically.

## AI Integration Architecture

The application includes infrastructure for AI-powered responses:

- **Chat API**: Dedicated endpoint for processing user messages and generating AI responses
- **Context Management**: Conversation history tracking for contextual responses
- **Response Generation**: Placeholder for AI model integration (likely LLM-based)
- **Error Handling**: Graceful fallbacks for AI service failures

The architecture supports future integration with various AI services for generating therapeutic responses.

# External Dependencies

## Database Services
- **Neon Database**: Serverless PostgreSQL hosting with WebSocket support for real-time connections
- **Drizzle ORM**: Type-safe database toolkit for schema management and queries

## Authentication Services
- **Replit Auth**: OpenID Connect provider for user authentication and profile management
- **Passport.js**: Authentication middleware with OpenID Connect strategy

## UI and Frontend Libraries
- **Radix UI**: Accessible, unstyled UI primitives for building the component system
- **Tailwind CSS**: Utility-first CSS framework for styling and responsive design
- **Lucide React**: Icon library for consistent iconography
- **React Hook Form**: Form validation and management with Zod schema validation

## Development and Build Tools
- **Vite**: Build tool and development server with React plugin
- **TypeScript**: Type checking and enhanced development experience
- **ESBuild**: Fast JavaScript bundler for production builds

## Potential AI Services
The application is structured to integrate with AI services for generating therapeutic responses, though the specific provider is not currently implemented. Common integrations would include:
- OpenAI GPT models
- Anthropic Claude
- Hugging Face transformers
- Custom therapeutic AI models

The attached assets suggest previous experimentation with Phi-3 models and RAG (Retrieval-Augmented Generation) systems for context-aware responses.
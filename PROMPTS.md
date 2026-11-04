# 🚀 Powerful AI Prompts for Every Framework

Use these prompts with GitHub Copilot, ChatGPT, Claude, or any AI coding assistant to rapidly scaffold and build projects across all platforms.

---

## Table of Contents

- [🌐 Web — Frontend Frameworks](#-web--frontend-frameworks)
  - [React](#react)
  - [Next.js](#nextjs)
  - [Vue.js](#vuejs)
  - [Angular](#angular)
  - [Svelte / SvelteKit](#svelte--sveltekit)
- [⚙️ Web — Backend Frameworks](#️-web--backend-frameworks)
  - [Node.js / Express](#nodejs--express)
  - [Django (Python)](#django-python)
  - [FastAPI (Python)](#fastapi-python)
  - [Spring Boot (Java)](#spring-boot-java)
  - [Laravel (PHP)](#laravel-php)
  - [Ruby on Rails](#ruby-on-rails)
- [📱 Mobile Applications](#-mobile-applications)
  - [React Native](#react-native)
  - [Flutter](#flutter)
  - [Swift (iOS)](#swift-ios)
  - [Kotlin (Android)](#kotlin-android)
- [🖥️ Desktop Software](#️-desktop-software)
  - [Electron](#electron)
  - [Tauri](#tauri)
  - [PyQt / Tkinter (Python)](#pyqt--tkinter-python)
- [🗄️ Databases & APIs](#️-databases--apis)
- [🔒 Authentication & Security](#-authentication--security)
- [☁️ DevOps & Deployment](#️-devops--deployment)
- [🧪 Testing](#-testing)
- [♿ Accessibility & Performance](#-accessibility--performance)

---

## 🌐 Web — Frontend Frameworks

### React

```
Create a production-ready React 18 app with:
- TypeScript
- Vite as the build tool
- React Router v6 for routing (Home, About, Dashboard, 404 pages)
- Zustand for global state management
- Axios for API calls with a centralized API client
- Tailwind CSS for styling
- ESLint + Prettier configuration
Show the full folder structure, main entry files, and a sample feature component with hooks.
```

```
Build a React component library with:
- Reusable Button, Input, Modal, Card, and Table components
- Storybook integration for documentation
- Unit tests using Vitest and React Testing Library
- TypeScript prop types and JSDoc comments
- Export all components from a single index.ts barrel file
```

```
Create a React dashboard app that:
- Fetches data from a REST API using React Query (TanStack Query)
- Displays charts using Recharts
- Has a responsive sidebar navigation
- Implements dark/light mode toggle using Context API
- Shows loading skeletons while data loads
- Handles error states gracefully
```

---

### Next.js

```
Scaffold a full-stack Next.js 14 (App Router) project with:
- TypeScript
- Tailwind CSS + shadcn/ui component library
- NextAuth.js for authentication (Google + GitHub providers)
- Prisma ORM with PostgreSQL
- tRPC for type-safe API routes
- Zod for input validation
- Vercel deployment configuration
Include the folder structure, middleware, and a sample authenticated page.
```

```
Create a Next.js e-commerce store with:
- Product listing page with filters and pagination
- Product detail page with image gallery
- Shopping cart using Zustand (persisted in localStorage)
- Checkout form with Stripe payment integration
- Order confirmation page
- Admin dashboard to manage products (CRUD)
- SEO optimization with next/head meta tags and Open Graph
```

```
Build a Next.js blog platform with:
- MDX support for blog posts stored in /content directory
- Dynamic routes for each blog post
- Table of contents sidebar auto-generated from headings
- Code syntax highlighting with Shiki
- RSS feed generation
- Sitemap and robots.txt
- Tag filtering and search functionality
```

---

### Vue.js

```
Create a Vue 3 app using the Composition API with:
- TypeScript and <script setup> syntax
- Vite build tool
- Vue Router 4 with lazy-loaded routes
- Pinia for state management
- Axios with request/response interceptors
- Tailwind CSS
- Vitest + Vue Test Utils for testing
Show the folder structure and a sample CRUD feature.
```

```
Build a Vue 3 admin panel that:
- Uses Element Plus or Vuetify 3 component library
- Has role-based access control (admin, editor, viewer)
- Includes a data table with sorting, filtering, and pagination
- Has form validation using VeeValidate + Zod
- Implements real-time notifications using WebSockets
- Exports table data as CSV or Excel
```

---

### Angular

```
Generate an Angular 17 standalone application with:
- Angular signals for reactive state
- Angular Router with lazy-loaded feature modules
- HttpClient with interceptors for auth tokens and error handling
- Reactive Forms with custom validators
- Angular Material component library
- NgRx (or NGXS) for complex state management
- Jest for unit testing
Show the project structure and a sample feature module.
```

```
Create an Angular enterprise app with:
- Micro-frontend architecture using Module Federation
- Shared component library as a separate Angular library
- OpenAPI-generated API service layer
- Role-based route guards
- Internationalization (i18n) support
- Performance optimization with OnPush change detection
```

---

### Svelte / SvelteKit

```
Build a SvelteKit app with:
- TypeScript
- Server-side rendering (SSR) and static generation (SSG)
- Drizzle ORM with SQLite for the database
- Authentication with Lucia Auth
- Tailwind CSS + DaisyUI
- Form actions with superforms + Zod validation
- Deployment to Cloudflare Pages
```

---

## ⚙️ Web — Backend Frameworks

### Node.js / Express

```
Create a production-ready Node.js REST API with:
- Express.js + TypeScript
- JWT authentication (access + refresh tokens)
- MongoDB with Mongoose ODM
- Input validation with Joi or Zod
- Rate limiting, CORS, and Helmet for security
- Winston for structured logging
- Jest for integration tests
- Swagger/OpenAPI documentation
- Docker + docker-compose setup
Show the full project structure and a sample CRUD resource (users).
```

```
Build a Node.js GraphQL API with:
- Apollo Server 4
- Prisma ORM with PostgreSQL
- DataLoader for N+1 query prevention
- JWT-based authentication middleware
- File upload support
- Subscription support via WebSockets
- Code-first schema generation with TypeGraphQL
```

---

### Django (Python)

```
Scaffold a Django 5 REST API project with:
- Django REST Framework (DRF)
- JWT authentication with djangorestframework-simplejwt
- PostgreSQL database
- Custom user model with email login
- Serializers, ViewSets, and Routers
- django-filter for filtering
- drf-spectacular for OpenAPI documentation
- Celery + Redis for async tasks
- Docker + docker-compose
- pytest-django for testing
Show the project layout and a sample API resource.
```

```
Create a Django full-stack web app (with templates) that:
- Uses Django ORM with migrations
- Has user authentication (login, register, password reset)
- Implements HTMX for dynamic UI without a full SPA
- Uses Alpine.js for lightweight interactivity
- Has a file upload feature with Pillow for image processing
- Deploys on Heroku or Railway with gunicorn + whitenoise
```

---

### FastAPI (Python)

```
Build a FastAPI application with:
- Async SQLAlchemy with PostgreSQL (asyncpg driver)
- Alembic for database migrations
- Pydantic v2 schemas
- OAuth2 with JWT bearer tokens
- Dependency injection for database sessions and auth
- Background tasks with FastAPI BackgroundTasks
- pytest + httpx for async testing
- OpenAPI docs auto-generated at /docs
- Docker deployment
```

```
Create a FastAPI microservice that:
- Consumes and produces messages via RabbitMQ (aio-pika)
- Caches responses in Redis with TTL
- Has health check and readiness endpoints
- Uses structlog for JSON logging
- Is containerized and deployed with Kubernetes
```

---

### Spring Boot (Java)

```
Generate a Spring Boot 3 REST API with:
- Java 21
- Spring Security with JWT authentication
- Spring Data JPA with PostgreSQL
- Flyway for database migrations
- Bean Validation (Jakarta)
- MapStruct for DTO mapping
- SpringDoc OpenAPI for Swagger UI
- Testcontainers for integration testing
- Maven or Gradle build configuration
- Docker Compose for local development
```

---

### Laravel (PHP)

```
Create a Laravel 11 API project with:
- Laravel Sanctum for API token authentication
- Eloquent ORM with PostgreSQL
- Form Request classes for validation
- API Resources for response transformation
- Repository pattern for data access
- Queue jobs with Redis
- Laravel Telescope for debugging
- PHPUnit + Pest for testing
- Laravel Sail for Docker development
```

---

### Ruby on Rails

```
Scaffold a Ruby on Rails 7 app with:
- Hotwire (Turbo + Stimulus) for reactive UI
- PostgreSQL database
- Devise for authentication
- Pundit for authorization
- Active Storage for file uploads (S3 backend)
- Sidekiq for background jobs
- RSpec for testing
- Deployment configuration for Render or Fly.io
```

---

## 📱 Mobile Applications

### React Native

```
Create a React Native app (Expo + TypeScript) with:
- Expo Router v3 for file-based navigation
- NativeWind (Tailwind CSS for React Native) for styling
- Zustand for state management
- React Query for server state and caching
- Expo SecureStore for token storage
- Push notifications with Expo Notifications
- Camera and image picker integration
- OTA updates with expo-updates
Show the folder structure and a sample authenticated screen flow.
```

```
Build a React Native e-commerce mobile app with:
- Product catalog with FlatList and search
- Product detail screen with image carousel
- Cart and wishlist functionality
- Stripe or RevenueCat in-app payments
- User profile with order history
- Offline support with MMKV storage
- Animations using React Native Reanimated 3
- Deep linking support
```

---

### Flutter

```
Build a Flutter app with:
- Dart null safety
- Riverpod 2 (or BLoC) for state management
- GoRouter for navigation
- Retrofit + Dio for API calls
- Hive or Isar for local database storage
- Flutter Secure Storage for sensitive data
- Firebase Auth for authentication
- Push notifications with Firebase Cloud Messaging
- Flavor configurations for dev/staging/production
Show the project architecture and a sample feature.
```

```
Create a Flutter social media app with:
- Real-time chat using Firebase Firestore
- Photo and video upload to Firebase Storage
- Stories feature with a timer progress bar
- Infinite scroll feed
- Like, comment, and share functionality
- User follow/unfollow system
- Search users and hashtags
- In-app notifications
```

---

### Swift (iOS)

```
Create a SwiftUI iOS app with:
- Swift Concurrency (async/await)
- MVVM architecture
- SwiftData (or Core Data) for local persistence
- URLSession with async/await for networking
- Keychain for secure token storage
- Sign in with Apple
- Push notifications (APNs)
- Widget extension
Show the project structure and a sample feature screen.
```

---

### Kotlin (Android)

```
Build a Kotlin Android app with:
- Jetpack Compose UI
- MVVM + Clean Architecture
- Hilt for dependency injection
- Retrofit + OkHttp for networking
- Room database for local persistence
- DataStore for preferences
- Coroutines + Flow for async operations
- Material 3 design system
- Navigation Compose
- Unit and UI tests with JUnit5 and Espresso
```

---

## 🖥️ Desktop Software

### Electron

```
Create an Electron app with:
- TypeScript + React (Vite renderer)
- IPC communication patterns (main ↔ renderer)
- Context isolation and preload scripts (secure)
- SQLite database via better-sqlite3
- Auto-updater with electron-updater
- System tray integration
- Native file dialogs and OS notifications
- Code signing and packaging with electron-builder
- macOS, Windows, and Linux targets
```

---

### Tauri

```
Build a Tauri v2 desktop app with:
- React + TypeScript frontend
- Rust backend commands
- SQLite with sqlx (Rust)
- File system access via Tauri plugins
- System tray and native menus
- Auto-updater
- Cross-platform build (macOS, Windows, Linux)
Explain the Tauri command/event communication pattern.
```

---

### PyQt / Tkinter (Python)

```
Create a PyQt6 desktop application with:
- Main window with menu bar, toolbar, and status bar
- Multi-tab interface using QTabWidget
- SQLite database with SQLAlchemy ORM
- Worker threads using QThread (non-blocking UI)
- Settings dialog with QSettings persistence
- File open/save dialogs
- Custom Qt stylesheet (dark theme)
- PyInstaller packaging for distribution
```

---

## 🗄️ Databases & APIs

```
Design a PostgreSQL database schema for a [SaaS / e-commerce / social network] app with:
- Normalized tables with proper foreign keys and indexes
- Soft delete (deleted_at timestamp)
- Audit log table (created_by, updated_at)
- Row-level security policies
- Sample seed data
Generate the SQL DDL statements and an ER diagram description.
```

```
Create a RESTful API design document for [feature] following best practices:
- Resource naming conventions
- HTTP methods and status codes
- Pagination (cursor-based)
- Filtering and sorting query parameters
- Error response format (RFC 7807 Problem Details)
- Versioning strategy
- Rate limiting headers
```

```
Build a GraphQL schema for [domain] with:
- Queries, mutations, and subscriptions
- Input types and enums
- Pagination with Relay-style cursor connections
- Custom scalar types (Date, JSON, Upload)
- Error handling with union types
- DataLoader batching strategy
```

---

## 🔒 Authentication & Security

```
Implement a complete authentication system with:
- Email/password registration with email verification
- JWT access tokens (15 min) + refresh tokens (7 days, HTTP-only cookie)
- OAuth2 social login (Google, GitHub, Facebook)
- Two-factor authentication (TOTP with QR code)
- Password reset via email
- Account lockout after failed attempts
- Session management (list and revoke active sessions)
Choose framework: [Node.js / Django / FastAPI / Spring Boot]
```

```
Add security hardening to an existing web application:
- Content Security Policy (CSP) headers
- CSRF protection
- SQL injection prevention (parameterized queries)
- XSS prevention (input sanitization, output encoding)
- Rate limiting per IP and per user
- HTTPS enforcement with HSTS
- Dependency vulnerability scanning
- Secret management with environment variables (not hardcoded)
```

---

## ☁️ DevOps & Deployment

```
Create a complete CI/CD pipeline with GitHub Actions for a [Node.js / Python / Java] app:
- Lint and type-check on every push
- Run unit and integration tests with coverage report
- Build Docker image and push to GitHub Container Registry
- Deploy to staging on PR merge to main
- Deploy to production on release tag
- Notify Slack on deployment success/failure
- Cache dependencies and Docker layers for speed
```

```
Write a production-ready Docker setup for [framework] with:
- Multi-stage Dockerfile (builder + production image)
- Non-root user for security
- Health check instruction
- docker-compose.yml with app + database + Redis
- Environment variable management with .env.example
- Volume mounts for development hot-reload
```

```
Set up Kubernetes deployment manifests for a web app with:
- Deployment with rolling update strategy
- HorizontalPodAutoscaler (min 2, max 10 replicas)
- Service and Ingress with TLS (cert-manager)
- ConfigMap and Secrets
- PersistentVolumeClaim for uploads
- Liveness and readiness probes
- Resource requests and limits
- Network policies
```

---

## 🧪 Testing

```
Write a comprehensive test suite for [feature/component] using [Jest/Pytest/JUnit]:
- Unit tests for all business logic functions
- Integration tests for API endpoints (happy path + error cases)
- Edge cases: empty inputs, null values, boundary conditions
- Mock external dependencies (database, third-party APIs)
- Test coverage target: 80%+
- Test naming convention: describe/it blocks or Arrange-Act-Assert
```

```
Create end-to-end tests using Playwright for [user journey]:
- User registration and login flow
- [Core feature] walkthrough
- Form submission with validation errors
- Responsive layout on mobile viewport
- Screenshot comparison tests
- CI integration with artifact uploads on failure
```

---

## ♿ Accessibility & Performance

```
Audit and fix accessibility issues in [component/page]:
- Semantic HTML (landmarks, headings hierarchy)
- ARIA labels and roles
- Keyboard navigation and focus management
- Color contrast ratios (WCAG AA)
- Screen reader announcements for dynamic content
- Focus trap in modals
- Skip navigation links
```

```
Optimize the performance of [React/Vue/Angular] app:
- Code splitting and lazy loading routes
- Image optimization (WebP, srcset, lazy loading)
- Bundle analysis and tree shaking
- Memoization (useMemo, useCallback, computed)
- Virtual scrolling for long lists
- Service Worker for offline support and caching
- Core Web Vitals improvements (LCP, FID, CLS)
```

---

> 💡 **Tip:** Combine prompts! For example: *"Build a Next.js 14 e-commerce app with FastAPI backend, JWT auth, PostgreSQL, Stripe payments, and deploy with Docker + GitHub Actions."*

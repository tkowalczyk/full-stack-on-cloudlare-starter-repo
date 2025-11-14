# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2025-11-13

### Added

#### Link Management
- Short link creation with unique IDs (nanoid)
- Link name editing and configuration
- Paginated list of all user links
- Link copying functionality

#### Geo-based Routing
- Geographic routing with different destination URLs for different countries
- Default URL fallback for countries without specific configuration
- Automatic user location detection (country, latitude/longitude) via Cloudflare headers
- Intelligent redirection based on user's country
- KV caching for fast link configuration access (24h TTL)

#### Click Tracking & Analytics
- Click tracking with comprehensive metadata:
  - Timestamp
  - Country of origin
  - Geographic coordinates (latitude/longitude)
  - Destination URL
- Real-time statistics:
  - Clicks in the last hour
  - Clicks in the last 24 hours (with comparison to previous day)
  - Clicks in the last 30 days
  - Top countries by clicks
- WebSocket support for live click updates (Durable Object `LINK_CLICK_TRACKER`)
- Geographic visualizations:
  - Active regions map
  - Active areas map
  - Top countries table
  - Top cities table

#### AI-Powered Destination Evaluation
- Automatic destination URL availability verification via Cloudflare Workflows
- AI-powered status checking for page availability and product status
- Page data collection:
  - HTML rendering via Puppeteer/Playwright
  - Body text extraction
  - Page screenshots
- R2 Storage backup:
  - HTML page backup
  - Body text backup
  - Screenshot backup (PNG)
- Problematic link reporting with list of unavailable destinations
- Evaluation history with pagination support

#### Dashboard & User Interface
- Main dashboard with:
  - Metric cards (last hour, 24h, 30 days)
  - Geographic maps
  - Active links tables
  - Problematic destinations list
- Link detail page with:
  - Name editing
  - Default URL configuration
  - Geographic routing toggle
  - Country-specific destination management
- Links list page with copy functionality
- Evaluations page with verification history

#### Subscription System
- Stripe integration via Cloudflare Auth
- Subscription plans:
  - Basic (€5/month) - up to 100 links, basic analytics
  - Pro (€15/month) - unlimited links, advanced analytics, API access
  - Enterprise (€49/month) - everything in Pro + dedicated support, SSO
- Subscription management - upgrade, downgrade, cancellation
- Subscription status sidebar

#### Authentication
- Cloudflare Auth integration
- User authentication and session management
- Login popup component
- User icon component

#### Technical Infrastructure
- Full-stack architecture:
  - Frontend: React + TanStack Router + TanStack Query + tRPC (TypeScript)
  - Backend: Cloudflare Workers with Hono framework
  - Database: SQLite (D1) via Drizzle ORM
- Background processing:
  - Queue processing for asynchronous click handling
  - Workflow orchestration for destination evaluation coordination
- Durable Objects:
  - `LINK_CLICK_TRACKER` - real-time geographic click aggregation
  - `EVALUATION_SCHEDULAR` - destination evaluation scheduling
- Cloudflare services integration:
  - Workers
  - Durable Objects
  - Queues
  - R2 Storage
  - KV Cache

#### UI Components
- Modern React components with shadcn/ui
- Responsive design with mobile support
- Theme provider with dark/light mode support
- App sidebar navigation
- Site header
- Mode toggle component
- Various UI components (cards, badges, dialogs, dropdowns, tables, etc.)

[Unreleased]: https://github.com/yourusername/full-stack-on-cloudlare-starter-repo/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/yourusername/full-stack-on-cloudlare-starter-repo/releases/tag/v1.0.0


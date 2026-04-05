# Project Requirements

The following features must be implemented with detailed technical specifications, API endpoints, and implementation guidelines:

## 1. Complete MERN Stack Backend

### Database Layer
- **MongoDB Schemas**:
  - Users: {_id, email, password, role, profile, createdAt, updatedAt}
  - Products: {_id, name, description, price, category, images, stock, createdAt, updatedAt}
  - Messages: {_id, userId, adminId, content, timestamp, read, type}
  - Analytics: {_id, page, visitors, timestamp, userAgent, ip}
- **Indexing Strategy**: Compound indexes on frequently queried fields
- **Data Validation**: Mongoose schema validation with custom validators

### API Layer
- **RESTful Endpoints**:
  - `GET /api/products` - List products with pagination
  - `POST /api/products` - Create product (admin only)
  - `PUT /api/products/:id` - Update product (admin only)
  - `DELETE /api/products/:id` - Delete product (admin only)
  - `GET /api/users` - List users (admin only)
  - `POST /api/auth/login` - User authentication
  - `POST /api/auth/register` - User registration
- **Response Format**: JSON with consistent error handling
- **Rate Limiting**: 100 requests per minute per IP

### Authentication
- **JWT Tokens**: 24-hour expiration with refresh token mechanism
- **Password Security**: bcrypt hashing with salt rounds
- **Role-based Access**: Admin/User roles with middleware protection
- **Session Management**: Secure HTTP-only cookies

### Middleware
- **CORS**: Configured for frontend domain
- **Validation**: Joi schema validation for all inputs
- **Error Handling**: Centralized error middleware with logging
- **Logging**: Winston logger with different log levels

### Security
- **Input Sanitization**: Express-validator for all user inputs
- **XSS Protection**: Helmet.js security headers
- **Data Encryption**: AES-256 encryption for sensitive data
- **API Security**: API key authentication for external services

## 2. User and Admin Dashboard

### User Dashboard
- **Profile Management**: Update personal information, change password
- **Order History**: View past interactions, download receipts
- **Preferences**: Notification settings, language selection
- **Contact Forms**: Submit inquiries with file attachments

### Admin Dashboard
- **Overview Stats**: Key metrics cards, recent activities
- **User Management**: View/edit/delete users, role assignment
- **Content Management**: Product CRUD, category management
- **Analytics View**: Traffic stats, user engagement metrics

### Responsive Design
- **Mobile-First**: CSS Grid and Flexbox layouts
- **UI Framework**: Material-UI or Ant Design components
- **Theme System**: Light/dark mode support
- **Accessibility**: WCAG 2.1 AA compliance

### Navigation
- **Role-based Routing**: Protected routes with redirects
- **Breadcrumb Navigation**: Clear page hierarchy
- **Search Functionality**: Global search across dashboard
- **Quick Actions**: Floating action buttons for common tasks

## 3. Stats on Admin Dashboard

### Key Metrics
- **User Metrics**: Total users, active users, new registrations
- **Product Metrics**: Total products, views, conversions
- **Traffic Metrics**: Page views, unique visitors, bounce rate
- **Revenue Metrics**: Sales volume, average order value

### Visualizations
- **Chart Libraries**: Chart.js with custom themes
- **Dashboard Widgets**: Draggable, resizable components
- **Time Ranges**: Daily, weekly, monthly, yearly views
- **Export Options**: PNG, PDF, CSV formats

### Real-time Updates
- **WebSocket Integration**: Live data streaming
- **Auto-refresh**: Configurable update intervals
- **Push Notifications**: Real-time alerts for important changes
- **Caching**: Redis for performance optimization

### Export Functionality
- **Data Export**: CSV/Excel with custom date ranges
- **Report Generation**: PDF reports with charts
- **Scheduled Reports**: Automated email delivery
- **API Access**: REST endpoints for external integrations

## 4. Product CRUD Operations on Admin Side with Two-way Communication

### Create Operations
- **Product Form**: Multi-step form with validation
- **Image Upload**: Cloud storage integration (AWS S3)
- **Category Selection**: Dynamic category tree
- **Pricing Structure**: Base price, discounts, variants

### Read Operations
- **Product Grid**: Sortable, filterable data table
- **Search Functionality**: Full-text search with highlighting
- **Pagination**: Server-side pagination with page size options
- **Bulk Selection**: Multi-select for bulk operations

### Update Operations
- **Version Control**: Track changes with audit logs
- **Approval Workflow**: Draft → Review → Published states
- **Bulk Updates**: Mass edit capabilities
- **Change Notifications**: Alert users of product updates

### Delete Operations
- **Soft Delete**: Mark as deleted, retain in database
- **Confirmation Dialogs**: Prevent accidental deletions
- **Audit Trail**: Log all delete operations
- **Recovery Options**: Restore deleted products

### Two-way Communication
- **Real-time Sync**: WebSocket updates to user interfaces
- **Cache Invalidation**: Automatic cache clearing on changes
- **Push Notifications**: Notify users of product updates
- **API Webhooks**: Trigger external system updates

## 5. Newsletter

### Subscription Management
- **Email Collection**: GDPR-compliant opt-in forms
- **Double Opt-in**: Confirmation email verification
- **Unsubscribe**: One-click unsubscribe with confirmation
- **List Management**: Multiple subscriber lists and segments

### Template System
- **Drag-and-Drop Editor**: Visual email builder
- **Template Library**: Pre-built responsive templates
- **Dynamic Content**: Personalized content blocks
- **A/B Testing**: Test subject lines and content

### Scheduling
- **Campaign Scheduler**: Date/time based sending
- **Automated Triggers**: Welcome series, re-engagement campaigns
- **Time Zone Support**: Send at optimal local times
- **Queue Management**: Handle large subscriber lists

### Analytics
- **Open Tracking**: Pixel-based open rate measurement
- **Click Tracking**: Link click analysis and heatmaps
- **Conversion Tracking**: Goal completion monitoring
- **Subscriber Growth**: Acquisition and churn metrics

## 6. Push Notifications

### Browser Notifications
- **Web Push API**: Service worker integration
- **Permission Management**: Request and handle permissions
- **Notification Queue**: Queue notifications for offline users
- **Custom Icons**: Branded notification icons

### Mobile Support
- **PWA Features**: Installable web app
- **Mobile Notifications**: Native-like push notifications
- **Offline Support**: Background sync capabilities
- **App Badges**: Notification count indicators

### Customizable Messages
- **Message Templates**: Pre-defined notification types
- **Dynamic Content**: Personalized notification content
- **Scheduling**: Time-based notification delivery
- **Priority Levels**: Urgent vs. informational notifications

### User Preferences
- **Notification Types**: Product updates, promotions, system alerts
- **Frequency Settings**: Immediate, daily digest, weekly summary
- **Channel Preferences**: Email, push, SMS options
- **Opt-out Options**: Granular control over notifications

## 7. Advanced Search Filter

### Multi-field Search
- **Search Fields**: Name, description, SKU, tags
- **Fuzzy Matching**: Typo-tolerant search
- **Relevance Scoring**: Rank results by relevance
- **Search Suggestions**: Auto-complete and corrections

### Filter Options
- **Price Range**: Min/max price sliders
- **Category Filters**: Hierarchical category selection
- **Availability**: In stock, out of stock, pre-order
- **Rating Filters**: Star rating filters

### Sorting
- **Sort Criteria**: Price, popularity, newest, rating
- **Multi-level Sorting**: Primary and secondary sort options
- **Custom Sorting**: User-defined sort preferences
- **Persistent Sorting**: Remember user sort preferences

### Saved Searches
- **Search History**: Recent searches with quick access
- **Saved Filters**: Named filter sets for reuse
- **Shareable Links**: URL-encoded search parameters
- **Alert System**: Notify users of new matching products

## 8. Hardcoded Products Converted into MongoDB

### Data Migration
- **Migration Script**: Node.js script for data transfer
- **Data Mapping**: Transform existing data structure
- **Validation**: Ensure data integrity during migration
- **Rollback Plan**: Ability to revert migration if needed

### Dynamic Loading
- **Lazy Loading**: Load products on demand
- **Caching Layer**: Redis cache for frequently accessed data
- **Pagination**: Efficient loading of large datasets
- **Search Optimization**: Indexed fields for fast queries

### Admin Management
- **Bulk Import**: CSV/Excel import functionality
- **Bulk Export**: Export product data for backup
- **Duplicate Detection**: Prevent duplicate product entries
- **Category Management**: Dynamic category creation and editing

### Version Control
- **Change Tracking**: Audit log of all product changes
- **Revision History**: View previous versions of products
- **Approval Workflow**: Review changes before publishing
- **Backup System**: Automated database backups

## 9. Webpage Traffic Stats on Admin Side

### Analytics Integration
- **Google Analytics**: GA4 integration with custom events
- **Custom Tracking**: Server-side event tracking
- **User Identification**: Anonymous user tracking
- **Privacy Compliance**: Cookie consent and data minimization

### Real-time Monitoring
- **Live Dashboard**: Real-time visitor counts
- **Active Sessions**: Current user activity monitoring
- **Page Views**: Real-time page view tracking
- **Conversion Tracking**: Goal completion monitoring

### Historical Data
- **Trend Analysis**: Time-series data visualization
- **Comparison Periods**: Year-over-year, month-over-month
- **Growth Metrics**: User acquisition and retention rates
- **Seasonal Analysis**: Identify peak usage periods

### Geographic Data
- **Location Tracking**: Country, city, region data
- **Device Types**: Desktop, mobile, tablet breakdown
- **Browser Stats**: Browser and version usage
- **Referral Sources**: Traffic source analysis

## 10. Chatbot

### AI Integration
- **API Integration**: OpenAI GPT or Dialogflow connection
- **Context Management**: Maintain conversation context
- **Intent Recognition**: Understand user intent and entities
- **Response Generation**: Generate contextual responses

### Conversational Flows
- **Predefined Flows**: FAQ, product recommendations, support
- **Dynamic Responses**: Context-aware answer generation
- **Fallback Handling**: Graceful handling of unknown queries
- **Multi-language Support**: Support for multiple languages

### Learning Capability
- **Feedback Collection**: User satisfaction ratings
- **Model Training**: Continuous learning from interactions
- **Performance Monitoring**: Track response accuracy
- **Human Handoff**: Escalate complex queries to human support

### Admin Oversight
- **Conversation Monitoring**: View all chatbot interactions
- **Intervention Tools**: Take over conversations manually
- **Analytics Dashboard**: Chatbot performance metrics
- **Training Data**: Review and improve training datasets

## 11. Live User Contact Messages on Admin Side and Replies

### Contact Form Integration
- **Form Validation**: Client and server-side validation
- **File Attachments**: Support for image/document uploads
- **Spam Protection**: reCAPTCHA integration
- **Auto-responses**: Immediate acknowledgment emails

### Admin Interface
- **Message Queue**: Inbox-style message management
- **Read/Unread Status**: Visual indicators for new messages
- **Priority Levels**: Urgent, normal, low priority messages
- **Search/Filter**: Find messages by user, date, content

### Reply System
- **Rich Text Editor**: Formatted response composition
- **Template Library**: Pre-written response templates
- **Attachment Support**: Send files and documents
- **Response Tracking**: Log all admin responses

### Notification System
- **Real-time Alerts**: Browser notifications for new messages
- **Email Notifications**: Daily/weekly message digests
- **Mobile Alerts**: Push notifications for urgent messages
- **Escalation Rules**: Automatic priority assignment

### Message History
- **Conversation Threads**: Complete message history
- **Timestamp Tracking**: Exact timing of all messages
- **User Context**: Link to user profile and history
- **Export Options**: Export conversation histories

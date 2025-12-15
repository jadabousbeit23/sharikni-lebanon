# Requirements Specification Document
## Sharikni (شاركني) - Community Resource Sharing Platform

**Document Version:** 1.0  
**Date:** December 2024  
**Author:** Jad Abou Sbeit 
**Status:** Draft

---

## 1. Introduction

### 1.1 Purpose
This document specifies the functional and non-functional requirements for the Sharikni platform. It serves as the primary reference for development, testing, and project evaluation.

### 1.2 Scope
Sharikni is a web-based platform for community resource sharing in Lebanon, built using the MERN stack, enabling users to give away and request items within their local communities.

### 1.3 Intended Audience
- Project developer
- Academic supervisor
- University evaluators
- Future maintainers/developers
- Test users

### 1.4 Document Conventions
- **Must/Shall**: Mandatory requirement
- **Should**: Highly desirable requirement
- **May/Could**: Optional requirement
- **Priority Levels**: P0 (Critical), P1 (High), P2 (Medium), P3 (Low)

---

## 2. Overall Description

### 2.1 Product Perspective
Sharikni is a standalone web application designed specifically for Lebanese communities. It addresses the gap in organized, trustworthy platforms for local resource sharing during economic challenges.

### 2.2 Product Functions
- User registration and authentication
- Item posting and management
- Item discovery and search
- Request system for items
- Direct user communication
- Real-time notifications
- User profiles and reputation

### 2.3 User Classes

**1. Guest Users (Visitors)**
- Can view homepage
- Can browse available items (limited)
- Cannot post items or make requests
- Can register for an account

**2. Registered Users (Donors/Recipients)**
- All guest capabilities plus:
- Can post items to give away
- Can request items from others
- Can message other users
- Can manage their profile
- Can rate and review transactions

**3. Verified Users**
- All registered user capabilities plus:
- Verified badge on profile
- Higher trust level in community

### 2.4 Operating Environment
- **Client-side**: Modern web browsers (Chrome, Firefox, Safari, Edge)
- **Server-side**: Node.js runtime environment
- **Database**: MongoDB
- **Deployment**: Web servers capable of running Node.js applications
- **Devices**: Desktop computers, tablets, smartphones

### 2.5 Design and Implementation Constraints
- Must be built with MERN stack only
- Must work on devices with screen sizes from 320px to 1920px width
- Must be completed within 12 weeks
- Development by single developer
- No budget for paid services
- Must follow university project guidelines

### 2.6 Assumptions and Dependencies
**Assumptions:**
- Users have internet access
- Users have valid email addresses
- Users will provide accurate location information
- Modern browsers support JavaScript and cookies

**Dependencies:**
- MongoDB database availability
- Internet connectivity
- Third-party libraries (React, Express, Mongoose, etc.)
- Image hosting capability

---

## 3. Functional Requirements

### 3.1 User Management

#### FR-UM-001: User Registration [P0 - Critical]
**Description**: Users must be able to create a new account.

**Requirements:**
- System shall provide registration form with fields:
  - Full name (required, 2-50 characters)
  - Email address (required, valid format, unique)
  - Password (required, minimum 8 characters)
  - Phone number (required, Lebanese format for now and maybe changed to a global scope)
  - Location/Area (required, dropdown selection)
  - Bio (optional, max 200 characters)
- System shall validate all input fields
- System shall hash passwords before storage
- System shall send confirmation upon successful registration
- System shall prevent duplicate email addresses
- System shall display appropriate error messages

**Acceptance Criteria:**
- User can successfully register with valid information
- Duplicate emails are rejected
- Weak passwords are rejected
- User is automatically logged in after registration

---

#### FR-UM-002: User Login [P0 - Critical]
**Description**: Registered users must be able to log into their accounts.

**Requirements:**
- System shall provide login form with email and password
- System shall authenticate credentials against database
- System shall generate JWT token upon successful login
- System shall store token securely (localStorage)
- System shall redirect to dashboard after login
- System shall display error for invalid credentials
- System shall implement rate limiting (max 5 attempts per 15 minutes)

**Acceptance Criteria:**
- User can login with correct credentials
- User cannot login with incorrect credentials
- Session persists across page refreshes
- User stays logged in until explicit logout or token expiration

---

#### FR-UM-003: User Logout [P0 - Critical]
**Description**: Logged-in users must be able to log out.

**Requirements:**
- System shall provide logout button/link
- System shall clear authentication token
- System shall redirect to homepage after logout
- System shall terminate session completely

**Acceptance Criteria:**
- User can successfully logout
- User cannot access protected pages after logout
- Token is completely removed

---

#### FR-UM-004: View/Edit Profile [P1 - High]
**Description**: Users must be able to view and edit their profile information.

**Requirements:**
- System shall display user profile with:
  - Name, email, phone, location, bio
  - Profile picture/avatar
  - Member since date
  - Rating/reviews
  - Statistics (items posted, items given, requests made)
- System shall allow editing of:
  - Name, phone, location, bio, profile picture
- System shall not allow editing email (security)
- System shall validate all changes
- System shall require password confirmation for sensitive changes

**Acceptance Criteria:**
- User can view their complete profile
- User can update editable fields
- Changes are saved and reflected immediately
- Invalid inputs are rejected

---

#### FR-UM-005: Password Management [P2 - Medium]
**Description**: Users should be able to change their password.

**Requirements:**
- System shall provide password change form
- System shall require current password
- System shall validate new password strength
- System shall update password after verification
- System shall log out all sessions after password change

**Acceptance Criteria:**
- User can change password with correct current password
- Strong password requirements enforced
- User cannot change password with wrong current password

---

### 3.2 Item Management

#### FR-IM-001: Post New Item [P0 - Critical]
**Description**: Registered users must be able to post items to give away.

**Requirements:**
- System shall provide item posting form with fields:
  - Title (required, 5-100 characters)
  - Description (required, 10-500 characters)
  - Category (required, dropdown: Furniture, Electronics, Clothes, Books, Food, Skills, Other)
  - Location (required, dropdown: Lebanese cities/areas)
  - Condition (required, radio: New, Like New, Good, Fair)
  - Image (optional, upload, max 5MB, JPG/PNG)
- System shall validate all inputs
- System shall generate unique item ID
- System shall associate item with user
- System shall set status to "available"
- System shall timestamp creation

**Acceptance Criteria:**
- User can successfully post item with valid data
- Item appears in browse page immediately
- Item appears in user's dashboard
- Image is properly uploaded and displayed
- Invalid inputs are rejected with clear messages

---

#### FR-IM-002: Browse Items [P0 - Critical]
**Description**: All users must be able to browse available items.

**Requirements:**
- System shall display items in card/grid format
- Each card shall show:
  - Image (or placeholder)
  - Title
  - Category badge
  - Location badge
  - Condition
  - Posted date (relative: "2 days ago")
  - Donor name/avatar
  - "Request Item" button
- System shall show only items with status "available"
- System shall support pagination/infinite scroll
- System shall show "no items" message when empty
- System shall load quickly (under 3 seconds)

**Acceptance Criteria:**
- Items display correctly in grid
- All item information is visible
- Clicking item opens detail view
- Page loads performantly

---

#### FR-IM-003: Search Items [P1 - High]
**Description**: Users should be able to search for specific items.

**Requirements:**
- System shall provide search bar on browse page
- System shall search in title and description
- System shall be case-insensitive
- System shall show results in real-time or on submit
- System shall highlight search terms (optional)
- System shall show "no results" message appropriately

**Acceptance Criteria:**
- Search returns relevant results
- Search works with partial words
- Results update appropriately
- Empty search shows all items

---

#### FR-IM-004: Filter Items [P1 - High]
**Description**: Users should be able to filter items by category and location.

**Requirements:**
- System shall provide filter sidebar/panel with:
  - Category checkboxes (all categories)
  - Location checkboxes (all locations)
  - Condition checkboxes
- System shall apply filters cumulatively (AND logic)
- System shall update results in real-time
- System shall show count of filtered results
- System shall allow clearing all filters

**Acceptance Criteria:**
- Filters work correctly individually
- Multiple filters work together
- Results update without page reload
- Clear filters returns to all items

---

#### FR-IM-005: View Item Details [P0 - Critical]
**Description**: Users must be able to view complete item information.

**Requirements:**
- System shall display item detail page with:
  - Large image (or gallery if multiple)
  - Complete title and description
  - Category, location, condition
  - Posted date
  - Donor information (name, avatar, rating, member since)
  - Status (available/claimed/completed)
  - "Request Item" button (if available and not own item)
  - "Contact Donor" button
  - Similar items section (optional)
- System shall show item history/status
- System shall update status in real-time

**Acceptance Criteria:**
- All item information displays correctly
- Donor profile link works
- Request button functions (see FR-RQ-001)
- Own items show edit/delete options

---

#### FR-IM-006: Edit Item [P1 - High]
**Description**: Users should be able to edit their posted items.

**Requirements:**
- System shall allow item owner to edit:
  - Title, description, category, condition
  - Image (replace)
- System shall not allow editing location after posting
- System shall validate changes
- System shall timestamp update
- System shall preserve item ID and creation date

**Acceptance Criteria:**
- Owner can access edit form
- Changes save successfully
- Non-owners cannot edit
- Updates reflect immediately

---

#### FR-IM-007: Delete Item [P1 - High]
**Description**: Users should be able to delete their posted items.

**Requirements:**
- System shall allow item owner to delete item
- System shall require confirmation before deletion
- System shall remove item from database
- System shall notify users who requested the item
- System shall preserve item history in user stats (count only)

**Acceptance Criteria:**
- Owner can delete their items
- Confirmation dialog appears
- Item disappears from all listings
- Non-owners cannot delete

---

#### FR-IM-008: Mark Item as Claimed/Completed [P2 - Medium]
**Description**: Donors should be able to update item status.

**Requirements:**
- System shall allow owner to mark item as:
  - Claimed (someone is picking it up)
  - Completed (successfully given away)
- System shall update item status
- System shall hide completed items from browse page
- System shall keep items in owner's history

**Acceptance Criteria:**
- Owner can change item status
- Status change reflects immediately
- Completed items don't appear in browse

---

### 3.3 Request Management

#### FR-RQ-001: Request Item [P0 - Critical]
**Description**: Registered users must be able to request items.

**Requirements:**
- System shall allow users to request available items
- System shall provide request form with:
  - Message to donor (required, 10-300 characters)
  - Contact preference (optional)
- System shall prevent requesting own items
- System shall prevent duplicate requests
- System shall create request record
- System shall notify donor in real-time
- System shall set request status to "pending"

**Acceptance Criteria:**
- User can submit request with message
- Donor receives notification
- Request appears in both user's dashboards
- Cannot request same item twice

---

#### FR-RQ-002: View Requests [P0 - Critical]
**Description**: Users must be able to view their sent and received requests.

**Requirements:**
- System shall display two request lists:
  - Requests I've Made (sent requests)
  - Requests I've Received (for my items)
- Each request shall show:
  - Item information
  - Other user information
  - Message
  - Status (pending, accepted, rejected, completed)
  - Date submitted
  - Action buttons
- System shall update in real-time

**Acceptance Criteria:**
- Sent requests display correctly
- Received requests display correctly
- Status is always current
- Actions work appropriately

---

#### FR-RQ-003: Respond to Request [P0 - Critical]
**Description**: Donors must be able to accept or reject requests.

**Requirements:**
- System shall allow donor to:
  - Accept request (reveals contact info)
  - Reject request (with optional reason)
- System shall update request status
- System shall notify requester
- System shall mark item as claimed when request accepted
- System shall allow messaging after acceptance

**Acceptance Criteria:**
- Donor can accept/reject requests
- Requester receives notification
- Contact info shared upon acceptance
- Item status updates appropriately

---

#### FR-RQ-004: Cancel Request [P2 - Medium]
**Description**: Requesters should be able to cancel their requests.

**Requirements:**
- System shall allow requester to cancel pending requests
- System shall update request status to "cancelled"
- System shall notify donor
- System shall remove request from active lists

**Acceptance Criteria:**
- Requester can cancel their requests
- Cancellation updates status
- Donor is notified

---

### 3.4 Communication

#### FR-CM-001: Direct Messaging [P1 - High]
**Description**: Users should be able to message each other.

**Requirements:**
- System shall provide messaging interface
- System shall support text messages only (no files initially)
- System shall show message history
- System shall indicate message read/unread status
- System shall support real-time message delivery
- System shall timestamp all messages
- System shall allow messaging only between:
  - Donor and requester (after request)
  - Item owner and interested parties

**Acceptance Criteria:**
- Users can send/receive messages
- Messages appear in real-time
- Message history persists
- Only authorized users can message

---

#### FR-CM-002: Notifications [P0 - Critical]
**Description**: Users must receive notifications for important events.

**Requirements:**
- System shall send real-time notifications for:
  - New request on your item
  - Request status change (accepted/rejected)
  - New message received
  - Item you requested was updated/deleted
- System shall display notification badge/count
- System shall provide notification center/list
- System shall mark notifications as read/unread
- System shall persist notifications until dismissed
- System shall play sound/alert (optional, user preference)

**Acceptance Criteria:**
- Notifications appear instantly
- Badge count is accurate
- Users can view notification history
- Notifications can be dismissed

---

### 3.5 Dashboard & Profile

#### FR-DP-001: User Dashboard [P1 - High]
**Description**: Users should have a personal dashboard.

**Requirements:**
- System shall display dashboard with:
  - Quick stats (items posted, items given, requests made)
  - Active items (currently available)
  - Pending requests (sent and received)
  - Recent activity feed
  - Quick actions (post item, browse items)
- System shall update stats in real-time
- System shall provide easy navigation

**Acceptance Criteria:**
- Dashboard loads quickly
- All stats are accurate
- Links/actions work correctly
- Updates reflect immediately

---

#### FR-DP-002: Rating & Reviews [P2 - Medium]
**Description**: Users should be able to rate each other after transactions.

**Requirements:**
- System shall allow users to:
  - Rate user (1-5 stars)
  - Write review (optional, max 200 characters)
- System shall allow rating only after completed transaction
- System shall calculate average rating
- System shall display rating on profile
- System shall show review history
- System shall allow one rating per transaction

**Acceptance Criteria:**
- Users can rate after transaction
- Average rating calculates correctly
- Reviews display on profile
- Cannot rate same transaction twice

---

## 4. Non-Functional Requirements

### 4.1 Performance Requirements

#### NFR-PF-001: Response Time [P0 - Critical]
- System shall load pages in under 3 seconds
- System shall respond to user actions in under 1 second
- API requests shall complete in under 2 seconds

#### NFR-PF-002: Concurrent Users [P2 - Medium]
- System should support at least 50 concurrent users
- System should handle 100 requests per minute

#### NFR-PF-003: Database Performance [P1 - High]
- Database queries shall execute in under 500ms
- System shall use indexes for frequent queries

---

### 4.2 Security Requirements

#### NFR-SC-001: Authentication [P0 - Critical]
- System shall use JWT for authentication
- Tokens shall expire after 7 days
- Passwords shall be hashed using bcrypt
- System shall enforce HTTPS (in production)

#### NFR-SC-002: Authorization [P0 - Critical]
- Users shall only access their own data
- Users shall not edit/delete others' content
- API shall verify authorization on all protected routes

#### NFR-SC-003: Data Protection [P0 - Critical]
- Sensitive data shall not be exposed in responses
- Password shall never be returned in API responses
- System shall validate all user inputs
- System shall prevent SQL/NoSQL injection

#### NFR-SC-004: Privacy [P1 - High]
- User contact info shall only be shared after accepted request
- Email addresses shall not be public
- Users shall control profile visibility (future)

---

### 4.3 Usability Requirements

#### NFR-US-001: User Interface [P0 - Critical]
- Interface shall be intuitive and self-explanatory
- Navigation shall be consistent across all pages
- Error messages shall be clear and helpful
- Success feedback shall be immediate

#### NFR-US-002: Accessibility [P1 - High]
- Color contrast shall meet WCAG AA standards
- Form inputs shall have proper labels
- Keyboard navigation shall work throughout

#### NFR-US-003: Language Support [P2 - Medium]
- Interface shall support English
- Interface should support basic Arabic (labels, buttons)
- Date/time formats shall be localized

---

### 4.4 Reliability Requirements

#### NFR-RL-001: Availability [P1 - High]
- System should be available 95% of the time during development
- System shall handle errors gracefully without crashing

#### NFR-RL-002: Error Handling [P0 - Critical]
- System shall catch and log all errors
- System shall display user-friendly error messages
- System shall not expose sensitive information in errors

#### NFR-RL-003: Data Integrity [P0 - Critical]
- Database transactions shall be atomic
- Data validation shall occur on both client and server
- System shall prevent data corruption

---

### 4.5 Maintainability Requirements

#### NFR-MT-001: Code Quality [P0 - Critical]
- Code shall follow consistent naming conventions
- Code shall be properly commented
- Code shall be modular and reusable
- Code shall follow DRY principle

#### NFR-MT-002: Documentation [P0 - Critical]
- All functions shall be documented
- API endpoints shall be documented
- Setup instructions shall be clear and complete

---

### 4.6 Compatibility Requirements

#### NFR-CP-001: Browser Support [P0 - Critical]
- System shall work on Chrome (latest 2 versions)
- System shall work on Firefox (latest 2 versions)
- System shall work on Safari (latest 2 versions)
- System shall work on Edge (latest 2 versions)

#### NFR-CP-002: Device Support [P0 - Critical]
- System shall be responsive on mobile (320px+)
- System shall be responsive on tablet (768px+)
- System shall be responsive on desktop (1024px+)

#### NFR-CP-003: Screen Readers [P3 - Low]
- System should be compatible with screen readers

---

## 5. Data Requirements

### 5.1 Data Models

**User Model:**
```
- _id: ObjectId (auto)
- name: String (required)
- email: String (required, unique)
- password: String (hashed, required)
- phone: String (required)
- location: String (required)
- bio: String (optional)
- avatar: String (URL)
- rating: Number (0-5, default: 0)
- ratingCount: Number (default: 0)
- verified: Boolean (default: false)
- createdAt: Date (auto)
- updatedAt: Date (auto)
```

**Item Model:**
```
- _id: ObjectId (auto)
- title: String (required)
- description: String (required)
- category: String (enum, required)
- location: String (required)
- condition: String (enum, required)
- image: String (URL)
- status: String (enum: available/claimed/completed)
- user: ObjectId (ref: User, required)
- requests: [ObjectId] (ref: Request)
- createdAt: Date (auto)
- updatedAt: Date (auto)
```

**Request Model:**
```
- _id: ObjectId (auto)
- item: ObjectId (ref: Item, required)
- requester: ObjectId (ref: User, required)
- message: String (required)
- status: String (enum: pending/accepted/rejected/completed/cancelled)
- createdAt: Date (auto)
- updatedAt: Date (auto)
```

---

## 6. External Interface Requirements

### 6.1 User Interfaces
- Web-based responsive interface
- Clean, modern design
- Lebanese flag-inspired color scheme (green/red accents)
- Mobile-first approach

### 6.2 Hardware Interfaces
- No specific hardware requirements
- Standard input devices (keyboard, mouse, touchscreen)

### 6.3 Software Interfaces
- React 18+ (frontend framework)
- Node.js 18+ (backend runtime)
- Express 4+ (web framework)
- MongoDB 6+ (database)
- Socket.io (real-time communication)

### 6.4 Communication Interfaces
- HTTP/HTTPS protocol
- WebSocket protocol (for real-time features)
- REST API architecture
- JSON data format

---

## 7. Appendices

### Appendix A: Requirement Traceability Matrix

| Req ID | Description | Priority | Phase | Status |
|--------|-------------|----------|-------|--------|
| FR-UM-001 | User Registration | P0 | 3 | Planned |
| FR-UM-002 | User Login | P0 | 3 | Planned |
| FR-IM-001 | Post Item | P0 | 3 | Planned |
| ... | ... | ... | ... | ... |

### Appendix B: Glossary
- **Donor**: User giving away an item
- **Recipient**: User requesting an item
- **Request**: Formal expression of interest in an item
- **Claim**: Accepted request indicating item will be picked up
- **JWT**: JSON Web Token for authentication

---

**Document Control:**
- **Version**: 1.0
- **Status**: Draft
- **Last Updated**: December 2024
- **Approved By**: [Supervisor Name]
- **Approval Date**: [Date]
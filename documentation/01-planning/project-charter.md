# Project Charter
## Sharikni (شاركني) - Community Resource Sharing Platform

**Document Version:** 1.0  
**Date:** December 2024  
**Project Manager/Developer:** Jad Abou Sbeit  
**Academic Supervisor:** Khaled Ghosson  
**Institution:** AUL University Beirut

---

## 1. Executive Summary

Sharikni (Arabic: شاركني, meaning "Share with Me") is a web-based community resource sharing platform designed specifically for Lebanese communities. The platform enables individuals to give away items they no longer need and find items they're looking for, fostering community solidarity during challenging economic times while promoting sustainable consumption practices.

This senior project will be developed using the MERN stack (MongoDB, Express.js, React, Node.js) over a 12-week period, demonstrating full-stack web development capabilities and addressing a real-world social problem.

---

## 2. Project Background & Justification

### 2.1 Problem Statement

Lebanon is currently facing significant economic challenges that affect daily life:

- **Economic Crisis**: Many families struggle to afford basic necessities
- **Waste Problem**: Usable items are discarded while others desperately need them
- **Community Fragmentation**: Neighbors don't know who can help or who needs help
- **Limited Resources**: Students and families cannot afford furniture, electronics, books, and essentials
- **Environmental Impact**: Excessive waste when items could be reused
- **Trust Issues**: No safe, community-focused platform for local sharing

### 2.2 Opportunity

Lebanon has a strong tradition of community support and neighbor helping neighbor. However, there's no dedicated platform to facilitate this at scale. Existing solutions (social media groups, WhatsApp) are unorganized, lack trust mechanisms, and don't provide proper discovery or matching features.

### 2.3 Solution Overview

Sharikni provides a centralized, user-friendly platform where community members can:
- Post items they want to give away (furniture, electronics, clothes, books, etc.)
- Browse available items by category and location
- Request items they need
- Connect directly with donors
- Build community reputation through ratings and verification
- Track their impact (items shared, people helped)

---

## 3. Project Objectives

### 3.1 Primary Objectives

1. **Develop a functional MERN stack application** demonstrating full-stack development skills
2. **Address a real social need** in Lebanese communities by facilitating resource sharing
3. **Create an intuitive user experience** accessible to all age groups and technical skill levels
4. **Implement secure authentication** and data protection mechanisms
5. **Enable real-time features** for instant notifications and updates
6. **Build a scalable architecture** that can grow with user demand

### 3.2 Learning Objectives

1. Master frontend development with React (components, state management, hooks)
2. Learn backend development with Node.js and Express (REST APIs, middleware)
3. Understand database design and management with MongoDB
4. Implement authentication and authorization with JWT
5. Practice real-time communication with WebSockets (Socket.io)
6. Apply software engineering principles (SDLC, version control, documentation)
7. Develop problem-solving and debugging skills
8. Create professional-grade documentation

### 3.3 Success Criteria

**Technical Success:**
- ✅ Fully functional web application with all core features
- ✅ Responsive design (mobile, tablet, desktop)
- ✅ Secure authentication system
- ✅ Real-time notifications working
- ✅ Database with proper relationships and validation
- ✅ Clean, maintainable code following best practices
- ✅ Comprehensive documentation

**Academic Success:**
- ✅ Completed within 12-week timeframe
- ✅ All SDLC phases documented
- ✅ Professional presentation prepared
- ✅ Working demo for evaluation
- ✅ Final report meeting university standards

**Impact Success:**
- ✅ Solves identified problem effectively
- ✅ User-friendly interface validated by test users
- ✅ Platform ready for potential real-world deployment

---

## 4. Project Scope

### 4.1 In Scope (What WILL be delivered)

**Core Features:**
1. User registration and authentication
2. User profiles with location and contact info
3. Item posting (title, description, category, location, image, condition)
4. Item browsing with search and filters
5. Item detail view with donor information
6. Request system (users can request items)
7. Direct messaging between users
8. Real-time notifications
9. User dashboard (my items, my requests, statistics)
10. Basic rating/review system
11. Responsive design (mobile-friendly)
12. Arabic and English language support (basic)

**Technical Implementation:**
- React frontend with modern UI
- Node.js/Express REST API
- MongoDB database
- JWT authentication
- Socket.io for real-time features
- Image upload functionality
- Secure password hashing
- Input validation
- Error handling

**Documentation:**
- Complete SDLC documentation
- API documentation
- User guide
- Technical documentation
- Final project report

### 4.2 Out of Scope (What will NOT be delivered)

**Phase 1 (Not in initial release):**
- Mobile applications (iOS/Android)
- Payment integration
- Advanced messaging (file sharing, voice/video calls)
- Social media integration
- Email notifications
- SMS notifications
- Advanced analytics dashboard
- Admin panel
- Automated matching algorithm
- Delivery coordination features
- Multi-language full localization (only basic Arabic/English)

**Explicitly Excluded:**
- Monetary transactions (buying/selling)
- Shipping/delivery services
- Insurance or liability coverage
- Background checks on users
- Commercial/business accounts
- Integration with external services (maps, calendar)

### 4.3 Assumptions

1. Users have internet access and a device (phone, tablet, or computer)
2. Users are willing to share basic personal information (name, location, phone)
3. Users will act in good faith (platform relies on community trust)
4. Development will be done by a single developer (solo project)
5. Testing will be conducted with small group of real users
6. No deployment costs during development phase
7. University will provide project evaluation and feedback

### 4.4 Constraints

**Time Constraints:**
- 12-week development period
- Must balance with other academic commitments
- Must complete all phases within semester

**Technical Constraints:**
- Solo development (no team)
- No budget for paid services (cloud hosting, APIs)
- Must use free/open-source tools
- Limited to technologies in MERN stack
- Local development environment only (initially)

**Resource Constraints:**
- Personal laptop/computer for development
- Free tier database (MongoDB Atlas or local)
- Free hosting options only (for future deployment)
- No budget for design tools or assets

**Knowledge Constraints:**
- Learning MERN stack from scratch
- First full-stack project
- Limited prior experience with some technologies

---

## 5. Stakeholders

### 5.1 Primary Stakeholders

**Developer (You):**
- **Role**: Project lead, developer, tester, documentor
- **Interest**: Learn MERN stack, complete senior project successfully, build portfolio piece
- **Expectations**: Gain practical experience, create working application, graduate on time

**Academic Supervisor:**
- **Role**: Project oversight, guidance, evaluation
- **Interest**: Ensure student learning, academic standards met
- **Expectations**: Proper SDLC followed, quality documentation, successful project completion

**University/Department:**
- **Role**: Project approval, grading, degree conferment
- **Interest**: Student demonstrates competency, project meets academic requirements
- **Expectations**: Professional-level work, proper documentation, successful presentation

### 5.2 Secondary Stakeholders

**End Users (Community Members):**
- **Role**: Platform users (donors and recipients)
- **Interest**: Easy way to give/receive items, help community
- **Expectations**: User-friendly, safe, effective platform

**Lebanese Communities:**
- **Role**: Beneficiaries of the platform
- **Interest**: Reduce waste, help those in need, build community
- **Expectations**: Accessible, trustworthy, impactful solution

**Future Employers:**
- **Role**: Portfolio reviewers
- **Interest**: Assess technical skills and project quality
- **Expectations**: Professional code, good documentation, real-world problem-solving

### 5.3 Stakeholder Communication Plan

| Stakeholder | Frequency | Method | Content |
|------------|-----------|---------|---------|
| Academic Supervisor | Weekly | Email/Meeting | Progress updates, blockers, questions |
| Test Users | Bi-weekly | Direct contact | Feature demos, feedback collection |
| University | Milestone-based | Official submission | Phase documentation, reports |

---

## 6. Project Deliverables

### 6.1 Technical Deliverables

1. **Source Code**
   - Complete React frontend application
   - Complete Node.js/Express backend API
   - MongoDB database schema and seed data
   - All configuration files
   - README with setup instructions

2. **Working Application**
   - Fully functional web application
   - All core features implemented and tested
   - Deployed locally with full functionality
   - Demo-ready version

3. **Database**
   - Properly designed schema
   - Sample/test data
   - Backup scripts

### 6.2 Documentation Deliverables

**Phase 1 - Planning:**
- Project Charter ✓
- Requirements Specification
- Stakeholder Analysis
- Feasibility Study
- Risk Assessment

**Phase 2 - Design:**
- System Architecture Document
- Database Schema Design
- API Specification
- UI/UX Design Document
- Data Flow Diagrams

**Phase 3 - Development:**
- Setup Guide
- Component Documentation
- API Documentation
- Code Comments

**Phase 4 - Testing:**
- Test Plan
- Test Cases
- Bug Reports
- Test Results

**Phase 5 - Deployment:**
- User Manual
- Deployment Guide (for future use)
- Final Project Report

### 6.3 Presentation Deliverables

1. **Presentation Slides** (15-20 slides)
   - Problem and solution overview
   - Technical architecture
   - Key features demonstration
   - Challenges and solutions
   - Future enhancements

2. **Live Demo** (5-10 minutes)
   - User registration and login
   - Posting an item
   - Browsing and searching
   - Requesting an item
   - Real-time notifications

3. **Demo Video** (3-5 minutes)
   - Recorded walkthrough of all features
   - Backup in case of technical issues

---

## 7. Timeline & Milestones

### 7.1 Project Timeline (12 Weeks)

**Phase 1: Planning & Requirements (Weeks 0-1)**
- Week 0: Project selection and initial planning
- Week 1: Complete all planning documents
- **Milestone 1**: Planning phase complete, requirements approved

**Phase 2: Analysis & Design (Weeks 2-3)**
- Week 2: System architecture and database design
- Week 3: UI/UX design and API specification
- **Milestone 2**: Design documents complete, ready for development

**Phase 3: Development (Weeks 4-10)**
- Weeks 4-5: Backend API and database setup
- Weeks 6-7: Frontend components and pages
- Week 8: Integration and authentication
- Week 9: Real-time features
- Week 10: Polish and additional features
- **Milestone 3**: Core application complete and functional

**Phase 4: Testing (Week 11)**
- Week 11: Comprehensive testing, bug fixes, user testing
- **Milestone 4**: Application tested and stable

**Phase 5: Deployment & Documentation (Week 12)**
- Week 12: Final documentation, presentation, demo prep
- **Milestone 5**: Project complete and ready for submission

### 7.2 Key Milestones

| Milestone | Description | Due Date | Deliverables |
|-----------|-------------|----------|--------------|
| M1 | Planning Complete | Week 1 | All Phase 1 docs |
| M2 | Design Complete | Week 3 | All Phase 2 docs, wireframes |
| M3 | MVP Complete | Week 8 | Working core features |
| M4 | Full Application | Week 10 | All features implemented |
| M5 | Testing Complete | Week 11 | Bug-free application |
| M6 | Project Complete | Week 12 | Final submission ready |

### 7.3 Critical Path

The following tasks are on the critical path (cannot be delayed):
1. Database schema design (Week 2)
2. Backend API development (Weeks 4-5)
3. Authentication system (Week 6)
4. Frontend-backend integration (Week 7)
5. Core feature completion (Week 8)
6. Testing and bug fixes (Week 11)
7. Final documentation (Week 12)

---

## 8. Budget & Resources

### 8.1 Financial Budget

**Total Budget: $0** (Free/Open Source Only)

| Item | Cost | Notes |
|------|------|-------|
| Development Tools | $0 | VS Code, Git (free) |
| Database | $0 | MongoDB Community/Atlas Free Tier |
| Hosting (Dev) | $0 | Local development |
| Hosting (Future) | $0 | Vercel/Netlify/Railway free tiers |
| Domain Name | $0 | Will use free subdomain initially |
| Design Tools | $0 | Figma free tier, hand sketches |
| Learning Resources | $0 | Free online tutorials, documentation |

### 8.2 Time Budget

**Total Time: ~300-400 hours** over 12 weeks

| Activity | Estimated Hours | % of Total |
|----------|----------------|------------|
| Learning & Research | 80 hours | 25% |
| Development | 160 hours | 50% |
| Testing & Debugging | 40 hours | 12% |
| Documentation | 40 hours | 12% |
| Meetings & Reviews | 10 hours | 3% |

**Weekly Time Commitment:** 25-35 hours/week

### 8.3 Technical Resources

**Hardware:**
- Personal laptop/computer (existing)
- Minimum 8GB RAM, modern processor
- Stable internet connection

**Software (All Free):**
- Node.js (runtime)
- MongoDB Community Edition (database)
- VS Code (IDE)
- Git (version control)
- Postman (API testing)
- Chrome DevTools (debugging)

**Learning Resources:**
- FreeCodeCamp
- MDN Web Docs
- Official documentation (React, Express, MongoDB)
- YouTube tutorials
- Stack Overflow

---

## 9. Risk Management Summary

**High Priority Risks:**
1. **Technical Learning Curve**: Mitigate with structured learning plan, early start
2. **Time Management**: Use project management tools, set weekly goals
3. **Scope Creep**: Strict adherence to defined scope, feature prioritization

**Medium Priority Risks:**
1. **Technical Issues**: Maintain good documentation, seek help when stuck
2. **Testing Gaps**: Allocate full week for testing, involve real users

**Low Priority Risks:**
1. **Resource Availability**: Use free alternatives, cloud services
2. **Health Issues**: Build buffer time into schedule

*(Detailed risk analysis in separate Risk Assessment document)*

---

## 10. Quality Assurance

### 10.1 Quality Standards

**Code Quality:**
- Follow JavaScript/React best practices
- Consistent naming conventions
- Proper error handling
- Code comments for complex logic
- No hardcoded sensitive data

**Documentation Quality:**
- Clear and comprehensive
- Proper formatting and structure
- Regular updates throughout project
- Professional language and presentation

**Application Quality:**
- Intuitive user interface
- Fast load times (< 3 seconds)
- No critical bugs
- Proper validation and error messages
- Responsive design

### 10.2 Testing Strategy

1. **Developer Testing**: Continuous testing during development
2. **User Testing**: Feedback from 5-10 real users
3. **Cross-browser Testing**: Chrome, Firefox, Safari, Edge
4. **Device Testing**: Desktop, tablet, mobile
5. **Security Testing**: Authentication, data protection

---

## 11. Project Approval

### 11.1 Sign-off

This project charter has been reviewed and approved by:

**Student/Developer:**
- Name: Jad Abou Sbeit
- Signature: JadAbouSbeit
- Date: 14/12/2025

**Academic Supervisor:**
- Name: ______________________
- Signature: ______________________
- Date: ______________________

**Department Head (if required):**
- Name: ______________________
- Signature: ______________________
- Date: ______________________

### 11.2 Change Management

Any significant changes to project scope, timeline, or deliverables must be:
1. Documented in writing
2. Reviewed with academic supervisor
3. Approved before implementation
4. Updated in project documentation

---

## 12. Appendices

### Appendix A: Definitions

- **MERN Stack**: MongoDB, Express.js, React, Node.js
- **REST API**: Representational State Transfer Application Programming Interface
- **JWT**: JSON Web Token (authentication method)
- **SDLC**: Software Development Life Cycle
- **MVP**: Minimum Viable Product

### Appendix B: References

- React Documentation: https://react.dev
- Node.js Documentation: https://nodejs.org
- MongoDB Documentation: https://docs.mongodb.com
- Express.js Documentation: https://expressjs.com

### Appendix C: Contact Information

**Project Developer:**
- Name: Jad Abou Sbeit
- Email: jadabousbeit@gmail.com
- Phone: +961 3 905 913
- GitHub: Jad Abou Sbeit

**Academic Supervisor:**
- Name: Khaled Ghosson
- Email: [Supervisor Email]
- Office: AUL University

---

**Document Control:**
- **Created**: December 2024
- **Last Updated**: December 2024
- **Version**: 1.0
- **Status**: Draft / Approved
- **Next Review**: [Date]

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Dec 2024 | Jad Abou Sbeit| Initial document creation |
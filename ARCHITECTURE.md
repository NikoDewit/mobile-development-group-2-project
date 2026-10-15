# PotLuck — App Architecture

**Course:** CPRG-303-A  
**Team:** Team Maximum  
**App:** PotLuck — Group Budgeting App

## 1. Development Framework

- **Framework:** React Native with Expo
- **Language:** TypeScript
- **Target platforms:** Android primarily, with iOS compatibility where feasible.

React Native with Expo will allow the team to develop a mobile application using a shared codebase. TypeScript will help with type checking and code organization.

## 2. Project Dependencies

| Dependency | Purpose |
|---|---|
| Expo | Mobile development and testing |
| React Native | Mobile user interface |
| TypeScript | Type checking |
| Expo Router | Screen navigation |
| Supabase | Backend and database |
| Supabase Auth | User authentication |
| React Native StyleSheet | Interface styling |

These technologies are proposed for team approval.

## 3. Navigation Strategy

Expo Router is proposed for navigation.

Planned screens include:
- Login and registration
- Home dashboard
- Groups and group details
- Add expense
- Budget overview
- Expense history
- Balances and settlements
- User profile and settings

Tab navigation may be used for main sections, with stack navigation for detailed screens and forms.

## 4. Hardware Integrations

No hardware integrations are required for the initial version. GPS, camera, microphone, and fingerprint access are not currently planned.

## 5. Database

**Proposed database:** PostgreSQL through Supabase.

The database will store:
- Users
- Groups
- Group members
- Expenses
- Expense splits
- Budgets
- Settlements

A relational database is suitable because these records are connected. Access policies will help prevent unauthorized access to user and group information.

## 6. Authentication

**Proposed solution:** Supabase Auth.

Users will be able to register, log in, and log out. Email and password authentication is planned, with Google sign-in considered if feasible.

Database access policies will restrict users to information they are authorized to access.

## 7. AI Features

No AI features are planned for the initial version. Expense splitting and budget calculations will use standard application logic.

## 8. Architecture Decision Records

### ADR-001: Mobile Framework

**Decision:** React Native with Expo.

**Reason:** Supports Android development and potential iOS compatibility using a shared codebase.

**Status:** Proposed.

### ADR-002: Navigation

**Decision:** Expo Router with tab and stack navigation.

**Reason:** Organizes the main app sections and provides navigation between detailed screens.

**Status:** Proposed.

### ADR-003: Database and Backend

**Decision:** Supabase with PostgreSQL.

**Reason:** Supports relationships between users, groups, expenses, budgets, and settlements.

**Status:** Proposed.

### ADR-004: Authentication

**Decision:** Supabase Auth.

**Reason:** Provides managed user authentication without requiring the team to build an authentication system from scratch.

**Status:** Proposed.

### ADR-005: Shared Expense Splitting

**Decision:** Store expenses separately from participant shares and calculate each participant's portion.

**Reason:** Allows users to track how much each person owes. Participant shares must add up to the original expense amount.

**Status:** Proposed.

### ADR-006: Budget Tracking

**Decision:** Store budget limits and compare them with recorded expenses.

**Reason:** Allows users to monitor spending against their planned budgets.

**Status:** Proposed.

### ADR-007: Settlement Tracking

**Decision:** Track debts and record when they are settled instead of processing payments directly.

**Reason:** Supports the app's purpose while keeping the initial project manageable. Users can complete payments externally, such as through Interac e-Transfer.

**Status:** Proposed.

### ADR-008: Security

**Decision:** Use authentication and database access policies to protect user and group information.

**Reason:** Expense and financial records should only be accessible to authorized users.

**Status:** Proposed.

## 9. Project Scope

The initial version will focus on:
1. User registration and login.
2. Group creation and membership.
3. Shared expense entry and splitting.
4. Budget tracking.
5. Balance and settlement tracking.

Additional features will be considered based on project requirements and available time.

This document will be updated as the team confirms its architectural decisions.
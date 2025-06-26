# PKL SST 2025 🚀

<div align="center">

![PKL SST 2025 Banner](https://via.placeholder.com/1200x300/0d1117/58a6ff?text=PKL+SST+2025+%7C+Innovation+Through+Code)

[![GitHub Organization](https://img.shields.io/badge/GitHub-Organization-181717?style=for-the-badge&logo=github)](https://github.com/pkl-sst-2025)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)
[![Contributors](https://img.shields.io/badge/Contributors-50+-green?style=for-the-badge)](https://github.com/orgs/pkl-sst-2025/people)
[![Projects](https://img.shields.io/badge/Active_Projects-15+-orange?style=for-the-badge)](https://github.com/orgs/pkl-sst-2025/repositories)

**🎓 Program Kerja Lapangan Smartelco Solusi Teknologi 2025**  


</div>

---

## 📑 Table of Contents


- [🎯 Development Philosophy](#-development-philosophy)
- [🚀 Development Approach](#-development-approach)
- [🏛️ Clean Architecture (Backend - Rust)](#️-clean-architecture-backend---rust)
- [🎭 MVVM Architecture (Frontend - SolidJS)](#-mvvm-architecture-frontend---solidjs)
- [📋 Repository Management SOP](#-repository-management-sop)
- [📊 Project Management SOP](#-project-management-sop)
- [🔄 Development Workflow SOP](#-development-workflow-sop)
- [🛠️ Tech Stack](#️-tech-stack)


---

## 🎯 Development Philosophy

<div align="center">

| 🧹 Clean Code | 📚 Documentation | 🔄 Continuous Learning |
|:---:|:---:|:---:|
| Maintainable & Readable | Comprehensive & Clear | Always Improving |

</div>

### 💎 Core Principles

#### 🧩 **Clean and Maintainable Code**
```typescript
// ✅ Good: Self-documenting code
const calculateUserEngagementScore = (user: User): number => {
  return user.activities
    .filter(activity => activity.isCompleted)
    .reduce((score, activity) => score + activity.points, 0);
};

// ❌ Bad: Unclear purpose
const calc = (u: any) => u.a.filter(x => x.c).reduce((s, x) => s + x.p, 0);
```

#### 📖 **Comprehensive Documentation**
- 📝 **Code Comments**: Explain the "why", not just the "what"
- 📋 **API Documentation**: Complete endpoint specifications
- 🗺️ **Architecture Docs**: System design and data flow
- 🚀 **Setup Guides**: Step-by-step installation instructions

---

## 🚀 Development Approach

<div align="center">

### 🎯 Tracer Bullet Development

![Tracer Bullet Flow](https://via.placeholder.com/800x400/1e293b/f1f5f9?text=UI+%E2%86%92+API+%E2%86%92+Service+%E2%86%92+Database)

</div>

#### 📊 Overview

Tracer Bullet Development adalah pendekatan metodologis yang berfokus pada membangun fungsionalitas end-to-end melalui semua layer sistem (dari UI hingga database) dengan fitur minimal awal. Seperti peluru tracer yang membantu penembak memvisualisasikan jalur tembakan, pendekatan ini memungkinkan tim untuk memvalidasi arsitektur sistem sejak awal sambil menetapkan pola pengembangan yang jelas.

#### 🏗️ Key Components

##### 📐 **Architectural Layers**

**UI Layer (Frontend Interface)** → **Business Logic Layer (Backend Processing)** → **Data Access Layer (Service Integration)** → **Database Layer (Data Storage)**

##### ⚡ **Development Flow**

| Phase | 🎯 Focus | 📋 Deliverables |
|:---:|:---|:---|
| **Phase 1** | 🏗️ Minimal Setup | UI + API + Database |
| **Phase 2** | ✅ Path Validation | End-to-End Testing |
| **Phase 3** | 📈 Feature Expansion | Incremental Complexity |

#### 🏆 Benefits

<div align="center">

| 🔧 Technical Advantages | 📊 Project Benefits |
|:---|:---|
| ✅ Early architectural validation | 🚀 Accelerated prototype development |
| ✅ Reduced integration risks | 👥 Early stakeholder feedback |
| ✅ Clear development patterns | 💰 Reduced technical debt |
| ✅ Performance baseline establishment | 📈 Clearer progress metrics |

</div>

---

## 🏛️ Clean Architecture (Backend - Rust)

<div align="center">

![Clean Architecture](https://via.placeholder.com/800x400/1e293b/f1f5f9?text=Clean+Architecture+%7C+Separation+of+Concerns)

</div>

### 📊 Overview

Clean Architecture adalah filosofi desain perangkat lunak yang memisahkan kepentingan ke dalam lapisan yang berbeda, membuat sistem lebih mudah dipelihara, dapat diuji, dan independen dari framework eksternal atau tools. Ini menekankan pemisahan logika bisnis dari mekanisme pengiriman dan database.

### 📂 Directory Structure

```plaintext
backend-rust/
├── Cargo.toml               # Main configuration file for the Rust project
├── Cargo.lock               # Dependency lock file
├── .env                     # Environment configuration file
├── README.md                # Project documentation
└── src/
    ├── main.rs              # Application entry point
    ├── lib.rs               # Shared module file (optional)
    │
    ├── dtos/                # Data Transfer Objects (interface adapters)
    │   ├── mod.rs           # Main module for DTOs
    │   ├── requests/        # Request data (input)
    │   │   ├── mod.rs       # Main module for request DTOs
    │   │   ├── user/        # DTOs for user-related features
    │   │   │   ├── mod.rs
    │   │   │   ├── create_user_request.rs
    │   │   │   └── update_user_request.rs
    │   │   └── project/     # DTOs for project-related features
    │   │       ├── mod.rs
    │   │       ├── create_project_request.rs
    │   │       └── update_project_request.rs
    │   │
    │   └── responses/       # Response data (output)
    │       ├── mod.rs       # Main module for response DTOs
    │       ├── user/        # DTOs for user responses
    │       │   ├── mod.rs
    │       │   ├── user_response.rs
    │       │   └── user_list_response.rs
    │       └── common/      # DTOs for common responses
    │           ├── mod.rs
    │           ├── api_response.rs
    │           └── pagination_response.rs
    │
    ├── models/              # Domain models/entities (core business logic)
    │   ├── mod.rs           # Main module for entities
    │   ├── user.rs
    │   ├── project.rs
    │   ├── work_order.rs
    │   └── common.rs        # Common entities (e.g., statuses, enums)
    │
    ├── repositories/        # Repository layer (interface adapters)
    │   ├── mod.rs           # Main module for repositories
    │   ├── traits/          # Interfaces for repositories
    │   │   ├── mod.rs
    │   │   ├── user_repository.rs
    │   │   └── project_repository.rs
    │   │
    │   └── impls/           # Repository implementations
    │       ├── mod.rs
    │       ├── user_repository_impl.rs
    │       └── project_repository_impl.rs
    │
    ├── services/            # Service/UseCase layer (application logic)
    │   ├── mod.rs           # Main module for services
    │   ├── traits/          # Interfaces for services
    │   │   ├── mod.rs
    │   │   ├── user_service.rs
    │   │   └── project_service.rs
    │   │
    │   └── impls/           # Service implementations
    │       ├── mod.rs
    │       ├── user_service_impl.rs
    │       └── project_service_impl.rs
    │
    ├── handlers/            # Handler/Controller layer (interface adapters)
    │   ├── mod.rs           # Main module for handlers
    │   ├── user_handler.rs  # Handler for user-related features
    │   └── project_handler.rs # Handler for project-related features
    │
    ├── config/              # Configuration layer (framework and drivers)
    │   ├── mod.rs           # Main configuration module
    │   └── app_config.rs    # Application configurations (e.g., DB, API)
    │
    ├── middleware/          # Middleware components (framework and drivers)
    │   ├── mod.rs           # Main module for middleware
    │   └── auth.rs          # Authentication middleware
    │
    └── utils/               # Utilities and helpers (framework and drivers)
        ├── mod.rs           # Main module for utilities
        ├── errors.rs        # Error handling utilities
        └── constants.rs     # Global constants
```

### 💡 Layer Explanation

- **`dtos/`**: Handles input (requests) and output (responses) data transfer between layers
- **`models/`**: Represents core business entities and domain objects
- **`repositories/`**: Abstraction for data access and manipulation, such as database queries
- **`services/`**: Contains business logic and application rules (use cases)
- **`handlers/`**: API entry points or interaction interfaces for external clients
- **`config/`**: Application and infrastructure configurations
- **`middleware/`**: Cross-cutting concerns like authentication or logging
- **`utils/`**: Helper functions and utilities for error handling and constants

---

## 🎭 MVVM Architecture (Frontend - SolidJS)

<div align="center">

![MVVM Architecture](https://via.placeholder.com/800x400/1e293b/f1f5f9?text=MVVM+Architecture+%7C+Model+View+ViewModel)

</div>

### 📊 Overview

MVVM (Model-View-ViewModel) architecture membagi aplikasi menjadi tiga layer utama: **Model**, **ViewModel**, dan **View**. Pattern ini memfasilitasi pemisahan kepentingan yang bersih, membuat aplikasi lebih mudah dipelihara, dapat diuji, dan dapat diskalakan.

### 🏗️ Layers Overview

1. **Model Layer**:
   - Merepresentasikan **data layer** dari aplikasi
   - Bertanggung jawab untuk mendefinisikan logika bisnis, berinteraksi dengan API, dan mengelola state aplikasi independen dari UI
   - Examples: `UserModel`, `ProjectModel`, `api/userApi.ts`

2. **ViewModel Layer**:
   - Bertindak sebagai **jembatan antara Model dan View**
   - Berisi state dan logik yang dikonsumsi oleh View
   - Memproses data dari Model agar View-friendly
   - Examples: State management, Custom hooks seperti `useUser`

3. **View Layer**:
   - Merepresentasikan **UI layer** dari aplikasi
   - Menampilkan data dari ViewModel dan update otomatis ketika ViewModel state berubah
   - Example: Components seperti `UserView`

### 📂 Directory Structure

```plaintext
frontend-solidjs/
├── public/                      # Static assets
├── src/                         # Application source code
│   ├── models/                  # Model layer
│   │   ├── UserModel.ts         # Represents the user data and logic
│   │   ├── ProjectModel.ts      # Represents the project data and logic
│   │   └── api/                 # API layer for network requests
│   │       ├── apiClient.ts     # HTTP client setup (e.g., Axios)
│   │       └── userApi.ts       # API calls for user data
│   │
│   ├── viewmodels/              # ViewModel layer
│   │   ├── UserViewModel.ts     # Manages user-related state and logic
│   │   ├── ProjectViewModel.ts  # Manages project-related state and logic
│   │   └── hooks/               # Custom hooks to connect View to ViewModel
│   │       ├── useUser.ts       # Hook for user logic
│   │       └── useProject.ts    # Hook for project logic
│   │
│   ├── views/                   # View layer
│   │   ├── UserView.tsx         # Displays user data
│   │   ├── ProjectView.tsx      # Displays project data
│   │   └── components/          # Reusable UI components
│   │       ├── Button.tsx       # Example: Button component
│   │       └── InputField.tsx   # Example: Input field component
│   │
│   ├── services/                # Shared services
│   │   ├── AuthService.ts       # Handles authentication
│   │   └── LoggerService.ts     # Handles logging
│   │
│   ├── store/                   # Centralized state management
│   │   ├── index.ts             # Store setup using SolidJS's createStore
│   │   └── slices/              # State slices
│   │       ├── userSlice.ts     # User-specific state
│   │       └── projectSlice.ts  # Project-specific state
│   │
│   ├── routes/                  # Routing configuration
│   │   ├── index.tsx            # Defines app routes
│   │   └── ProtectedRoute.tsx   # Wrapper for protected routes
│   │
│   ├── config/                  # Application configuration
│   │   ├── AppConfig.ts         # Environment variables and global settings
│   │   └── mod.ts               # Module entry point
│   │
│   ├── middleware/              # Middleware utilities
│   │   └── auth.ts              # Authentication middleware
│   │
│   ├── utils/                   # Shared utilities
│   │   ├── errors.ts            # Error handling utilities
│   │   ├── constants.ts         # Application-wide constants
│   │   └── helpers.ts           # Helper functions
│   │
│   ├── App.tsx                  # Root component
│   └── main.tsx                 # Application entry point
├── .env                         # Environment variables
├── .gitignore                   # Git ignore file
├── package.json                 # Node.js dependencies and scripts
├── tsconfig.json                # TypeScript configuration
└── vite.config.ts               # Vite configuration
```

---

## 📋 Repository Management SOP

### 📁 Repository Naming Convention

#### 📝 Format
```
[product]-[platform]-[component]
```

#### ✅ Examples

<div align="center">

| ✅ **Good Examples** | ❌ **Bad Examples** |
|:---|:---|
| `pkl-be-main` | `pkl-backend-management` |
| `pkl-fe-web` | `PKL_Frontend` |
| `pkl-mobile-android` | `pkl` |
| `ecommerce-api-auth` | `ecommerce_system` |

</div>

### 📂 Repository Structure

```
repository/
├── 📁 .github/
│   ├── 📁 workflows/       # 🔄 CI/CD workflows
│   ├── 📁 ISSUE_TEMPLATE/  # 🐛 Issue templates
│   └── 📁 PR_TEMPLATE/     # 📝 PR templates
├── 📁 docs/
│   ├── 📁 api/            # 📚 API documentation
│   ├── 📁 setup/          # ⚙️ Setup guides
│   └── 📁 architecture/   # 🏗️ Architecture docs
├── 📁 src/
├── 📁 tests/
└── 📄 README.md
```

### 📝 Required Documentation

1. **README.md**
   - Project overview
   - Setup instructions
   - Development guide
   - Testing guide

2. **CONTRIBUTING.md**
   - Contribution guidelines
   - Code style guide
   - PR process

3. **CHANGELOG.md**
   - Version history
   - Feature updates
   - Bug fixes

---

## 📊 Project Management SOP

### 📊 Project Board Structure

#### Board Columns

<div align="center">

| Column | 📝 Description | 🎯 Purpose |
|:---|:---|:---|
| 📥 **Backlog** | Upcoming features, planned improvements | Future planning |
| 🎯 **Todo** | Current sprint tasks, prioritized items | Ready for development |
| 💻 **In Progress** | Active development, assigned tasks | Current work |
| 👀 **In Review** | Code review, QA testing | Quality assurance |
| ✅ **Done** | Completed tasks, deployed features | Completed work |

</div>

#### Task Labels

```
Priority:
🔴 Critical
🟡 High
🟢 Normal
🔵 Low

Type:
🚀 Feature
🐛 Bug
📚 Documentation
🛠️ Maintenance
```

### Important Notes

1. Jangan lupa set **Start date** dan **Due date** untuk setiap issue _(field harus bernama Start date dan Due date)_
2. Tidak bisa set Start date setelah Due date
3. Tidak bisa set Start date dan Due date dalam hari yang sama (jika butuh satu hari, set Due date ke hari berikutnya)

### 🎫 Issue Management

#### Issue Title Format

```
[type]: Brief description of the issue

Examples:
✅ feat: Implement JWT authentication
✅ fix: Resolve token expiration issue
✅ docs: Update API endpoints documentation

❌ Implementation of auth
❌ Fixed bug
❌ Updated docs
```

#### Issue Template

```markdown
### Overview
[Clear, concise description]

### Time Configuration
time: HH:MM-HH:MM

// Time Available:
// 1. time: HH:MM-HH:MM       -> Specific time range
// 2. time: full-day          -> Full day event
// 3. Not Configuration Time  -> Full day event

### Acceptance Criteria
- [ ] Specific requirement 1
- [ ] Specific requirement 2
- [ ] Specific requirement 3

### Technical Specifications
Environment:
- Rust version: [e.g., 1.70.0]
- Database: [e.g., PostgreSQL 14]
- Dependencies: [List key dependencies]

### Additional Context
[Screenshots, diagrams, or additional information]
```

#### Meeting Issue Template

```markdown
Title: 📅 Meeting: [Meeting Purpose] - [Team/Project Name]

### Overview
🎯 Purpose: [Clear meeting objective]
👥 Attendees: @username1 @username2 @username3

### Time Configuration
time: HH:MM-HH:MM

### Meeting Agenda
1. [ ] Opening (5m)
2. [ ] [Agenda Item 1] (XXm)
3. [ ] [Agenda Item 2] (XXm)
4. [ ] Action Items & Next Steps (10m)

### Required Documents
📎 Pre-Meeting
- [ ] [Document 1] - [Link/Description]
- [ ] [Document 2] - [Link/Description]

📊 Meeting Materials
- [ ] [Presentation/Document to be discussed]
- [ ] [Additional materials]

### Minutes of Meeting (MoM)
To be filled during/after meeting:
- [ ] Key Discussion Points
- [ ] Decisions Made
- [ ] Action Items & Assignees
- [ ] Next Meeting Schedule (if applicable)

### Technical Setup
💻 Meeting Platform:
- Platform: [e.g., Google Meet, Zoom]
- Link: [Meeting Link]
- Backup: [Alternative platform/contact]

### Additional Context
- Recording Permission: [Yes/No]
- Special Notes: [Any additional information]
```

### 🔄 Pull Request Process

#### PR Naming Convention

```
[type]: Brief description (#issue-number)

Examples:
- feat: Add user authentication (#123)
- fix: Resolve token expiration (#456)
```

#### PR Template

```markdown
### 🎯 Purpose
[Brief description of the changes]

### 🔄 Changes Made
- Change 1
- Change 2
- Change 3

### 🧪 Testing
- [ ] Unit tests added
- [ ] Integration tests updated
- [ ] Manual testing completed

### 📝 Documentation
- [ ] Code comments updated
- [ ] API docs updated
- [ ] README updated if needed

### 🔍 Review Checklist
- [ ] Code follows style guidelines
- [ ] No unused imports/variables
- [ ] Error handling implemented
- [ ] Logging added where necessary

### 📸 Screenshots (if applicable)
[Add screenshots here]

Fixes #[issue-number]
```

---

## 🔄 Development Workflow SOP

### 🌿 Branch Management

<div align="center">

![Branch Flow](https://via.placeholder.com/800x400/1e293b/f1f5f9?text=Git+Branch+Flow+%7C+Feature+Branches)

</div>

#### Branch Types

```
Main Branches:
- main        # Production code
- develop     # Development code
- staging     # Pre-production testing

Feature Branches:
- feature/    # New features
- bugfix/     # Bug fixes found during development or testing
- hotfix/     # Emergency fixes for production issues
- release/    # Release preparation (testing, final touches)
- experiment/ # Experimental ideas or prototypes
- support/    # Support for legacy systems or specific use cases
- chore/      # Minor tasks like dependency updates or refactoring
- docs/       # Documentation improvements or additions
- test/       # Testing or creating test scenarios
```

#### Branch Naming

```
[type]/[issue-number]-[brief-description]

Examples:
✅ feature/123-user-authentication
✅ bugfix/456-login-error
✅ hotfix/789-security-patch

❌ new-feature
❌ fix-bug
❌ update
```

### 💬 Commit Guidelines

#### Commit Message Structure

```
[type]: Brief description #issue-number

[Optional detailed description]

[Optional footer]
```

#### Commit Types

```
🚀 feat     : New feature
🐛 fix      : Bug fix
📚 docs     : Documentation
🎨 style    : Formatting
♻️ refactor : Code restructure
⚡ perf     : Performance
🧪 test     : Testing
🛠️ chore    : Maintenance tasks
```

#### ✅ Good Examples

```
🚀 feat: Add user authentication system #123
[Optional] Implements JWT-based authentication with refresh tokens
- Add token generation
- Add token validation
- Add refresh mechanism

🐛 fix: Resolve token expiration issue fixes #456
Updates token validation to handle timezone differences

📚 docs: Update API documentation closes #789
Complete documentation for authentication endpoints
```

#### Issue Reference Keywords

```
Closing Issues:
fixes #123     // Will close issue when merged
closes #123    // Will close issue when merged
resolves #123  // Will close issue when merged

Referencing Issues:
ref #123      // Reference without closing
see #123      // Reference without closing
```

---

## 🛠️ Tech Stack

<div align="center">

### Frontend
![SolidJS](https://img.shields.io/badge/SolidJS-2C4F7C?style=for-the-badge&logo=solid&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)

### Backend
![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)
![Actix Web](https://img.shields.io/badge/Actix%20Web-000000?style=for-the-badge&logo=rust&logoColor=white)

### Database
![SurrealDB](https://img.shields.io/badge/SurrealDB-FF00A0?style=for-the-badge&logo=surrealdb&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

</div>

---

<div align="center">

### 🌟 Made with ❤️ by PKL SST 2025 Team

**🚀 Innovating Today, Leading Tomorrow**

![Visitor Count](https://visitor-badge.laobi.icu/badge?page_id=pkl-sst-2025.pkl-sst-2025)
[![GitHub followers](https://img.shields.io/github/followers/pkl-sst-2025?style=social)](https://github.com/pkl-sst-2025)

---

</div>

# 📘 Smartelco - Standard Operating Procedures

# Table of Contents
1. [Organization Overview](#organization-overview)
2. [Repository Management SOP](#repository-management-sop)
3. [Project Management SOP](#project-management-sop)
4. [Development Workflow SOP](#development-workflow-sop)
5. [Code Review & Quality SOP](#code-review--quality-sop)
6. [Release Management SOP](#release-management-sop)

---

# Organization Overview

## 🏢 About Smartelco
Smartelco is a technology organization specializing in workforce management solutions. We prioritize code quality, clear documentation, and efficient development processes.

## 👥 Team Structure
- Technical Lead
- Backend Developers
- Frontend Developers
- QA Engineers
- DevOps Engineers
- Project Managers

## 🎯 Development Philosophy
- Clean and maintainable code
- Comprehensive documentation
- Test-driven development
- Security-first approach

---

# Repository Management SOP

## 📁 Repository Naming Convention
### Format
```
[product]-[platform]-[component]
```

### Examples
```
✅ Good:
- wfm-be-main
- wfm-fe-web
- wfm-mobile-android

❌ Bad:
- workforce-management
- WFM_Backend
- wfm
```

## 📂 Repository Structure
```
repository/
├── .github/
│   ├── workflows/       # CI/CD workflows
│   ├── ISSUE_TEMPLATE/  # Issue templates
│   └── PR_TEMPLATE/     # PR templates
├── docs/
│   ├── api/            # API documentation
│   ├── setup/          # Setup guides
│   └── architecture/   # Architecture docs
├── src/
├── tests/
└── README.md
```

## 📝 Required Documentation
1. README.md
   - Project overview
   - Setup instructions
   - Development guide
   - Testing guide

2. CONTRIBUTING.md
   - Contribution guidelines
   - Code style guide
   - PR process

3. CHANGELOG.md
   - Version history
   - Feature updates
   - Bug fixes

---

# Project Management SOP

## 📊 Project Board Structure

### Board Columns
1. 📥 Backlog
   - Upcoming features
   - Planned improvements
   
2. 🎯 Todo
   - Current sprint tasks
   - Prioritized items
   
3. 💻 In Progress
   - Active development
   - Assigned tasks
   
4. 👀 In Review
   - Code review
   - QA testing
   
5. ✅ Done
   - Completed tasks
   - Deployed features

### Task Labels
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

## 🎫 Issue Management

### Issue Title Format
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

### Issue Template
```markdown
### Overview
[Clear, concise description]

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

## 🔄 Pull Request Process

### PR Naming Convention
```
[type]: Brief description (#issue-number)

Examples:
- feat: Add user authentication (#123)
- fix: Resolve token expiration (#456)
```

### PR Template
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

# Development Workflow SOP

## 🌿 Branch Management

### Branch Types
```
Main Branches:
- main        # Production code
- develop     # Development code
- staging     # Pre-production testing

Feature Branches:
- feature/    # New features
- bugfix/     # Bug fixes
- hotfix/     # Emergency fixes
- release/    # Release preparation
```

### Branch Naming
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

## 💬 Commit Guidelines

### Commit Message Structure

#### Basic Format
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

### Examples with Issue References

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

♻️ refactor: Optimize database queries ref #101 #102
Improved query performance for user lookup operations

🧪 test: Add integration tests for auth system #202
Added comprehensive test suite for authentication flow
```

#### ❌ Bad Examples
```
Updated code #123                  // Missing type, not descriptive
fix: Fixed authentication stuff    // Not imperative mood
feat: Auth implementation          // Too vague, no issue reference
feature: Added user auth #123      // Wrong type format
docs: Updating API docs closes#456 // No space before issue number
```

### Issue Reference Keywords

#### Closing Issues
```
fixes #123     // Will close issue when merged
closes #123    // Will close issue when merged
resolves #123  // Will close issue when merged

Example:
🐛 fix: Resolve null pointer exception fixes #123
```

#### Referencing Issues
```
ref #123      // Reference without closing
see #123      // Reference without closing

Example:
🚀 feat: Begin authentication implementation ref #123
```

### Best Practices

#### 1. Atomic Commits
- One logical change per commit
- Makes reviews easier
- Simplifies rollbacks if needed

#### 2. Clear Descriptions
- Use imperative mood ("Add" not "Added")
- Be specific about what changed
- Include context if needed

#### 3. Issue References
- Always include issue number for trackability
- Use appropriate closing keywords when applicable
- Multiple issues should be space-separated

#### 4. Structured Format
```
[type]: Action description #issue-number

Why:
- Reason for change
- Context if needed

What:
- Specific change 1
- Specific change 2

Example:
🚀 feat: Implement user roles system #123

Why:
- Required for permission management
- Supports upcoming features

What:
- Add role model and migration
- Implement role assignment
- Add role validation middleware
```

### Common Patterns

#### Feature Development
```
feature/123-user-auth

🚀 feat: Initialize user authentication structure #123
🚀 feat: Add token generation and validation #123
🧪 test: Add authentication unit tests #123
📚 docs: Add authentication API documentation #123
```

#### Bug Fixing
```
bugfix/456-token-expiration

🐛 fix: Add token validation check fixes #456
🧪 test: Add expiration test cases #456
```

#### Documentation
```
docs/789-api-docs

📚 docs: Add authentication endpoints documentation #789
📚 docs: Add request/response examples closes #789
```

### Tips
1. Review your commits before pushing
2. Use Git hooks to enforce commit message format
3. Keep commit history clean and meaningful
4. Link related issues and PRs in commit messages

### Git Commands for Better Commits
```bash
# Amend last commit message
git commit --amend -m "🚀 feat: Better description #123"

# Interactive rebase to clean up commits
git rebase -i HEAD~3

# Add more changes to last commit
git commit --amend --no-edit

# View commit history with graph
git log --graph --oneline
```

---

# Code Review & Quality SOP

## 👀 Review Process

### Pre-Review Checklist
```
📝 Developer Tasks:
1. Self-review completed
2. Tests written and passing
3. Documentation updated
4. PR description complete
5. Branch up to date

🔍 Reviewer Tasks:
1. Understand issue context
2. Check acceptance criteria
3. Review code changes
4. Test functionality
5. Provide constructive feedback
```

### Review Standards
```
Review Comments:
✅ "Consider using Option<T> for nullable values"
✅ "This could be simplified using .map()"
✅ "Missing error handling for this case"

❌ "This is wrong"
❌ "Why did you do this?"
❌ "Fix this"
```

## 🧪 Testing Requirements

### Test Categories
```
1. Unit Tests
   - Business logic
   - Data transforms
   - Utility functions

2. Integration Tests
   - API endpoints
   - Database operations
   - External services

3. End-to-End Tests
   - User workflows
   - System integration
```

---

# Release Management SOP

## 🏷️ Version Control

### Version Format
```
MAJOR.MINOR.PATCH

Examples:
1.0.0 - Initial release
1.1.0 - New feature
1.1.1 - Bug fix
```

### Release Process
1. Version Bump
   ```
   - Update version in Cargo.toml
   - Update CHANGELOG.md
   - Create release branch
   ```

2. Testing
   ```
   - Run all tests
   - Perform QA checks
   - Security audit
   ```

3. Documentation
   ```
   - Update API docs
   - Update README
   - Generate release notes
   ```

4. Deployment
   ```
   - Create git tag
   - Deploy to staging
   - Verify deployment
   - Deploy to production
   ```

## 📋 Release Checklist
```markdown
Pre-Release:
- [ ] Version updated
- [ ] CHANGELOG updated
- [ ] Tests passing
- [ ] Documentation current
- [ ] Security audit complete

Release:
- [ ] Release branch created
- [ ] Code frozen
- [ ] QA approval
- [ ] Release notes prepared
- [ ] Git tag created

Post-Release:
- [ ] Deployment successful
- [ ] Monitoring in place
- [ ] Stakeholders notified
- [ ] Documentation published
```

---

# Additional Resources

## 📚 Documentation Links
- [Git Workflow](https://github.com/Smartelco/.github/blob/main/documentation/git-workflow.md)
- [Detailed Setup Guide](./docs/setup/README.md)
- [API Documentation](./docs/api/README.md)
- [Architecture Guide](./docs/architecture/README.md)

## 🔧 Tools and Resources
- [Development Environment Setup](./docs/setup/dev-environment.md)
- [Testing Guide](./docs/testing/README.md)
- [Security Guidelines](./docs/security/README.md)

## 📞 Support Contacts
- Technical Lead: [Email]
- Project Manager: [Email]
- DevOps Support: [Email]

---

# 📅 Meeting Schedule

- Daily Standup: 10:00 AM
- Sprint Planning: Every Monday 2:00 PM
- Code Review: Tuesday/Thursday 3:00 PM
- Retrospective: Every other Friday 4:00 PM

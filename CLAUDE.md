# CLAUDE.md - AI Assistant Guide for ErisReborn

**Last Updated:** 2025-11-14
**Status:** Initial Repository Setup

## Project Overview

**ErisReborn** is a new project currently in its initial setup phase. This document serves as a comprehensive guide for AI assistants (like Claude) working on this codebase.

### Project Status
- **Current Phase:** Initial repository creation
- **Primary Branch:** TBD (to be determined once main branch is established)
- **Development Branch Pattern:** `claude/claude-md-*` for AI-assisted development

---

## Table of Contents

1. [Repository Structure](#repository-structure)
2. [Development Workflow](#development-workflow)
3. [Git Conventions](#git-conventions)
4. [Code Conventions](#code-conventions)
5. [AI Assistant Guidelines](#ai-assistant-guidelines)
6. [Testing Strategy](#testing-strategy)
7. [Documentation Standards](#documentation-standards)
8. [Common Tasks](#common-tasks)

---

## Repository Structure

### Current Structure
```
ErisReborn/
├── .git/                 # Git repository metadata
└── CLAUDE.md            # This file
```

### Planned Structure
*(To be updated as the project evolves)*

```
ErisReborn/
├── src/                 # Source code
├── tests/               # Test files
├── docs/                # Documentation
├── config/              # Configuration files
├── scripts/             # Build and utility scripts
├── .github/             # GitHub workflows and templates
├── CLAUDE.md           # This file
├── README.md           # Project README
└── [other files]       # Package manifests, configs, etc.
```

### Key Directories
*(Update this section as directories are added)*

- **src/**: Main application source code
- **tests/**: Unit, integration, and e2e tests
- **docs/**: Additional documentation beyond README
- **config/**: Environment and build configurations

---

## Development Workflow

### Branch Strategy

**Main Branch:**
- TBD - Will be established with first commit
- Protected branch requiring review
- Always deployable state

**Feature Branches:**
- Pattern: `feature/<descriptive-name>`
- Created from main branch
- Merged via pull requests

**AI-Assisted Development Branches:**
- Pattern: `claude/claude-md-<session-id>`
- Automatically created for AI development sessions
- Should be merged or cleaned up after task completion

### Workflow Steps

1. **Start New Feature:**
   ```bash
   git checkout -b feature/feature-name
   ```

2. **Development:**
   - Make incremental commits
   - Write tests alongside code
   - Update documentation as needed

3. **Before Committing:**
   - Run tests
   - Check code style/linting
   - Review changes

4. **Create Pull Request:**
   - Provide clear description
   - Reference related issues
   - Ensure CI passes

---

## Git Conventions

### Commit Messages

Follow the Conventional Commits specification:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, no logic change)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks
- `perf`: Performance improvements
- `ci`: CI/CD changes

**Examples:**
```
feat(auth): add user authentication system

Implements JWT-based authentication with refresh tokens.
Includes login, logout, and token refresh endpoints.

Closes #123
```

```
fix(api): resolve race condition in data fetching

Added proper locking mechanism to prevent concurrent
access issues when multiple requests arrive simultaneously.
```

### Branch Naming

- `feature/user-authentication`
- `fix/login-validation-bug`
- `docs/update-api-documentation`
- `refactor/simplify-data-layer`

---

## Code Conventions

### General Principles

1. **Clarity over Cleverness:** Write code that's easy to understand
2. **DRY (Don't Repeat Yourself):** Extract common logic
3. **SOLID Principles:** Follow object-oriented design principles
4. **Separation of Concerns:** Keep modules focused and independent
5. **Error Handling:** Always handle errors gracefully
6. **Security First:** Never commit secrets, sanitize inputs, validate data

### Language-Specific Conventions
*(To be added based on project language)*

**Example for JavaScript/TypeScript:**
- Use meaningful variable names
- Prefer `const` over `let`, avoid `var`
- Use async/await over raw promises
- Always use semicolons
- Maximum line length: 100 characters
- Use TypeScript strict mode

**Example for Python:**
- Follow PEP 8 style guide
- Use type hints
- Docstrings for all public functions/classes
- Maximum line length: 88 characters (Black formatter)

### File Naming

- Use lowercase with hyphens for files: `user-service.js`
- Match file name to primary export: `UserService` → `user-service.js`
- Test files: `user-service.test.js` or `user-service.spec.js`

---

## AI Assistant Guidelines

### Core Responsibilities

1. **Understand Context First:**
   - Always read relevant files before making changes
   - Use Task tool with Explore agent for codebase exploration
   - Don't assume - verify by reading actual code

2. **Plan Before Acting:**
   - Use TodoWrite tool for multi-step tasks
   - Break down complex tasks into manageable steps
   - Keep user informed of progress

3. **Write Quality Code:**
   - Follow existing patterns and conventions
   - Add appropriate error handling
   - Include comments for complex logic
   - Write/update tests for new features

4. **Security Awareness:**
   - Never expose sensitive data
   - Validate and sanitize all inputs
   - Avoid common vulnerabilities (XSS, SQL injection, etc.)
   - Use parameterized queries
   - Implement proper authentication/authorization

5. **Documentation:**
   - Update CLAUDE.md when project structure changes
   - Keep README.md current
   - Add inline documentation for complex code
   - Update API documentation

### Task Workflow for AI Assistants

```
1. Receive task → Use TodoWrite to create task breakdown
2. Explore codebase → Use Task tool with Explore agent
3. Read relevant files → Use Read tool
4. Make changes → Use Edit/Write tools
5. Test changes → Run tests, verify functionality
6. Update documentation → Update relevant docs
7. Commit → Create meaningful commit message
8. Push → Push to designated branch
9. Mark complete → Update todos as completed
```

### Best Practices

**DO:**
- ✓ Read files before editing them
- ✓ Use specialized tools (Read, Edit) over bash commands
- ✓ Run tests after making changes
- ✓ Update this CLAUDE.md when structure changes
- ✓ Ask clarifying questions when requirements are unclear
- ✓ Mark todos in_progress before starting, completed when done
- ✓ Make atomic commits with clear messages

**DON'T:**
- ✗ Make changes without understanding existing code
- ✗ Skip tests
- ✗ Commit without descriptive messages
- ✗ Push directly to main branch
- ✗ Hardcode secrets or credentials
- ✗ Use bash for file operations (use Read/Edit/Write instead)
- ✗ Create files unnecessarily (prefer editing existing files)

### Common Patterns

**Exploring Unknown Codebase:**
```
1. Use Task tool with Explore agent to understand structure
2. Look for main entry points (main.js, index.js, __main__.py, etc.)
3. Read configuration files (package.json, requirements.txt, etc.)
4. Examine test files to understand expected behavior
5. Check for existing documentation
```

**Adding New Feature:**
```
1. Create TodoWrite task list
2. Research similar existing features
3. Design the solution
4. Implement core functionality
5. Add error handling
6. Write tests
7. Update documentation
8. Commit and push
```

**Fixing Bugs:**
```
1. Reproduce the issue
2. Locate the problematic code
3. Understand root cause
4. Implement fix
5. Add regression test
6. Verify fix works
7. Commit with clear description
```

---

## Testing Strategy

### Testing Principles
*(To be updated based on project needs)*

1. **Test Coverage:** Aim for high coverage (>80%)
2. **Test Types:**
   - Unit tests: Test individual functions/components
   - Integration tests: Test module interactions
   - E2E tests: Test full user workflows

3. **Testing Best Practices:**
   - Write tests before or alongside code (TDD)
   - Test both happy paths and error cases
   - Use meaningful test descriptions
   - Keep tests independent and isolated
   - Mock external dependencies

### Running Tests
*(Update with actual commands once established)*

```bash
# Run all tests
npm test  # or pytest, cargo test, etc.

# Run specific test file
npm test user-service.test.js

# Run with coverage
npm test -- --coverage

# Watch mode for development
npm test -- --watch
```

---

## Documentation Standards

### Code Comments

**When to Comment:**
- Complex algorithms or business logic
- Non-obvious design decisions
- Workarounds or gotchas
- Public APIs and interfaces

**When NOT to Comment:**
- Obvious code (don't state the obvious)
- Instead of fixing bad code (refactor instead)

**Example:**
```javascript
// GOOD: Explains WHY
// Use exponential backoff to avoid overwhelming the API
// during high traffic periods
await retryWithBackoff(apiCall, { maxAttempts: 3 });

// BAD: Explains WHAT (code already shows this)
// Set x to 5
const x = 5;
```

### Function/Method Documentation

Include:
- Purpose/description
- Parameters with types
- Return value
- Exceptions/errors thrown
- Usage example (if complex)

**Example (JSDoc):**
```javascript
/**
 * Fetches user data from the API with retry logic
 *
 * @param {string} userId - The unique identifier for the user
 * @param {Object} options - Configuration options
 * @param {number} options.timeout - Request timeout in milliseconds
 * @returns {Promise<User>} The user object
 * @throws {UserNotFoundError} If user doesn't exist
 * @throws {NetworkError} If request fails after retries
 *
 * @example
 * const user = await fetchUser('123', { timeout: 5000 });
 */
async function fetchUser(userId, options = {}) {
  // Implementation
}
```

---

## Common Tasks

### Initial Project Setup
*(For when the project tech stack is determined)*

```bash
# Clone repository
git clone <repo-url>
cd ErisReborn

# Install dependencies
# npm install  # Node.js
# pip install -r requirements.txt  # Python
# cargo build  # Rust
# etc.

# Run tests
# npm test

# Start development server
# npm run dev
```

### Adding Dependencies
*(Update based on package manager)*

```bash
# Add production dependency
npm install <package>

# Add development dependency
npm install -D <package>

# Update package after adding
# Update package.json and lock files
git add package.json package-lock.json
git commit -m "deps: add <package> for <reason>"
```

### Database Migrations
*(If applicable - update when database is added)*

```bash
# Create migration
# npm run migrate:create <migration-name>

# Run migrations
# npm run migrate:up

# Rollback migration
# npm run migrate:down
```

---

## Project-Specific Notes

### Technology Stack
*(To be updated once technologies are chosen)*

- **Language:** TBD
- **Framework:** TBD
- **Database:** TBD
- **Testing Framework:** TBD
- **Build Tool:** TBD
- **CI/CD:** TBD

### Architecture Patterns
*(To be documented as project develops)*

- Architecture style (MVC, Clean Architecture, Microservices, etc.)
- Design patterns in use
- External services and integrations

### Environment Variables
*(Document required environment variables)*

```bash
# Example:
# DATABASE_URL=postgresql://localhost/erisreborn
# API_KEY=your-api-key
# NODE_ENV=development|production
```

### Known Issues and Gotchas
*(Document any quirks or known issues)*

- None yet (new project)

---

## Updating This Document

This CLAUDE.md file should be updated whenever:
- Project structure changes significantly
- New conventions or patterns are established
- New tools or technologies are added
- Development workflow changes
- New team members or AI assistants need onboarding

**AI Assistants:** When you make structural changes to the project, please update the relevant sections of this document.

---

## Resources

### Internal Documentation
- README.md (to be created)
- API Documentation (to be created)
- Architecture Diagrams (to be created)

### External Resources
*(Add links to relevant external documentation)*
- [Git Conventional Commits](https://www.conventionalcommits.org/)
- [Semantic Versioning](https://semver.org/)
- Technology-specific documentation (to be added)

---

## Contact and Support

For questions about this codebase:
- Create an issue in the repository
- Contact project maintainers
- Review existing documentation

---

**Note to AI Assistants:** This document is your primary reference for working with the ErisReborn codebase. Always consult this file before making significant changes. When in doubt, ask the user for clarification rather than making assumptions.

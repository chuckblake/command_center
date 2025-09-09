# AI-Friendly Documentation Plan

## Step 1: Analyze the Project
Explore the codebase to understand:

- Project type (web app, API, library, CLI tool, etc.)
- Technology stack and frameworks
- Directory structure
- Key business domains
- External integrations
- Testing approach
- Development workflow

---

## Step 2: Create `CLAUDE.md`
Create a `CLAUDE.md` file in the project root that serves as the AI assistant's entry point. Include:

- Greeting instruction (e.g., `🚀 CLAUDE.MD LOADED`)
- Project overview (what it does, who uses it, core workflow)
- Your role definition for the AI
- Common tasks quick reference (5–10 most frequent development tasks)
- Essential commands (setup, test, lint, deploy)
- Core architecture principles
- Link to detailed documentation in `/docs/ai/`
- Any project-specific instructions or constraints

---

## Step 3: Create Documentation Structure
Directory layout:  

	docs/ai/
	├── 00-index.md          # Navigation hub and project overview
	├── 01-overview.md       # Business context and user flows
	├── 02-architecture.md   # System design and tech stack
	├── 03-conventions.md    # Coding standards and patterns
	├── 04-runbook-dev.md    # Development commands and workflow
	├── 05-testing.md        # Testing guidelines and structure
	├── 06-security.md       # Auth, authorization, data protection
	├── 07-glossary.md       # Domain terminology
	├── domains/             # Deep dives into business domains
	│   ├── [domain1].md     # e.g., users, payments, etc.
	│   ├── [domain2].md
	│   └── ...
	├── adr/                 # Architecture Decision Records
	│   ├── 0001-[decision].md
	│   └── ...
	├── prompts/             # AI development patterns
	│   └── development-partner.md
	└── workflows/           # Process documentation
	    └── project-management.md

---

## Step 4: Document Content Guidelines

### `00-index.md` should include:
- Project purpose (one sentence)
- Core subsystems list
- Technology stack details
- External integrations
- Key directories with descriptions
- Navigation links to other docs

### Domain files should cover:
- Overview
- Core models/entities
- Key services/business logic
- API endpoints (if applicable)
- Database schemas
- Common operations
- Testing patterns

### Architecture docs should include:
- System boundaries
- Data flow diagrams (as text/ASCII)
- Infrastructure components
- Deployment architecture
- Performance considerations

---

## Step 5: Code-Level Documentation
For key directories (`models`, `services`, `controllers`, etc.), add `README.md` files explaining:

- Directory purpose
- Common patterns used
- Naming conventions
- Examples of proper implementation

---

## Step 6: Integration Points
Document external services in appropriate locations:

- API integrations
- Third-party libraries
- Environment variables
- Configuration requirements

---

## Output Requirements
- Start by exploring the codebase thoroughly
- Create all files with proper markdown formatting
- Use code examples from the actual codebase
- Include file paths in documentation (e.g., `app/models/user.rb`)
- Add cross-references between related documentation
- Keep descriptions concise but comprehensive
- Focus on what AI assistants need to know to be effective

---

## Special Instructions
- Analyze the project’s `README` first if it exists
- Incorporate existing documentation if present
- Check for configuration files (`package.json`, `Gemfile`, `requirements.txt`, etc.)
- Identify the testing framework and document test patterns
- Note any CI/CD configuration
- Document environment setup requirements
- Include common troubleshooting scenarios

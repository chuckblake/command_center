# System Review Prompt 

You are conducting a comprehensive technical review of the LEA Rails application system health and architecture.

## CRITICAL REQUIREMENTS

**FACTUAL ACCURACY ONLY**: 
- Base ALL findings and statements ONLY on actual code analysis and the provided notes file
- DO NOT make assumptions, inferences, or add information not explicitly found in the source code or notes
- If information is not available in the code or notes, explicitly state "Information not available" or omit the section
- DO NOT speculate about functionality, performance, or implementation details
- When in doubt, err on the side of omission rather than inclusion

**SOURCE-BASED ANALYSIS**:
- Every statement must be traceable to specific code files, lines, or the notes document
- Quote directly from source code when describing functionality
- Reference specific file paths and line numbers when discussing implementation details
- Use exact language from the notes file when describing system status

## Instructions

1. **Read the notes file**: Review `docs/command_center/system_review/system_review_notes.md` for current system status and specific concerns
2. **Find the most recent previous report**: Locate the most recent system review in `app/views/command_center/system_review/` (sort by filename date)
3. **Review release notes since last update**: Check `db/seeds/release_notes.rb` for any release notes or changelog entries since the date of the most recent system review file
4. **Compare with previous report**: Analyze differences between current codebase and the previous report to identify changes
5. **Follow the template**: Use `docs/command_center/system_review/system_review_template.md` as the structure for your report
6. **Analyze system health**: Review all system components, focusing on:
   - Code quality and architecture patterns
   - Infrastructure and deployment processes
   - Database design and performance
   - Background jobs and queue management
   - Security and observability
   - Development workflow and tooling

7. **Generate the report**: Create a comprehensive markdown report following the template structure
8. **Save the output**: Save the final report to `app/views/command_center/system_review/` with a timestamped filename

## Key Areas to Review

### Code Quality & Architecture
- Rails conventions and best practices adherence
- Service object organization and modularity
- Model and controller implementations
- Code duplication and DRY principles
- Test coverage and quality
- Documentation completeness

### Infrastructure & Deployment
- Docker Compose setup for local development
- Heroku production deployment configuration
- CI/CD pipeline automation
- Environment variable management
- Database configuration and connections
- Asset compilation and delivery

### Database Design & Performance
- Schema design and normalization
- Index usage and optimization
- Query performance and N+1 prevention
- Migration patterns and data integrity
- Connection pooling and resource usage
- Backup and recovery procedures

### Background Jobs & Queues
- Que job implementation and patterns
- Error handling and retry mechanisms
- Job monitoring and alerting
- Queue performance and throughput
- Idempotency and concurrency control
- Job scheduling and dependencies

### Security & Observability
- Authentication and authorization (Devise/Pundit)
- Input validation and strong parameters
- API security and rate limiting
- Logging and monitoring setup
- Error tracking and alerting
- Data encryption and protection

### Development Workflow
- Testing framework and coverage
- Code review and quality gates
- Documentation and onboarding
- Development environment setup
- Debugging and troubleshooting tools
- Performance profiling and optimization

## Key Changes Analysis

When comparing with the previous report, focus on:

### Release Notes Analysis
- Review all release notes in `db/seeds/` since the date of the most recent system review
- Identify any system-related changes, bug fixes, or new features mentioned
- Note any breaking changes or deprecations that affect system architecture
- Include relevant release note information in the comparison section

### Database Changes
- Check for new migrations in `db/migrate/` since last review
- Analyze schema changes and their impact on performance
- Review new indexes, constraints, or data modifications
- Identify any data migration patterns or concerns

### Code Quality Changes
- Compare file counts and sizes in key directories
- Look for new service objects or architectural patterns
- Check for refactoring or code organization improvements
- Review test coverage changes and new test patterns

### Infrastructure Updates
- Check for changes in Docker configuration
- Review CI/CD pipeline modifications
- Analyze deployment process improvements
- Identify new environment variables or configuration changes

### Security Enhancements
- Look for new authentication or authorization patterns
- Check for encryption or security hardening
- Review input validation improvements
- Analyze error handling and logging enhancements

### Performance Improvements
- Check for new caching strategies
- Review database query optimizations
- Analyze job processing improvements
- Identify monitoring and alerting enhancements

### Resolved Issues
- Check if previously identified TODOs or blockers have been addressed
- Look for new error handling or retry mechanisms
- Verify if known issues from previous report are still present

### New Issues
- Identify any new problems or limitations discovered in current analysis
- Note any regressions or new technical debt
- Flag any security or performance concerns

### Status Changes
- Compare system health status with previous assessment
- Note any improvements or degradations in system quality
- Identify any architectural changes or new patterns

## Factual Reporting Guidelines

- **Status Assessment**: Only report status based on actual code presence and notes file information
- **Feature Lists**: Only include features that are explicitly implemented in the code
- **Known Issues**: Only include issues mentioned in the notes file or evident from code analysis
- **Architecture**: Describe only what is actually present in the codebase
- **Dependencies**: List only dependencies that are actually imported or used in the code
- **Test Coverage**: Report only on test files that actually exist
- **Changes**: Only report changes that can be verified by comparing current code with previous report

## Output Format

Generate a markdown file with the current date prefix: `YYYY-MM-DD-SystemReview.md`

The report should follow the exact structure of the template, with all sections completed based on factual analysis of the codebase and notes file.

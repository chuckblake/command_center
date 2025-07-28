---
description: Apply this rule when the LLM is creating an implementation plan for a coding request. 
alwaysApply: false
---
# Implementation Notes Prompt Template

Use this prompt template to generate comprehensive implementation notes for your projects. This template ensures consistent formatting, proper file naming, and complete documentation coverage.

## Prompt Template

```
You are tasked with creating comprehensive implementation notes for a completed feature or enhancement. Follow these guidelines exactly:

## File Naming Convention
- Use YYYY-MM-DD format for the date prefix
- Follow the pattern: YYYY-MM-DD-feature_name_implementation.md
- Example: 2025-07-14-document_validation_results_implementation.md
- Always save in docs/implementation_notes/ directory by default

## Content Structure
Your implementation notes must include the following sections:

### 1. Title and Overview
- Clear, descriptive title with issue/ticket number if applicable
- Brief overview of what was implemented
- Key objectives and goals achieved

### 2. Requirements Met
- List all acceptance criteria with ✅ checkmarks for completed items
- Include both functional and non-functional requirements
- Highlight any requirements that were modified or deferred

### 3. Technical Implementation
- Detailed breakdown of the implementation approach
- Key technical decisions and rationale
- Architecture and design patterns used
- Integration points with existing systems

### 4. Core Components Created/Modified
- List all new files created
- List all existing files modified
- Include brief description of each component's purpose
- Organize by type (controllers, models, services, views, tests, etc.)

### 5. Test Coverage
- Comprehensive test strategy implemented
- Types of tests written (unit, integration, feature, etc.)
- Test coverage metrics if available
- Any testing challenges or solutions

### 6. Features and Functionality
- Detailed list of implemented features
- User-facing functionality
- Administrative or backend features
- Configuration options and settings

### 7. Integration Points
- How the feature integrates with existing systems
- API endpoints created or modified
- Database changes and migrations
- External service integrations

### 8. Usage Instructions
- Step-by-step guide for using the feature
- User interface navigation
- Configuration requirements
- Troubleshooting tips

### 9. Files Created/Modified
- Complete list organized by category:
  - New Files: [list with brief descriptions]
  - Modified Files: [list with brief descriptions]
- Include file paths and purposes

### 10. Future Enhancements
- Potential improvements or extensions
- Technical debt considerations
- Scalability considerations
- User feedback integration opportunities

## Writing Style Guidelines
- Use clear, concise language
- Include code examples where relevant
- Use bullet points and numbered lists for clarity
- Include technical details but remain accessible
- Focus on the "why" and "how" not just the "what"
- Use consistent formatting throughout

## Quality Checklist
Before finalizing, ensure your implementation notes include:
- [ ] Proper YYYY-MM-DD filename format
- [ ] All acceptance criteria addressed
- [ ] Complete file listing (created and modified)
- [ ] Test coverage documentation
- [ ] Usage instructions
- [ ] Technical implementation details
- [ ] Integration points documented
- [ ] Future enhancement considerations

## Example Structure
```
# Feature Name Implementation - ISSUE-XXX

## Overview
Brief description of what was implemented and why.

## Requirements Met
### ✅ Acceptance Criteria Implemented
- [Requirement 1]
- [Requirement 2]

### ✅ Technical Implementation
1. [Technical detail 1]
2. [Technical detail 2]

## Core Components Created

### Service Layer
- [Service description]

### Controller & Routes
- [Controller details]

### Views
- [View details]

## Test Coverage
### ✅ Tests Created
1. [Test type 1]
2. [Test type 2]

## Files Created/Modified

### New Files
- `path/to/file.rb` - [description]

### Modified Files
- `path/to/file.rb` - [description]

## Usage
1. [Step 1]
2. [Step 2]

## Future Enhancements
- [Enhancement 1]
- [Enhancement 2]

---

*Implementation completed following TDD methodology with comprehensive test coverage.*
```

## Additional Notes
- Always use the current system date for the filename
- Include issue/ticket numbers when available
- Reference any relevant documentation or specifications
- Consider the audience (developers, stakeholders, future maintainers)
- Keep implementation notes focused and actionable
- Update notes if requirements change during implementation

This template ensures consistent, comprehensive documentation that serves both technical and business stakeholders.
```

## Usage Instructions

1. Copy the prompt template above
2. Replace the placeholder text with your specific feature details
3. Follow the structure exactly as outlined
4. Ensure all sections are completed
5. Save the file with the proper YYYY-MM-DD naming convention
6. Place in your project's `docs/implementation_notes/` directory

## Benefits

- **Consistency**: All implementation notes follow the same structure
- **Completeness**: Ensures no important details are missed
- **Maintainability**: Future developers can quickly understand what was built
- **Traceability**: Links implementation to requirements and tests
- **Knowledge Transfer**: Facilitates onboarding and handoffs

## Customization

Feel free to adapt this template to your specific project needs:
- Add project-specific sections
- Modify the file naming convention if needed
- Include additional quality checkpoints
- Add links to external documentation or tools 

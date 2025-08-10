# Integration Review Prompt

You are conducting a comprehensive review of all integrations in the LEA Rails application.

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
- Use exact language from the notes file when describing integration status
- **INCORPORATE ALL NOTES CONTENT**: All information from the notes file must be included in the final report - do not omit any sections, status updates, or details from the notes document
- **CRITICAL**: Every section, URL, credential, note, and detail from the notes file must be explicitly included in the appropriate integration section of the report

## Instructions

1. **Read the notes file**: Review `docs/command_center/integrations/integrations_notes.md` for current integration status and specific concerns. **CRITICAL**: Every piece of information in this file must be included in the final report - URLs, credentials, notes, TODOs, and all details.
2. **Find the most recent previous report**: Locate the most recent integration review in `app/views/command_center/integrations/` (sort by filename date)
3. **Review release notes since last update**: Check `db/seeds/release_notes.rb` for any release notes or changelog entries since the date of the most recent integration review file
4. **Compare with previous report**: Analyze differences between current codebase and the previous report to identify changes
5. **Follow the template**: Use `docs/command_center/integrations/integrations_template.md` as the structure for your report
6. **Analyze integrations**: Review all integration-related code, focusing on:
   - External API integrations (Linear, Egnyte, Box, etc.)
   - OAuth implementations
   - File processing and storage integrations
   - Background job integrations
   - Third-party service integrations

7. **Generate the report**: Create a comprehensive markdown report following the template structure
8. **Save the output**: Save the final report to `app/views/command_center/integrations/` with a timestamped filename

## Key Areas to Review

- Integration service objects and their organization
- Error handling and retry mechanisms
- API rate limiting and throttling
- Authentication and authorization for external services
- Data synchronization patterns
- Monitoring and logging for integrations
- Security considerations for external API usage
- Performance impact of integrations
- Test coverage for integration code
- Documentation of integration endpoints and usage

## Key Changes Analysis

When comparing with the previous report, focus on:

### Release Notes Analysis
- Review all release notes in `db/seeds/` since the date of the most recent integration review
- Identify any integration-related changes, bug fixes, or new features mentioned
- Note any breaking changes or deprecations that affect integrations
- Include relevant release note information in the comparison section

### New Integrations
- Check for new integration directories in `app/services/integrations/`
- Look for new OAuth controllers in `app/controllers/integrations/`
- Identify any new service objects or workflow integrations

### Updated Integrations
- Compare file counts and sizes in integration directories
- Look for new service methods or enhanced functionality
- Check for changes in OAuth implementation or error handling
- Review any new workflow steps or job integrations

### Resolved Issues
- Check if previously identified TODOs or blockers have been addressed
- Look for new error handling or retry mechanisms
- Verify if known issues from previous report are still present

### New Issues
- Identify any new problems or limitations discovered in current analysis
- Note any regressions or new technical debt
- Flag any security or performance concerns

### Status Changes
- Compare integration status (Complete/Partial/Stub/Deprecated)
- Note any changes in feature completeness
- Identify any integrations that have moved forward or backward in development

## Factual Reporting Guidelines

- **Status Assessment**: Only report status based on actual code presence and notes file information
- **Feature Lists**: Only include features that are explicitly implemented in the code
- **Known Issues**: Only include issues mentioned in the notes file or evident from code analysis
- **Architecture**: Describe only what is actually present in the codebase
- **Dependencies**: List only dependencies that are actually imported or used in the code
- **Test Coverage**: Report only on test files that actually exist
- **Changes**: Only report changes that can be verified by comparing current code with previous report
- **Notes File Compliance**: **MANDATORY** - Every integration section in the notes file must have a corresponding detailed section in the report, including all URLs, credentials, TODOs, and operational notes

## Output Format

Generate a markdown file with the current date prefix: `YYYY-MM-DD-integrations.md`
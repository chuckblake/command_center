# Test Coverage Review Prompt

You are conducting a comprehensive test coverage review of the LEA Rails application with a primary focus on model and service test coverage, test quality, and critical business logic testing.

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
- Use exact language from the notes file when describing test coverage status

## Instructions

1. **Read the notes file**: Review `docs/command_center/test_coverage_review/test_coverage_notes.md` for specific test coverage information, concerns, and priorities documented by developers
2. **Find the most recent previous report**: Locate the most recent test coverage review in `app/views/command_center/test_coverage_review/` (sort by filename date)
3. **Review release notes since last update**: Check `db/seeds/release_notes.rb` for any test-related release notes or changelog entries since the date of the most recent test coverage review file
4. **Compare with previous report**: Analyze differences between current codebase and the previous report to identify test coverage changes
5. **Follow the template**: Use `docs/command_center/test_coverage_review/test_coverage_review_template.md` as the structure for your report
6. **Analyze test coverage**: Review all test-related code, focusing on:
   - Model test coverage (validations, associations, scopes, methods, callbacks, enums)
   - Service test coverage (happy path, error handling, edge cases, dependencies)
   - Factory and test data quality
   - Controller and request test coverage
   - Background job test coverage
   - Integration and end-to-end test coverage
   - Test performance and optimization
   - Test quality and maintainability

7. **Generate the report**: Create a comprehensive markdown report following the template structure
8. **Save the output**: Save the final report to `app/views/command_center/test_coverage_review/` with a timestamped filename

## 🧪 Primary Focus Areas

### 1. Model Test Coverage - CRITICAL
- **Validations**: Are all validations tested (presence, uniqueness, format, length, inclusion, exclusion)?
- **Associations**: Are all belongs_to, has_many, has_one, has_and_belongs_to_many relationships tested?
- **Scopes**: Are all custom scopes tested, including success and failure scenarios?
- **Instance/Class Methods**: Are custom methods tested, including edge cases and logic branches?
- **Callbacks**: Are before_*, after_*, and around_* callbacks tested?
- **Custom Validations**: Are custom validation methods tested?
- **Enums**: Are all enum behaviors tested?
- **Nested Attributes**: If using accepts_nested_attributes_for, are those tested?

### 2. Service Test Coverage - CRITICAL
- **Happy Path**: Is the primary execution path covered by tests?
- **Error Handling**: Are exceptions and error conditions tested?
- **Edge Cases**: Are boundary/atypical input scenarios tested?
- **Dependencies**: Are external services (APIs, other services) mocked or stubbed appropriately?
- **Return Values**: Are all expected outcomes tested?
- **Side Effects**: Are database changes, API calls, or other side effects tested?
- **Input Validation**: Are invalid or missing parameters tested?
- **Business Logic**: Are all business rules and decision points exercised in tests?

### 3. Critical Business Logic Testing
- **Complex Models**: Models with complex logic, callbacks, or metaprogramming
- **Financial Data**: Models handling sensitive financial or critical data
- **Authentication/Authorization**: Security-related model and service coverage
- **External Integrations**: API and third-party service test coverage

### 4. Test Quality and Performance
- **Test Isolation**: Test independence and proper mocking/stubbing
- **Test Maintainability**: Test readability and DRY principles
- **Test Performance**: Slow tests and optimization opportunities
- **Factory Quality**: Factory definitions and usage patterns

## Key Areas to Review

### Models and Test Coverage
- Scan all models in `app/models/` for test coverage gaps
- Check validation test coverage using `shoulda-matchers` or similar patterns
- Identify missing association, scope, and method tests
- Review callback and enum test coverage

### Services and Test Coverage
- Review all services in `app/services/` for comprehensive test coverage
- Check error handling and edge case testing
- Review dependency mocking and stubbing patterns
- Assess business logic test coverage

### Controllers and Request Testing
- Review controller action test coverage
- Check authorization and parameter testing
- Review response format and status testing
- Assess error handling test coverage

### Background Jobs and Async Testing
- Review job execution test coverage
- Check error handling and retry logic testing
- Review side effect and queue behavior testing
- Assess job failure scenario testing

### Integration and End-to-End Testing
- Review user journey and workflow testing
- Check service integration testing
- Review API endpoint testing
- Assess cross-service interaction testing

### Factory and Test Data Quality
- Review factory definitions and completeness
- Check factory usage patterns in tests
- Review test data quality and realism
- Assess factory association and trait usage

## 🚨 Critical Red Flags - ALWAYS FLAG

### CRITICAL RISK
- Models with complex business logic and no test coverage
- Financial data models without comprehensive testing
- Authentication/authorization models with missing tests
- External API services without proper mocking/stubbing

### HIGH RISK
- Services with error handling but no error tests
- Models with callbacks but no callback tests
- Controllers with authorization but no authorization tests
- Background jobs without failure scenario testing

### MEDIUM RISK
- Missing validation tests for critical fields
- Poor test isolation and cleanup
- Slow tests affecting development velocity
- Code duplication in test files

## Key Changes Analysis

When comparing with the previous report, focus on:

### Release Notes Analysis
- Review all release notes in `db/seeds/` since the date of the most recent test coverage review
- Identify any test-related changes, bug fixes, or new features mentioned
- Note any test coverage improvements or new testing requirements
- Include relevant test-related release note information in the comparison section

### New Test Coverage Requirements
- Check for new models or services added without tests
- Look for new business logic that needs test coverage
- Identify any new external integrations requiring test coverage
- Review new authentication or authorization features needing tests

### Updated Test Coverage
- Compare test coverage status of existing models and services
- Look for enhanced test coverage or new test patterns
- Check for improved test quality or performance
- Review any new test infrastructure or tools

### Resolved Test Coverage Issues
- Check if previously identified test gaps have been addressed
- Look for new test coverage or quality improvements
- Verify if known test coverage issues from previous report are still present

### New Test Coverage Issues
- Identify any new test coverage gaps discovered
- Note any regressions or new test technical debt
- Flag any test quality or performance issues

### Status Changes
- Compare test coverage posture with previous assessment
- Note any changes in coverage levels
- Identify any improvements or degradations in test quality

## Required Output Format

**IMPORTANT**: When generating the final report, DO NOT include the header information from the template that contains file path instructions. The report should start directly with the Executive Summary section.

### Executive Summary
- 2-3 sentence overview with overall test coverage level
- Critical findings summary
- Test quality status overview

### Test Coverage Assessment
- **Complete Model Coverage Table**: List all models with test coverage status
- **Service Coverage Table**: List all services with test coverage status
- **Risk Assessment**: Specific recommendations for test coverage improvements
- **Quality Impact**: Test quality and maintainability implications

### Top 5 Critical Test Coverage Priorities
- Specific actionable items with risk levels
- Implementation timelines
- Resource requirements

### Detailed Findings by Category
- Evidence and code examples for each test coverage type
- Specific file paths and line numbers
- Impact assessment and risk scenarios

### Test Quality and Performance Review
- Test isolation and maintainability analysis
- Performance optimization opportunities
- Factory and test data quality assessment
- Test architecture improvements

### Prioritized Recommendations
- **Immediate** (0-30 days): Critical test coverage gaps
- **Short-term** (1-3 months): High-risk test coverage issues
- **Medium-term** (3-6 months): Medium-risk improvements
- **Long-term** (6+ months): Test quality enhancements

## Factual Reporting Guidelines

- **Test Coverage Assessment**: Only report coverage status based on actual test file presence
- **Coverage Gaps**: Only include gaps that are explicitly found in code analysis
- **Known Issues**: Only include issues mentioned in the notes file or evident from code analysis
- **Test Quality**: Describe only what is actually implemented in the test files
- **Dependencies**: List only test-related dependencies that are actually imported or used
- **Coverage Metrics**: Report only on test files that actually exist
- **Changes**: Only report changes that can be verified by comparing current code with previous report

## Output Format

Generate a markdown file with the current date prefix: `YYYY-MM-DD-TestCoverageReview.md`

**CRITICAL**: The generated report should NOT include any header text about file paths, naming conventions, or instructions. The report should start directly with the Executive Summary section and contain only the actual test coverage analysis content.

## 📂 Files to Analyze

Please review the following directories:

**Models**: `app/models/**/*.rb`
**Services**: `app/services/**/*.rb`
**Model specs**: `spec/models/**/*_spec.rb`
**Service specs**: `spec/services/**/*_spec.rb`
**Controller specs**: `spec/controllers/**/*_spec.rb`
**Request specs**: `spec/requests/**/*_spec.rb`
**Job specs**: `spec/jobs/**/*_spec.rb`
**Factory definitions**: `spec/factories/**/*.rb`
**Shared test helpers and matchers**: `spec/support/**/*.rb`

## 📊 Analysis Requirements

### 1. Model Test Coverage
For each model in `app/models/`, examine:

- **Validations**: Are all validations tested (presence, uniqueness, format, length, inclusion, exclusion)?
- **Associations**: Are all belongs_to, has_many, has_one, has_and_belongs_to_many relationships tested?
- **Scopes**: Are all custom scopes tested, including success and failure scenarios?
- **Instance/Class Methods**: Are custom methods tested, including edge cases and logic branches?
- **Callbacks**: Are before_*, after_*, and around_* callbacks tested?
- **Custom Validations**: Are custom validation methods tested?
- **Enums**: Are all enum behaviors tested?
- **Nested Attributes**: If using accepts_nested_attributes_for, are those tested?
- **Factories**: Is a factory defined for the model (e.g., in FactoryBot)? Is it used correctly in tests?

### 2. Service Test Coverage
For each service in `app/services/`, examine:

- **Happy Path**: Is the primary execution path covered by tests?
- **Error Handling**: Are exceptions and error conditions tested?
- **Edge Cases**: Are boundary/atypical input scenarios tested?
- **Dependencies**: Are external services (APIs, other services) mocked or stubbed appropriately?
- **Return Values**: Are all expected outcomes tested?
- **Side Effects**: Are database changes, API calls, or other side effects tested?
- **Input Validation**: Are invalid or missing parameters tested?
- **Business Logic**: Are all business rules and decision points exercised in tests?

### 3. Test Quality Assessment
- **Test Isolation**: Are tests independent and properly isolated?
- **Test Maintainability**: Are tests readable and follow DRY principles?
- **Test Performance**: Are tests optimized and not unnecessarily slow?
- **Factory Quality**: Are factories comprehensive and well-designed?
- **Mock/Stub Usage**: Are external dependencies properly mocked/stubbed?

### 4. Critical Business Logic Testing
- **Complex Models**: Models with complex logic, callbacks, or metaprogramming
- **Financial Data**: Models handling sensitive financial or critical data
- **Authentication/Authorization**: Security-related model and service coverage
- **External Integrations**: API and third-party service test coverage

## 🧠 High-Risk Areas
Flag any model or service that:

- Contains complex logic, callbacks, or metaprogramming
- Is business-critical (e.g., billing, access control, data sync)
- Has little to no test coverage
- Handles sensitive data (PII, financial information)
- Integrates with external APIs or services

## ✅ Recommendations
**Priority 1 (Critical)**: [Highest risk gaps that could cause regressions or outages]
**Priority 2 (Important)**: [Key logic not yet tested, but with less immediate risk]
**Priority 3 (Nice to have)**: [Low-risk or less central gaps]

## 🧪 Suggested RSpec Examples
For the highest priority gaps, provide 2–3 idiomatic RSpec test examples. Use:

- `describe`, `context`, and `it` blocks
- `let`, `subject`, and test doubles where appropriate
- Clear test names and expectations

Example:
```ruby
describe '#cancel!' do
  context 'when the order is already shipped' do
    it 'raises an InvalidTransition error' do
      expect { order.cancel! }.to raise_error(Order::InvalidTransition)
    end
  end
end
```
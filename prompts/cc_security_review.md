# Security Review Prompt

You are conducting a comprehensive security review of the LEA Rails application with a primary focus on PII encryption and OWASP Top 10 vulnerabilities.

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
- Use exact language from the notes file when describing security status

## Instructions

1. **Read the notes file**: Review `docs/command_center/security_review/security_review_notes.md` for current security status and specific concerns
2. **Find the most recent previous report**: Locate the most recent security review in `app/views/command_center/security_review/` (sort by filename date)
3. **Review release notes since last update**: Check `db/seeds/release_notes.rb` for any security-related release notes or changelog entries since the date of the most recent security review file
4. **Compare with previous report**: Analyze differences between current codebase and the previous report to identify security changes
5. **Follow the template**: Use `app/views/command_center/security_review/security_review_template.md` as the structure for your report
6. **Analyze security posture**: Review all security-related code, focusing on:
   - PII encryption status across all models
   - Authentication and authorization patterns
   - OWASP Top 10 vulnerabilities
   - Data protection and privacy measures
   - API security and input validation
   - Session management and CSRF protection

7. **Generate the report**: Create a comprehensive markdown report following the template structure
8. **Save the output**: Save the final report to `app/views/command_center/security_review/` with a timestamped filename

## 🔒 Primary Focus Areas

### 1. PII Encryption Review - CRITICAL
- **Social Security Numbers**: Are SSN fields (ss_num, spouse_ss_num) encrypted?
- **Personal Information**: Are DOB, email, phone, address fields encrypted?
- **Financial Data**: Are income fields (annual_income, adjusted_gross_income) encrypted?
- **Document Data**: Are document parsing results and OCR data encrypted?

### 2. OWASP Top 10 Vulnerabilities
- Broken Access Control
- Cryptographic Failures
- Injection (SQL, XSS, etc.)
- Insecure Design
- Security Misconfiguration
- Vulnerable and Outdated Components
- Authentication and Identification Failures
- Software and Data Integrity Failures
- Security Logging and Monitoring Failures
- Server-Side Request Forgery (SSRF)

### 3. Authentication & Authorization
- Devise implementation security
- Pundit policy coverage
- Role-based access control
- Session management
- Password policies

### 4. Data Protection & Privacy
- GDPR/CCPA compliance
- Data retention policies
- Data export/deletion capabilities
- Audit logging

## Key Areas to Review

### Models and PII Fields
- Scan all models in `app/models/` for PII-containing fields
- Check encryption status using `has_encrypted` or similar patterns
- Identify unencrypted sensitive data fields
- Review data validation and sanitization

### Controllers and API Security
- Input validation and sanitization
- Strong parameters implementation
- CSRF protection
- Rate limiting
- Error handling (information disclosure)

### Authentication & Authorization
- Devise configuration in `config/initializers/`
- Pundit policies in `app/policies/`
- Admin constraints and access controls
- Session configuration

### External Integrations Security
- API key management
- OAuth implementation security
- Third-party service authentication
- Data transmission security

### Background Jobs and Services
- Sensitive data handling in jobs
- Service object security
- Queue security and access controls

### Database and Storage Security
- Database encryption at rest
- ActiveStorage security
- Backup encryption
- Connection security

## 🚨 Critical Red Flags - ALWAYS FLAG

### CRITICAL RISK
- SSNs in plain text
- Unencrypted financial data
- Unencrypted personal addresses
- Missing authentication on endpoints
- SQL injection vulnerabilities
- XSS vulnerabilities

### HIGH RISK
- Unencrypted DOB/email fields
- Weak password policies
- Missing CSRF protection
- Insecure session management
- Unvalidated file uploads

### MEDIUM RISK
- Missing rate limiting
- Insecure error handling
- Outdated dependencies
- Insufficient logging

## Key Changes Analysis

When comparing with the previous report, focus on:

### Release Notes Analysis
- Review all release notes in `db/seeds/` since the date of the most recent security review
- Identify any security-related changes, bug fixes, or new features mentioned
- Note any security patches or vulnerability fixes
- Include relevant security release note information in the comparison section

### New Security Features
- Check for new encryption implementations
- Look for new authentication methods
- Identify any new security policies or constraints
- Review new security-related gems or dependencies

### Updated Security Measures
- Compare encryption status of PII fields
- Look for enhanced authentication or authorization
- Check for improved input validation
- Review any new security monitoring or logging

### Resolved Security Issues
- Check if previously identified vulnerabilities have been addressed
- Look for new security controls or mitigations
- Verify if known security issues from previous report are still present

### New Security Issues
- Identify any new vulnerabilities or security gaps discovered
- Note any regressions or new security technical debt
- Flag any compliance issues or privacy concerns

### Status Changes
- Compare security posture with previous assessment
- Note any changes in risk levels
- Identify any improvements or degradations in security measures

## Required Output Format

### Executive Summary
- 2-3 sentence overview with overall risk level
- Critical findings summary
- Compliance status overview

### PII Encryption Assessment
- **Complete PII Inventory Table**: List all models with encrypted vs unencrypted fields
- **PII Level Classification**: Critical/High/Medium/Low for each field
- **Risk Assessment**: Specific recommendations for encryption improvements
- **Compliance Impact**: GDPR/CCPA implications

### Top 5 Critical Security Priorities
- Specific actionable items with risk levels
- Implementation timelines
- Resource requirements

### Detailed Findings by OWASP Category
- Evidence and code examples for each vulnerability type
- Specific file paths and line numbers
- Impact assessment and exploit scenarios

### Authentication & Authorization Review
- Devise configuration analysis
- Pundit policy coverage assessment
- Access control effectiveness
- Session security analysis

### Data Protection & Privacy Assessment
- GDPR/CCPA compliance status
- Data retention and deletion capabilities
- Audit logging implementation
- Data export functionality

### Prioritized Recommendations
- **Immediate** (0-30 days): Critical vulnerabilities
- **Short-term** (1-3 months): High-risk issues
- **Medium-term** (3-6 months): Medium-risk improvements
- **Long-term** (6+ months): Security enhancements

## Factual Reporting Guidelines

- **PII Assessment**: Only report encryption status based on actual code presence
- **Vulnerability Lists**: Only include vulnerabilities that are explicitly found in code analysis
- **Known Issues**: Only include issues mentioned in the notes file or evident from code analysis
- **Security Controls**: Describe only what is actually implemented in the codebase
- **Dependencies**: List only security-related dependencies that are actually imported or used
- **Test Coverage**: Report only on security test files that actually exist
- **Changes**: Only report changes that can be verified by comparing current code with previous report

## Output Format

Generate a markdown file with the current date prefix: `YYYY-MM-DD-security_review.md`

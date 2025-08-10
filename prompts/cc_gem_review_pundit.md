# Pundit Gem Maintenance Review Prompt

You are conducting a maintenance-focused review of the Pundit Rails gem to assess operational risks and provide actionable integration guidance.

## CRITICAL REQUIREMENTS

**MAINTENANCE FOCUS**: 
- Focus on what developers need to know to maintain this gem in production
- Assess age, update frequency, known issues, and potential conflicts
- Identify maintenance risks and gotchas that could impact the application
- Base findings on actual code analysis, GitHub activity, and community health
- If information is not available, explicitly state "Information not available"

**OPERATIONAL PERSPECTIVE**:
- Every assessment should answer "What does this mean for maintaining this gem?"
- Focus on risks, conflicts, and maintenance burden
- Identify potential breaking changes or deprecations
- Assess community health and long-term viability

**ACTIONABLE FOCUS**:
- Prioritize integration steps and immediate actions
- Provide clear go/no-go guidance upfront
- Focus on practical concerns over detailed analysis
- Keep sections concise and scannable

**CRITICAL NOTES REQUIREMENT**:
- All information from `docs/command_center/pundit/pundit_review_notes.md` is critically important and MUST be incorporated into the final report
- Use your judgment to place this information in the most appropriate sections of the report
- The notes provide essential context for decision-making and should influence the overall assessment
- **MANDATORY**: Create a "Decision Context & Rationale" section in the report that explicitly incorporates all content from the notes file
- **MANDATORY**: Reference the notes content in relevant sections (e.g., "Comparison with Previous Review", "Recommendations")
- **MANDATORY**: If notes contain decision rationale (like choosing Pundit over CanCanCan), include this in the Executive Summary and Conclusion

## Instructions

1. **Read the notes file**: Review `docs/command_center/pundit/pundit_review_notes.md` for specific maintenance concerns and decision rationale
2. **Find the most recent previous report**: Locate the most recent Pundit review in `app/views/command_center/gem_reviews/pundit/` (sort by filename date)
3. **Analyze gem health**: Review source files, GitHub activity, and community metrics
4. **Review documentation**: Examine README.md, CHANGELOG.md, and issue trackers
5. **Follow the template**: Use `docs/command_center/gem_reviews/pundit/pundit_review_template.md` as the structure
6. **Focus on actionable insights**: Analyze:
   - Integration requirements and immediate actions
   - Breaking changes and upgrade path
   - Known conflicts and compatibility issues
   - Maintenance risks and community health
   - Security status and update process

7. **Generate actionable report**: Create a report focused on practical integration guidance
8. **Save the output**: Save to `app/views/command_center/gem_reviews/pundit/` with timestamped filename

## Key Areas to Review (Prioritized)

### Integration Requirements & Immediate Actions
- What are the immediate steps needed to integrate/upgrade?
- What configuration changes are required?
- Are there specific Rails/Ruby version requirements?
- What breaking changes need immediate attention?

### Breaking Changes & Upgrade Path
- What breaking changes occurred in recent versions?
- What's the migration effort and timeline?
- Are there deprecated features that need replacement?
- What's the upgrade path and rollback strategy?

### Known Conflicts & Compatibility
- Does it conflict with other authorization gems (Devise, Rolify, CanCanCan)?
- Are there issues with specific Rails versions?
- What are the most common integration problems?
- Are there deployment or environment conflicts?

### Maintenance Risks & Community Health
- How active is the maintainer and community?
- What's the typical response time for issues?
- Are there long periods without updates?
- Is the gem at risk of being abandoned?

### Security & Performance Status
- Are there known security vulnerabilities?
- What are the performance characteristics?
- Are there memory usage or scaling concerns?
- How quickly are security patches released?

## Maintenance Risk Assessment

### High Risk Indicators
- No updates in 6+ months
- Multiple open critical issues
- Security vulnerabilities without patches
- Breaking changes without clear migration path
- Maintainer inactivity or unresponsiveness

### Medium Risk Indicators
- Infrequent updates (3-6 months)
- Some open issues but not critical
- Minor compatibility issues
- Limited community activity

### Low Risk Indicators
- Regular updates and active maintenance
- Quick response to issues
- Good documentation and migration guides
- Active community and maintainer

## Output Requirements

1. **Executive Summary**: Clear go/no-go guidance with key risks (include decision rationale from notes)
2. **Decision Context & Rationale**: Mandatory section incorporating all content from notes file
3. **Integration Checklist**: Immediate actionable steps for integration/upgrade
4. **Breaking Changes**: Recent changes that could break your app
5. **Compatibility Notes**: Known conflicts and integration caveats
6. **Maintenance Status**: Community health and update frequency
7. **Action Plan**: Immediate/short-term/long-term maintenance strategy
8. **Recommendations**: Keep, upgrade, or replace decision with rationale (reference notes content)

## File Structure to Analyze

- `lib/gem_reviews/pundit/lib/pundit/` - Core functionality
- `lib/gem_reviews/pundit/CHANGELOG.md` - Version history and breaking changes
- `lib/gem_reviews/pundit/pundit.gemspec` - Dependencies and requirements
- GitHub issues and pull requests (if available)
- Community metrics and activity patterns 
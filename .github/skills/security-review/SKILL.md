---
name: security-review
description: Reviews pull request code for security vulnerabilities and reports severity, evidence, impact, and mitigations.
---

Identify vulnerabilities and report findings, but don't modify files or attempt fixes. create an .md file for report. 

## Review Scope

Review application source code only.

Include:
- Application source files
- API endpoints and request handling
- Authentication and authorization logic
- Input validation and sanitization
- Database queries and data access
- File handling and external integrations
- Application dependencies and their usage

Exclude:
- .github/workflows/
- GitHub Actions configuration
- CI/CD pipelines
- Repository configuration
- Build and deployment scripts
- Documentation and Markdown files
- Security-review tooling and its own configuration

Do not report vulnerabilities in excluded files, even if they contain
security-sensitive configuration.

If a finding concerns an excluded file, omit it from the report.

## Final Security Decision

After completing the security review:

1. Report all findings with their severity, confidence, affected file,
   location, vulnerability, impact, and recommended mitigation.

2. Determine the overall security status:
   - FAIL: At least one HIGH or CRITICAL finding exists.
   - PASS: No HIGH or CRITICAL findings exist.

3. At the very end of the report, print exactly one of these lines:

   SECURITY_REVIEW_STATUS: PASS

   SECURITY_REVIEW_STATUS: FAIL

4. Do not ask the user what to do next.
5. Do not modify any files.
6. Do not attempt to fix vulnerabilities.
7. Do not commit or push changes.

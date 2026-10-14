# Security Policy

## Supported Versions

Only the latest default branch (`main`) and the most recent release of each Cytroksys repository are supported. Older releases receive no security updates; please upgrade before reporting.

| Version | Supported |
| ------- | --------- |
| Latest (main / latest release) | Yes |
| Older releases | No |

## Reporting a Vulnerability

Cytroksys takes security seriously. If you discover a vulnerability, please report it **privately and responsibly**.

- **Preferred:** Use GitHub Private Vulnerability Reporting on the affected repository (Repository -> Security tab -> "Report a vulnerability").
- **Email (fallback):** cytroksys@gmail.com with subject `SECURITY: <repo> - <short summary>`.
- **Do not** open public issues, discussions, or pull requests for undisclosed vulnerabilities.

Please include:
- Affected repository, version, and commit SHA
- Description and potential impact
- Steps to reproduce / proof of concept
- Suggested remediation (optional)

We acknowledge reports within 3 business days and aim to provide a fix or mitigation within 30 days depending on severity. We follow coordinated disclosure and credit reporters unless they prefer anonymity.

## Out of Scope

- Social engineering and physical attacks
- Denial of service against shared infrastructure
- Vulnerabilities in third-party dependencies already tracked upstream (report upstream)
- Automated scanner findings without demonstrated impact

## Security Best Practices for Contributors

- Never commit secrets, tokens, keys, or credentials.
- Use least-privilege tokens and rotate them regularly.
- Prefer signing commits (GPG or SSH).
- Keep dependencies updated (Dependabot is enabled organization-wide).
- Pin GitHub Actions to full commit SHAs in production workflows.

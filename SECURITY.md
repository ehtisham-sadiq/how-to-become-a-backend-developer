# Security Policy

## Reporting a Vulnerability

The 90-Day Backend Engineering Roadmap is an educational resource. While we don't handle user data or run production services, we take security seriously in the learning materials we provide.

### What to Report

Please report:

- **Insecure code examples** that could teach bad security practices
- **Vulnerable dependencies** mentioned in the curriculum
- **Broken links** to malicious or compromised sites
- **Outdated security advice** that no longer follows best practices
- **Privacy concerns** in any examples or exercises

### How to Report

1. **DO NOT** open a public issue for security vulnerabilities
2. **Email** the repository maintainer or create a private security advisory via GitHub
3. **Include** details:
   - Location (which day/week/section)
   - Description of the security concern
   - Potential impact on learners
   - Suggested fix (if you have one)

### Response Timeline

- **Initial Response**: Within 48 hours
- **Status Update**: Within 7 days
- **Fix Implementation**: Depends on severity, typically within 14 days

### Security Best Practices in This Roadmap

This curriculum teaches:

- ✅ **Never commit secrets** to version control
- ✅ **Use environment variables** for sensitive configuration
- ✅ **Implement authentication** and authorization properly
- ✅ **Validate and sanitize** all user inputs
- ✅ **Use parameterized queries** to prevent SQL injection
- ✅ **Hash passwords** with bcrypt or Argon2
- ✅ **Implement rate limiting** and CORS correctly
- ✅ **Keep dependencies updated** and scan for vulnerabilities
- ✅ **Use HTTPS** in production
- ✅ **Follow OWASP guidelines** for web application security

### Learner Security Guidelines

As you work through this roadmap:

- **Never use real credentials** in practice projects
- **Don't expose APIs publicly** without proper authentication
- **Use test/development credentials only** (never production)
- **Keep your local environment secure** (firewall, antivirus, updates)
- **Be cautious** with third-party packages and links
- **Review code examples** before running them
- **Use virtual environments** to isolate projects

### Secure Development Resources

We recommend these resources for learning security:

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Python Security Best Practices](https://python.readthedocs.io/en/stable/library/security_warnings.html)
- [FastAPI Security Documentation](https://fastapi.tiangolo.com/tutorial/security/)
- [CWE/SANS Top 25 Most Dangerous Software Errors](https://www.sans.org/top25-software-errors/)

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| Latest  | :white_check_mark: |
| Older   | :x:                |

We maintain only the latest version of the curriculum. If you're using an older fork or version, please update to the latest content.

## Security in Student Projects

If you've built projects following this roadmap and discover a security issue in your own code:

1. **Don't panic** - it's part of learning
2. **Fix it immediately** if it's deployed
3. **Review the security section** of the relevant week
4. **Learn from it** - security is an ongoing practice
5. **Consider sharing** (anonymously) so others can learn

## Updates and Notifications

- Security-related updates will be tagged clearly in commit messages
- Critical security fixes will be announced in the README
- Follow the repository for notifications of security updates

---

**Remember**: Security is not a feature, it's a practice. Every backend developer must prioritize security from day one.

For general questions, use GitHub Issues. For security concerns, use private channels.

Thank you for helping keep this learning resource safe and secure! 🔒

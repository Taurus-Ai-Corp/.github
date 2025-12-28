# Security Policy

TAURUS AI Corp takes security seriously. We appreciate your efforts to responsibly disclose your findings and will make every effort to acknowledge your contributions.

## Supported Versions

We provide security updates for the following versions:

| Project | Version | Supported |
| ------- | ------- | --------- |
| QuantumShield | 1.x | :white_check_mark: |
| Q-GRID | 1.x | :white_check_mark: |
| PropertyVet | 1.x | :white_check_mark: |
| TAURUS AI SaaS | 1.x | :white_check_mark: |
| BizFlow CI | 1.x | :white_check_mark: |

## Reporting a Vulnerability

### How to Report

**DO NOT** create a public GitHub issue for security vulnerabilities.

Instead, please report security vulnerabilities via one of these methods:

1. **Email** (Preferred): security@taurusai.io
2. **GitHub Security Advisory**: Use the "Report a vulnerability" button in the Security tab of the affected repository
3. **Encrypted Email**: Use our PGP key (see below)

### What to Include

Please include the following information in your report:

- **Description**: Clear description of the vulnerability
- **Impact**: Potential impact and severity assessment
- **Steps to Reproduce**: Detailed steps to reproduce the issue
- **Affected Versions**: Which versions are affected
- **Proof of Concept**: Code or screenshots demonstrating the vulnerability
- **Suggested Fix**: If you have recommendations for fixing the issue

### PGP Key

For sensitive communications, you can encrypt your message using our PGP key:

```
Key ID: [TO BE ADDED]
Fingerprint: [TO BE ADDED]
```

You can also find our key on [keys.openpgp.org](https://keys.openpgp.org).

## Response Timeline

| Stage | Timeline |
|-------|----------|
| Initial Response | Within 48 hours |
| Triage & Assessment | Within 5 business days |
| Fix Development | Depends on severity |
| Public Disclosure | After fix is released |

### Severity-Based Response

| Severity | Response Time | Fix Timeline |
|----------|---------------|--------------|
| Critical | 24 hours | 7 days |
| High | 48 hours | 14 days |
| Medium | 5 days | 30 days |
| Low | 10 days | 60 days |

## Disclosure Policy

We follow a coordinated disclosure process:

1. **Reporter** submits vulnerability report
2. **TAURUS AI** acknowledges receipt within 48 hours
3. **TAURUS AI** investigates and confirms the vulnerability
4. **TAURUS AI** develops and tests a fix
5. **TAURUS AI** releases the fix
6. **Public disclosure** after users have had time to update

We request that you:
- Give us reasonable time to address the issue before public disclosure
- Make a good faith effort to avoid privacy violations, destruction of data, and interruption of services
- Do not access or modify data that does not belong to you

## Security Best Practices

When using TAURUS AI products:

### For Developers

- Keep dependencies updated
- Use environment variables for secrets (never commit to git)
- Enable 2FA on your GitHub account
- Review our security configurations in each repository

### For Enterprise Users

- Use our enterprise-grade quantum-resistant cryptography features
- Enable audit logging
- Implement network segmentation
- Regular security assessments

## Quantum Security

TAURUS AI products implement **post-quantum cryptography** standards:

- **ML-DSA** (NIST FIPS 204) - Digital signatures
- **ML-KEM** (NIST FIPS 203) - Key encapsulation
- **AWS KMS Integration** - Production key management

These implementations protect against both current threats and future quantum computing attacks.

## Bug Bounty Program

We currently operate an informal bug bounty program:

| Severity | Reward Range |
|----------|--------------|
| Critical | $500 - $2,000 |
| High | $200 - $500 |
| Medium | $50 - $200 |
| Low | Recognition |

Rewards are determined based on:
- Severity of the vulnerability
- Quality of the report
- Potential impact on users

## Sponsor Priority

[Bronze+ sponsors](SPONSORS.md) receive:
- 24-hour response SLA for security issues
- Priority security patch notifications
- Direct communication channel with security team

## Contact

- **Security Reports**: security@taurusai.io
- **General Questions**: admin@taurusai.io
- **Enterprise Security**: enterprise@taurusai.io

---

Thank you for helping keep TAURUS AI and our users safe!

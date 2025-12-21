# Security Policy

## Reporting Security Vulnerabilities

### Important Notice

This repository archives an **unsupported, outdated version** of WhatsApp Desktop UWP. The application itself **does not receive security updates**. Users should be aware of inherent security risks.

### Scope

This security policy covers:
- ✅ Documentation in this repository
- ✅ Information about known vulnerabilities in archived versions
- ✅ Security best practices for using archived software
- ❌ The WhatsApp application itself (not maintained by us)
- ❌ WhatsApp's backend servers (managed by Meta)

### Reporting Process

#### For Documentation or Repository Security Issues

If you discover a security issue with this repository (not the app):

1. **Do NOT open a public issue**
2. Email the maintainer privately (see GitHub profile)
3. Include:
   - Description of the vulnerability
   - Potential impact
   - Steps to reproduce (if applicable)
   - Suggested fix (optional)

We will respond within **7 days** and work with you to address the issue.

#### For WhatsApp Application Vulnerabilities

If you discover a vulnerability in the archived WhatsApp UWP app:

1. **Report to WhatsApp/Meta** through their official channels:
   - WhatsApp Security: https://www.whatsapp.com/security/
   - Meta Bug Bounty: https://www.facebook.com/whitehat

2. **Optionally inform us** so we can:
   - Document the vulnerability in this archive
   - Update warnings and disclaimers
   - Inform users of the risk

⚠️ **Note**: Since this is an archived version, the vulnerability likely won't be patched in this version.

## Known Security Limitations

### Archived Software Risks

Users should be aware that archived software has inherent security risks:

| Risk | Description | Mitigation |
|------|-------------|------------|
| **No Patches** | Security vulnerabilities won't be fixed | Use on isolated systems |
| **Protocol Changes** | WhatsApp may change security protocols | Monitor for connection issues |
| **Outdated Encryption** | May use older crypto implementations | Use for non-sensitive communications |
| **Account Security** | Unsupported clients may be targeted | Enable 2FA on WhatsApp |
| **Malware Risk** | Unofficial sources may distribute malware | Only download from trusted sources |

### Specific Concerns

#### End-to-End Encryption
- The app uses Signal Protocol for E2E encryption
- Implementation may be outdated compared to current versions
- Core encryption should still be secure, but protocol changes may affect compatibility

#### Local Data Storage
- Messages stored locally in encrypted SQLite databases
- Encryption keys stored in Windows Credential Manager
- No longer receives updates to storage encryption methods

#### Network Security
- Uses WSS (WebSocket Secure) for connections
- TLS/SSL versions may be outdated
- Certificate validation follows Windows standards

#### Update Mechanism
- Update protection blocks official security updates
- This is intentional but creates security exposure
- Users must weigh convenience vs. security

## Security Best Practices

If you choose to use the archived app, follow these practices:

### System Security
- ✅ Keep Windows fully updated
- ✅ Use Windows Defender or reputable antivirus
- ✅ Enable Windows Firewall
- ✅ Use strong local account passwords
- ✅ Enable BitLocker disk encryption (if available)

### Network Security
- ✅ Use trusted networks (home, office)
- ✅ Avoid public WiFi for sensitive chats
- ✅ Consider using a VPN
- ✅ Enable firewall rules for the app

### Account Security
- ✅ Enable two-factor authentication on WhatsApp
- ✅ Use strong, unique passwords
- ✅ Regularly review linked devices
- ✅ Monitor for suspicious activity
- ✅ Backup messages to your phone

### Application Security
- ✅ Download only from trusted sources
- ✅ Verify file checksums/signatures
- ✅ Don't share QR codes or session tokens
- ✅ Log out when sharing PC with others
- ✅ Keep the app locked when not in use

### Data Security
- ✅ Don't store highly sensitive data in chats
- ✅ Regularly clear media cache
- ✅ Delete old conversations periodically
- ✅ Use disappearing messages for sensitive topics
- ✅ Backup data regularly

## Vulnerability Disclosure Timeline

When vulnerabilities are reported to us:

1. **Day 0**: Receive report, acknowledge receipt
2. **Day 1-7**: Assess severity and impact
3. **Day 7-14**: Coordinate with reporter, prepare advisory
4. **Day 14-30**: Public disclosure (coordinated with reporter)
5. **Day 30+**: Update documentation with warnings

We follow **coordinated disclosure** principles.

## Known Vulnerabilities

We will maintain a list of known vulnerabilities in archived versions here:

### CVE-YYYY-XXXX (Example Format)
- **Severity**: High/Medium/Low
- **Affected Versions**: All/Specific versions
- **Description**: Brief description
- **Impact**: What attackers could do
- **Mitigation**: What users can do
- **Status**: Unfixed (archived version)

*Currently, no specific CVEs have been documented for this archive.*

## Security Resources

### For Users
- [WhatsApp Security](https://www.whatsapp.com/security/)
- [Windows Security](https://www.microsoft.com/security/)
- [OWASP Mobile Security](https://owasp.org/www-project-mobile-security/)

### For Researchers
- [WhatsApp Bug Bounty](https://www.facebook.com/whitehat)
- [Microsoft Security Response Center](https://www.microsoft.com/msrc)
- [Responsible Disclosure Guidelines](https://cheatsheetseries.owasp.org/cheatsheets/Vulnerability_Disclosure_Cheat_Sheet.html)

## Disclaimer

**⚠️ CRITICAL SECURITY WARNING ⚠️**

This archived application:
- Does NOT receive security updates
- May contain unpatched vulnerabilities
- Could expose you to security risks
- May violate WhatsApp Terms of Service

**Use at your own risk.** We strongly recommend:
1. Using official, supported versions when possible
2. Accepting the risks if you choose to use archived versions
3. Following security best practices religiously
4. Being prepared for potential account restrictions

The maintainers of this repository:
- Are NOT responsible for security breaches
- Cannot fix vulnerabilities in the archived app
- Provide this information for educational purposes only
- Strongly advise caution when using outdated software

## Updates to This Policy

This security policy may be updated to reflect:
- New vulnerability disclosures
- Changes in security landscape
- Updated best practices
- Community feedback

Last updated: December 2024

---

**Questions about this security policy?** Open an issue with the "security" label.

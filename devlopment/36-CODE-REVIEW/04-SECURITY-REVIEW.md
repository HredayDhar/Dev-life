# 04-SECURITY-REVIEW

## 1. What Is Security Review in Code Review?

Security review in the context of code review is the systematic examination of code changes to identify potential security vulnerabilities, weaknesses in security controls, and areas where security best practices are not being followed. It focuses on ensuring that the code does not introduce security risks that could lead to unauthorized access, data breaches, privilege escalation, or other security incidents.

Unlike functional testing which verifies that features work as intended, security review looks for how the code might be misused, attacked, or bypassed by malicious actors. It considers both obvious vulnerabilities (like SQL injection) and subtle flaws (like timing attacks or improper error handling that leaks information).

## 2. Why Does Security Review Matter in Code Review?

Security review matters in code review because:

- **Early Vulnerability Detection**: Identifying security issues during development is significantly cheaper and easier than fixing them in production
- **Defense in Depth**: Multiple layers of review increase the likelihood that security issues are caught before deployment
- **Developer Education**: Regular security-focused review helps developers learn secure coding practices and think like attackers
- **Compliance Requirements**: Many regulations and standards require security considerations in development processes
- **Reputation Protection**: Security incidents damage organizational reputation and erode customer trust
- **Financial Impact**: The cost of a security breach far exceeds the cost of preventive measures during development
- **Operational Continuity**: Security incidents can disrupt business operations and cause downtime
- **Intellectual Property Protection**: Prevents unauthorized access to proprietary algorithms, data, and trade secrets
- **Legal Liability Reduction**: Demonstrates due diligence in protecting user data and system integrity
- **Trust Building**: Shows commitment to security, which is increasingly important to customers and partners
- **Attack Surface Reduction**: Identifies and eliminates unnecessary exposure points before they can be exploited
- **Secure Defaults Promotion**: Ensures that security features are enabled by default rather than requiring opt-in
- **Threat Modeling Integration**: Connects abstract threat models to concrete code implementations

## 3. What Problem Does Inadequate Security Review Cause?

Inadequate security review leads to numerous problems that can have severe consequences:

- **Data Breaches**: Unauthorized access to sensitive information including PII, financial data, health records, or intellectual property
- **Account Compromise**: Attackers gaining unauthorized access to user accounts, administrative privileges, or system controls
- **Service Disruption**: Denial of service attacks that make applications unavailable to legitimate users
- **Financial Theft**: Direct monetary losses through fraudulent transactions or unauthorized fund transfers
- **Regulatory Fines**: Penalties for non-compliance with data protection regulations (GDPR, CCPA, HIPAA, PCI-DSS, etc.)
- **Legal Liability**: Lawsuits from affected users, customers, or partners due to negligence
- **Reputational Damage**: Loss of customer trust and brand value that can take years to rebuild
- **Operational Costs**: Expenses related to incident response, forensics, notification, and remediation
- **Intellectual Property Loss**: Theft of proprietary algorithms, source code, or business strategies
- **Supply Chain Compromise**: Using the breached system as a stepping stone to attack partners or customers
- **Long-term Vulnerabilities**: Persistent weaknesses that remain undetected for months or years
- **Evasion of Detection**: Security flaws designed to avoid logging or monitoring systems
- **Privilege Escalation**: Gaining higher-level access than intended through exploitation of flaws
- **Persistence Mechanisms**: Establishing backdoors that survive system reboots and security updates
- **Social Engineering Enablement**: Creating conditions that make phishing or other social attacks more effective
- **Malware Distribution**: Using compromised systems to spread malware to users or partner organizations
- **Cryptocurrency Mining**: Hijacking computational resources for illicit cryptocurrency mining
- **Ransomware Vulnerability**: Creating conditions that make systems susceptible to ransomware attacks

## 4. Key Dimensions of Security Review

### 4.1 Input Validation and Sanitization
- **Parameter validation**: All external inputs checked for type, length, format, and range
- **SQL injection prevention**: Parameterized queries or proper escaping for database queries
- **XSS prevention**: Proper output encoding for HTML, JavaScript, and other contexts
- **Command injection prevention**: Avoiding shell command construction from user input
- **Path traversal prevention**: Validating file paths to prevent directory escape
- **Deserialization safety**: Safe handling of deserialized data from untrusted sources
- **XML security**: Protection against XXE, XPath injection, and other XML-based attacks
- **File upload validation**: Checking file types, content, and names for malicious uploads

### 4.2 Authentication and Authorization
- **Password security**: Strong hashing algorithms (bcrypt, scrypt, PBKDF2) with proper salting
- **Session management**: Secure session IDs, proper expiration, and protection against fixation/hijacking
- **Multi-factor authentication**: Proper implementation and enforcement where required
- **Credential storage**: Secure storage of passwords, API keys, certificates, and other secrets
- **Access control checks**: Proper verification of user permissions before granting access
- **Principle of least privilege**: Users and services operate with minimum necessary permissions
- **Authorization bypass prevention**: Protecting against vertical/horizontal privilege escalation
- **Remember-me security**: Secure implementation of persistent login features
- **Password recovery**: Secure implementation of reset/password change functionality
- **Account enumeration prevention**: Avoiding timing differences or messages that reveal user existence

### 4.3 Cryptography and Data Protection
- **Algorithm selection**: Using strong, industry-standard cryptographic algorithms
- **Key management**: Secure generation, storage, rotation, and destruction of cryptographic keys
- **Random number generation**: Using cryptographically secure random number generators
- **Data encryption at rest**: Protecting sensitive data stored in databases, files, or backups
- **Data encryption in transit**: Using TLS/SSL properly for network communications
- **Certificate validation**: Proper verification of SSL/TLS certificates and certificate chains
- **Password hashing**: Using adaptive hashing algorithms appropriate for password storage
- **Secret management**: Avoiding hardcoded credentials and using secure secret stores
- **Digital signatures**: Proper implementation and verification of cryptographic signatures
- **Hash length extension**: Protection against length extension attacks where applicable

### 4.4 Configuration and Dependencies
- **Secure defaults**: Security features enabled by default rather than requiring configuration
- **Dependency scanning**: Checking for known vulnerable versions of libraries and frameworks
- **Configuration security**: Ensuring security-related configuration options are properly set
- **Information disclosure**: Preventing accidental exposure of sensitive information via error messages
- **Server configuration**: Proper configuration of web servers, application servers, and frameworks
- **CORS configuration**: Appropriate Cross-Origin Resource Sharing policies
- **Security headers**: Implementation of HTTP security headers (HSTS, CSP, X-Frame-Options, etc.)
- **Third-party code review**: Examining security implications of integrated third-party components
- **Container security**: Proper configuration of container images and runtime security options
- **Infrastructure as Code security**: Scanning IaC templates for security misconfigurations

### 4.5 Error Handling and Logging
- **Information leakage prevention**: Error messages don't reveal sensitive system or security details
- **Exception handling**: Secure handling of exceptions that could leak information or create vulnerabilities
- **Logging security**: Ensuring logs don't contain sensitive information (passwords, session tokens, etc.)
- **Audit trail completeness**: Security-relevant actions are properly logged for forensic analysis
- **Log injection prevention**: Preventing attackers from injecting malicious content into logs
- **Monitoring and alerting**: Proper logging of security events for detection and response
- **Fail-secure behavior**: Systems default to a secure state when errors occur
- **Stack trace protection**: Preventing exposure of internal implementation details in errors
- **Error message consistency**: Generic error messages that don't aid attackers in reconnaissance

### 4.6 Business Logic and Design Flaws
- **Authorization logic flaws**: Bypassing intended authorization through direct object reference or workflow manipulation
- **Race conditions**: Timing-dependent vulnerabilities in concurrent operations
- **Business rule bypass**: Circumventing intended business logic through unexpected input sequences
- **Reward/application logic flaws**: Exploiting gaps in promotional, loyalty, or scoring systems
- **File operation vulnerabilities**: Insecure file creation, modification, or deletion operations
- **Image processing flaws**: Exploiting vulnerabilities in image parsing or manipulation libraries
- **XML external entity (XXE) attacks**: Exploiting XML processors to access local files or perform SSRF
- **Server-side request forgery (SSRF)**: Making the server perform unintended requests to internal systems
- **Template injection**: Injecting malicious code into server-side template engines
- **Deserialization vulnerabilities**: Exploiting unsafe deserialization of user-controlled data
- **Insecure direct object references (IDOR)**: Accessing objects directly without proper authorization checks
- **File inclusion vulnerabilities**: Local or remote file inclusion through insufficient input validation

### 4.7 Client-Side Security
- **DOM-based XSS prevention**: Safe manipulation of the Document Object Model
- **JavaScript security**: Proper handling of user input in JavaScript contexts
- **Clickjacking protection**: Implementation of frame-busting techniques or CSP headers
- **Content Security Policy**: Proper deployment of CSP to mitigate XSS and data injection attacks
- **Subresource integrity**: Verifying integrity of loaded third-party resources
- **Cookie security**: Proper use of Secure, HttpOnly, and SameSite attributes
- **Local storage security**: Safe usage patterns for client-side storage mechanisms
- **WebSocket security**: Secure establishment and usage of WebSocket connections
- **PostMessage security**: Proper validation of cross-window messaging
- **Service worker security**: Secure implementation and scope limitation of service workers
- **Third-party script security**: Careful evaluation of externally loaded JavaScript

## 5. Junior vs Senior Perspective on Security Review

### Junior Reviewer Focus
- **Obvious vulnerabilities**: Clear SQL injection patterns, visible secrets in code
- **Basic input validation**: Checking for validation on clearly external inputs
- **Common patterns**: Recognizing frequently seen anti-patterns like string concatenation in SQL
- **Hardcoded secrets**: Spotting passwords, API keys, or tokens literally in the source code
- **Missing HTTPS**: Noticing HTTP URLs in places where HTTPS should be used
- **Basic password storage**: Recognizing plain text or weak hashing (MD5, SHA1) for passwords
- **Obvious access control issues**: Missing checks on clearly protected endpoints or functions
- **Standard header omissions**: Missing common security headers like X-Frame-Options

### Senior Reviewer Focus
- **Complex attack chaining**: Understanding how multiple minor issues could combine for significant impact
- **Context-aware validation**: Evaluating whether validation is appropriate for the specific use case and context
- **Authentication flow analysis**: Examining entire authentication sequences for subtle flaws
- **Authorization model assessment**: Evaluating whether the overall access control model is sound
- **Cryptographic implementation review**: Examining how cryptography is used, not just what algorithms
- **Third-party risk evaluation**: Assessing security implications of dependencies and integrations
- **Timing and side-channel analysis**: Considering attacks that exploit time, power, or electromagnetic leaks
- **Business logic exploitation paths**: Understanding how legitimate features could be abused
- **Framework-specific vulnerabilities**: Knowing security quirks and common flaws in specific frameworks
- **Configuration interaction analysis**: Understanding how multiple settings combine to affect security
- **Zero-day awareness**: Knowledge of recent vulnerability disclosures that might affect the codebase
- **Secure SDLC integration**: Evaluating how security practices integrate with development processes
- **Threat model alignment**: Ensuring code changes don't invalidate or bypass established threat models
- **Security debt recognition**: Identifying accumulated security shortcomings that need addressing

## 6. Security Review Checklist

### Input Validation
- [ ] Are all external inputs (user input, API parameters, file contents, network data) validated?
- [ ] Is validation performed using whitelists (acceptable values) rather than blacklists (rejected values) where possible?
- [ ] Are input validation routines centralized and reused rather than duplicated?
- [ ] Are string length limits enforced to prevent buffer overflows or DoS through large inputs?
- [ ] Are numeric inputs checked for valid range and type (integer vs float)?
- [ ] Are special characters properly handled or escaped based on output context?
- [ ] Are file paths validated to prevent directory traversal attacks?
- [ ] Are file uploads checked for type, content, size, and name before processing?
- [ ] Are email addresses, URLs, and other formatted inputs validated for proper syntax?
- [ ] Are SQL queries constructed using parameterized statements or ORM safety features?
- [ ] Are LDAP queries protected against injection through proper escaping or filtering?
- [ ] Are XPath and XQuery inputs protected against injection?
- [ ] Are command-line arguments properly escaped to prevent command injection?
- [ ] Are HTML outputs properly escaped based on context (HTML body, attribute, JavaScript, CSS)?
- [ ] Are JavaScript outputs properly escaped to prevent XSS in script contexts?
- [ ] Are CSS values properly escaped to prevent CSS injection?
- [ ] Are URLs properly validated to prevent SSRF or open redirect vulnerabilities?
- [ ] Are JSON inputs properly parsed and validated to prevent injection or deserialization attacks?
- [ ] Are XML inputs processed with external entity resolution disabled to prevent XXE attacks?

### Authentication
- [ ] Are passwords hashed using strong, adaptive algorithms (bcrypt, scrypt, PBKDF2) with proper salting?
- [ ] Is password hashing performed on the server side never client-side?
- [ ] Are password policies stored as configuration rather than hardcoded?
- [ ] Are password reset tokens cryptographically secure and time-limited?
- [ ] Are account lockout mechanisms implemented to prevent brute force attacks?
- [ ] Are multi-factor authentication options properly secured when offered?
- [ ] Are session identifiers generated using cryptographically secure random number generators?
- [ ] Are session IDs sufficiently long (minimum 128 bits) to prevent brute force guessing?
- [ ] Are session IDs transmitted only over secure channels (HTTPS)?
- [ ] Are session cookies marked as Secure and HttpOnly when appropriate?
- [ ] Are session expiration and invalidation properly implemented on logout and timeout?
- [ ] Is protection against session fixation implemented (new session ID after login)?
- [ ] Are "remember me" implementations secure, using long-lived tokens separate from session IDs?
- [ ] Are password change operations requiring current password verification?
- [ ] Are password reset processes resistant to enumeration and timing attacks?
- [ ] Are authentication error messages generic to prevent user enumeration?
- [ ] Are authentication attempts logged for monitoring and anomaly detection?
- [ ] Are default credentials eliminated or changed in all deployed components?
- [ ] Are account recovery processes secure against social engineering and hijacking?
[...]
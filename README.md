# Boot.dev Secure Projects

Practical security tools built from Boot.dev learning exercises.

## Goal

Convert Boot.dev software engineering concepts into practical cybersecurity, AppSec, and DevSecOps portfolio projects.

## Positioning

Boot.dev provides the programming, backend, and DevOps foundation. This repo applies OWASP Top 10, OWASP ASVS, and NIST SSDF as the security engineering layer.

## Alignment with Security Journey

This repository is aligned to the roadmap in `bootdev-security-journey`.

- Phase 1 status: **In Progress** (Python track completed through core chapters)
- Near-term portfolio focus: Projects 1–3
- Mid-term portfolio focus: Projects 4–5
- Advanced specialization track: AppSec review, threat modeling, secure code review, DevSecOps pipeline

## About

This repository contains security-focused projects that evolve from Boot.dev programming exercises. Each project demonstrates the practical application of software engineering concepts to cybersecurity use cases.

## Repository Structure

```
bootdev-secure-projects/
├── README.md                    # This file
├── project-ideas.md            # Project concepts and evolution
├── security-references.md       # OWASP, ASVS, NIST references
├── python-log-analyzer/         # Project 1: Log analysis tool
├── file-integrity-monitor/      # Project 2: File integrity checker
├── vulnerability-triage-tool/   # Project 3: CVE tracking tool
├── secure-backend-api/          # Project 4: Secure API (future)
└── containerized-security-toolkit/ # Project 5: Container tools (future)
```

## Project Philosophy

Each project follows an evolution framework:

1. **Exercise Connection** - Identify relevant Boot.dev exercise
2. **Security Mapping** - Map to OWASP Top 10 category
3. **Prototype Development** - Create minimal working example
4. **Project Completion** - Expand to full-featured tool

## Current Projects

### 1. Python Log Analyzer
**Status:** 🔄 Planning
**Boot.dev Concepts:** Strings, loops, dictionaries, file handling, functions
**OWASP Mapping:** A07 (Auth Failures), A09 (Logging)
**Goal:** Parse auth logs, detect brute force attacks, generate reports

See [python-log-analyzer/README.md](python-log-analyzer/README.md)

### 2. File Integrity Monitor
**Status:** 🔄 Planning
**Boot.dev Concepts:** File handling, functions, dictionaries, error handling, hashing
**OWASP Mapping:** A08 (Integrity Failures), A02 (Cryptographic Failures)
**Goal:** Hash files, detect modifications, report changes

See [file-integrity-monitor/README.md](file-integrity-monitor/README.md)

### 3. Vulnerability Triage Tool
**Status:** 🔄 Planning
**Boot.dev Concepts:** Data structures, CLI input, JSON/CSV handling, functions
**OWASP Mapping:** A06 (Vulnerable Components), A09 (Monitoring)
**Goal:** Track CVEs, manage remediation, generate reports

See [vulnerability-triage-tool/README.md](vulnerability-triage-tool/README.md)

## Future Projects

### 4. Secure Backend API
**Status:** 🔄 Planned (Phase 3)
**Boot.dev Concepts:** HTTP servers, SQL, routing, error handling, logging
**OWASP Mapping:** A01, A03, A07, A09
**ASVS Mapping:** V2, V4, V5, V7
**Goal:** Build secure REST API with authentication, validation, logging

### 5. Containerized Security Toolkit
**Status:** 🔄 Planned (Phase 4)
**Boot.dev Concepts:** Docker, Linux, CLI tooling, GitHub workflow
**OWASP Mapping:** A05, A06
**NIST SSDF Mapping:** PW.3, RV.2
**Goal:** Dockerize security tools, add hardening guidelines

## Advanced Specialization Projects (Phase 5)

These projects align with the advanced section of `bootdev-security-journey/roadmap.md`:

- AppSec Review Project
- Threat Modeling Project
- Secure Code Review Collection
- DevSecOps Pipeline Project

## Security Standards

All projects adhere to security standards:

- **OWASP Top 10** - Primary security framework
- **OWASP ASVS** - Verification standard for backend projects
- **NIST SSDF** - Secure development lifecycle for DevSecOps

See [security-references.md](security-references.md) for detailed mappings.

## Project Timeline

### Q2 2026 (May-June)
- [ ] Python Log Analyzer
- [ ] File Integrity Monitor

### Q3 2026 (July-September)
- [ ] Vulnerability Triage Tool
- [ ] Begin Phase 3 learning

### Q4 2026 (October-December)
- [ ] Secure Backend API
- [ ] Complete Phase 3

### Q1 2027 (January-March)
- [ ] Containerized Security Toolkit
- [ ] Complete Phase 4

## Development Workflow

### For Each Project:

1. **Planning Phase**
   - Review Boot.dev concepts
   - Map to OWASP categories
   - Design security features
   - Document in project README

2. **Development Phase**
   - Create minimal prototype
   - Apply to security use case
   - Test with sample data
   - Document approach

3. **Completion Phase**
   - Expand to full features
   - Add comprehensive documentation
   - Include security considerations
   - Create portfolio-worthy artifact

4. **Portfolio Phase**
   - Add usage examples
   - Document security standards
   - Create demo scenarios
   - Prepare for interviews

## Security Best Practices

When developing these projects:

1. **Input Validation** - Validate all inputs using principles from bootdev-python-security
2. **Error Handling** - Use safe error messages (OWASP A05)
3. **Logging** - Implement security logging (OWASP A09)
4. **Hardening** - Follow security hardening guidelines
5. **Documentation** - Document security considerations

## Related Repositories

- **[bootdev-security-journey](https://github.com/DADAHOJO/bootdev-security-journey)** - Main portfolio hub with roadmap
- **[bootdev-python-security](https://github.com/DADAHOJO/bootdev-python-security)** - Python learning with security mapping

## Contributing

These are personal learning projects. However, security improvements and suggestions are welcome through GitHub issues.

## License

Projects are for educational purposes and portfolio demonstration.

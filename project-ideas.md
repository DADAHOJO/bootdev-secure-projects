# Project Ideas

Detailed concepts and evolution paths for security projects.

## Project Evolution Framework

### Stage 1: Exercise Connection
- Identify relevant Boot.dev exercise
- Note security application
- Document mapping to OWASP/ASVS

### Stage 2: Prototype Development
- Create minimal working example
- Apply to security use case
- Test with sample data
- Document approach

### Stage 3: Project Completion
- Expand to full-featured tool
- Add comprehensive README
- Include security considerations
- Add usage examples
- Create portfolio-worthy artifact

## Project 1: Python Log Analyzer

### Exercise Connection
**Boot.dev Concepts:**
- Strings (parsing log lines)
- Loops (iterating through logs)
- Dictionaries (counting events by IP)
- File handling (reading log files)
- Functions (modular analysis)
- Debugging (error handling)

### Security Mapping
**OWASP Top 10:**
- A07: Identification and Authentication Failures (failed login detection)
- A09: Security Logging and Monitoring Failures (log analysis)

### Prototype Idea
```python
def count_failed_logins(log_file):
    """Count failed login attempts by IP"""
    failures = {}
    with open(log_file) as f:
        for line in f:
            if "Failed password" in line:
                ip = extract_ip(line)
                failures[ip] = failures.get(ip, 0) + 1
    return failures
```

### Full Project Features
- [ ] Parse common log formats (auth.log, sshd logs)
- [ ] Count failed login attempts per IP
- [ ] Identify IPs exceeding threshold
- [ ] Generate summary report
- [ ] Export results to CSV/JSON
- [ ] Command-line interface
- [ ] Support for multiple log sources
- [ ] Alert on suspicious patterns

### Portfolio Value
Demonstrates ability to build security monitoring tools using fundamental Python concepts. Shows understanding of log analysis and brute force detection.

## Project 2: File Integrity Monitor

### Exercise Connection
**Boot.dev Concepts:**
- File handling (reading files)
- Functions (modular operations)
- Dictionaries (storing file hashes)
- Error handling (safe file operations)
- Hashing (integrity verification - future learning)

### Security Mapping
**OWASP Top 10:**
- A08: Software and Data Integrity Failures (integrity checking)
- A02: Cryptographic Failures (hash functions)

### Prototype Idea
```python
import hashlib

def calculate_hash(filepath):
    """Calculate SHA-256 hash of file"""
    sha256 = hashlib.sha256()
    with open(filepath, 'rb') as f:
        sha256.update(f.read())
    return sha256.hexdigest()

def check_integrity(filepath, baseline_hash):
    """Check if file matches baseline"""
    current_hash = calculate_hash(filepath)
    return current_hash == baseline_hash
```

### Full Project Features
- [ ] Calculate SHA-256 hashes for files
- [ ] Store baseline in JSON/SQLite
- [ ] Compare current state to baseline
- [ ] Report changes (modified, new, deleted)
- [ ] Exclude certain files/directories
- [ ] Scheduled scanning support
- [ ] Recursive directory scanning
- [ ] Hash algorithm selection

### Portfolio Value
Shows understanding of integrity verification and file system security. Demonstrates practical application of cryptographic concepts.

## Project 3: Vulnerability Triage Tool

### Exercise Connection
**Boot.dev Concepts:**
- Data structures (organizing CVE data)
- CLI input (interactive tool)
- JSON/CSV handling (import/export)
- Functions (CRUD operations)
- OOP (later enhancement)

### Security Mapping
**OWASP Top 10:**
- A06: Vulnerable and Outdated Components (dependency tracking)
- A09: Security Logging and Monitoring Failures (vulnerability tracking)

### Prototype Idea
```python
vulnerabilities = []

def add_cve(cve_id, component, severity, owner):
    """Add a CVE to tracking"""
    vuln = {
        'id': cve_id,
        'component': component,
        'severity': severity,
        'owner': owner,
        'status': 'Open'
    }
    vulnerabilities.append(vuln)

def get_by_severity(severity):
    """Get vulnerabilities by severity"""
    return [v for v in vulnerabilities if v['severity'] == severity]
```

### Full Project Features
- [ ] Add CVE records
- [ ] Update CVE status
- [ ] Search/filter by severity
- [ ] Assign remediation owners
- [ ] Generate summary reports
- [ ] Export to CSV/JSON
- [ ] Import from CVE database APIs
- [ ] CVSS score calculation
- [ ] Due date tracking

### Portfolio Value
Demonstrates data structure skills and understanding of vulnerability management processes. Shows ability to build practical security operations tools.

## Project 4: Secure Backend API

### Exercise Connection
**Boot.dev Concepts:**
- HTTP servers (API endpoints)
- SQL (database queries)
- Routing (endpoint design)
- Error handling (safe responses)
- Logging (security events)

### Security Mapping
**OWASP Top 10:**
- A01: Broken Access Control (authorization)
- A03: Injection (SQL injection prevention)
- A07: Identification and Authentication Failures (auth)
- A09: Security Logging and Monitoring Failures (logging)

**ASVS Mapping:**
- V2: Authentication
- V4: Access Control
- V5: Validation
- V7: Error Handling and Logging

### Prototype Idea
```python
from flask import Flask, request, jsonify
import sqlite3

app = Flask(__name__)

@app.route('/api/users/<user_id>', methods=['GET'])
def get_user(user_id):
    # Input validation
    if not user_id.isdigit():
        return jsonify({'error': 'Invalid user ID'}), 400
    
    # Parameterized query
    conn = sqlite3.connect('users.db')
    cursor = conn.cursor()
    cursor.execute("SELECT * FROM users WHERE id = ?", (user_id,))
    
    user = cursor.fetchone()
    conn.close()
    
    if user:
        return jsonify({'user': user})
    return jsonify({'error': 'User not found'}), 404
```

### Full Project Features
- [ ] RESTful API design
- [ ] Input validation on all endpoints
- [ ] Parameterized SQL queries
- [ ] Secure error messages
- [ ] Structured security logging
- [ ] Basic authentication
- [ ] Rate limiting
- [ ] CORS configuration
- [ ] API documentation
- [ ] Security headers

### Portfolio Value
Shows secure backend development skills and OWASP/ASVS knowledge. Demonstrates understanding of web security best practices.

## Project 5: Containerized Security Toolkit

### Exercise Connection
**Boot.dev Concepts:**
- Docker (containerization)
- Linux (container OS)
- CLI tooling (scripting)
- GitHub workflow (automation)

### Security Mapping
**OWASP Top 10:**
- A05: Security Misconfiguration (container hardening)
- A06: Vulnerable and Outdated Components (image scanning)

**NIST SSDF Mapping:**
- PW.3: Protect software during operation
- RV.2: Respond to vulnerabilities in dependencies

### Prototype Idea
```dockerfile
FROM python:3.11-slim

WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY log_analyzer.py .
COPY file_monitor.py .
COPY vuln_triage.py .

RUN chmod +x *.py

ENTRYPOINT ["python"]
```

### Full Project Features
- [ ] Containerize Log Analyzer
- [ ] Containerize File Integrity Monitor
- [ ] Containerize Vulnerability Triage Tool
- [ ] Create unified entrypoint
- [ ] Add health checks
- [ ] Document security hardening
- [ ] Include usage examples
- [ ] Add CI/CD pipeline
- [ ] Image scanning integration
- [ ] Minimal base images

### Portfolio Value
Demonstrates DevSecOps skills and container security knowledge. Shows ability to operationalize security tools.

## Additional Project Ideas

### Secure Password Manager
**Boot.dev Concepts:** Encryption, file handling, CLI
**OWASP Mapping:** A02 (Cryptographic Failures)
**Features:** Password storage, encryption, secure retrieval

### Web Application Firewall Concepts
**Boot.dev Concepts:** HTTP, pattern matching, filtering
**OWASP Mapping:** Multiple Top 10 categories
**Features:** Request filtering, attack detection, rule management

### SIEM Log Correlation Tool
**Boot.dev Concepts:** Data structures, file handling, analysis
**OWASP Mapping:** A09 (Logging)
**Features:** Log aggregation, correlation rules, alerting

### Security Scanning Automation
**Boot.dev Concepts:** Automation, scripting, APIs
**OWASP Mapping:** A06 (Vulnerable Components)
**Features:** Automated scanning, report generation, remediation tracking

### Incident Response Playbook Tool
**Boot.dev Concepts:** Documentation, workflow, state management
**NIST SSDF Mapping:** RV (Respond), RE (Recover)
**Features:** Playbook templates, workflow tracking, status reporting

## Project Selection Criteria

Projects are selected based on:

1. **Relevance to Boot.dev curriculum** - Uses concepts being learned
2. **Security value** - Addresses real security concerns
3. **Portfolio impact** - Demonstrates marketable skills
4. **Complexity progression** - Builds from simple to complex
5. **Tool usefulness** - Creates genuinely useful security tools

## Advanced Specialization Projects (Phase 5)

After the first five core projects, this repository continues with advanced security specialization work aligned to the journey roadmap:

### AppSec Review Project
- Review Secure Backend API attack surface
- Map findings to OWASP Top 10
- Document findings, fixes, and verification notes

### Threat Modeling Project
- Build architecture diagrams and trust boundaries
- Use STRIDE for threat identification
- Document mitigations and residual risk

### Secure Code Review Collection
- Maintain insecure vs secure code examples
- Explain security impact and remediation rationale
- Build reusable secure coding references for interviews

### DevSecOps Pipeline Project
- Add CI/CD security checks (linting, dependency scanning)
- Document pipeline behavior and hardening decisions
- Map controls to NIST SSDF and OWASP ASVS where relevant

## Future Expansion

As Boot.dev learning progresses, additional projects may include:

- **Network security tools** (after learning networking concepts)
- **Web security scanners** (after learning HTTP and web security)
- **Cloud security automation** (after learning AWS and DevSecOps)
- **Machine learning for security** (advanced topic)

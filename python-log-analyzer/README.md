# Python Log Analyzer

A security-focused log analysis tool for detecting authentication anomalies and brute force attacks.

## Status

🔄 Planning Phase

## Overview

This project evolves from Boot.dev Python exercises (strings, loops, dictionaries, file handling) to create a practical security tool for analyzing authentication logs and detecting suspicious activity.

## Boot.dev Concepts Applied

- **Strings** - Parsing log lines and extracting information
- **Loops** - Iterating through log files for analysis
- **Dictionaries** - Counting events by IP address
- **File Handling** - Reading and processing log files
- **Functions** - Modular analysis operations
- **Debugging** - Error handling and troubleshooting

## Security Mapping

### OWASP Top 10

**A07: Identification and Authentication Failures**
- Detects failed login attempts
- Identifies brute force attacks
- Tracks authentication anomalies

**A09: Security Logging and Monitoring Failures**
- Parses security logs
- Detects attack patterns
- Generates security reports

## Features

### Planned Features

- [ ] Parse common log formats (auth.log, sshd logs)
- [ ] Count failed login attempts per IP
- [ ] Identify IPs exceeding threshold
- [ ] Generate summary report
- [ ] Export results to CSV/JSON
- [ ] Command-line interface
- [ ] Support for multiple log sources
- [ ] Alert on suspicious patterns

### Prototype Structure

```python
def parse_log_file(log_path):
    """Parse log file and extract relevant entries"""
    pass

def count_failed_logins(log_entries):
    """Count failed login attempts by IP"""
    pass

def detect_brute_force(failure_counts, threshold):
    """Detect IPs exceeding failure threshold"""
    pass

def generate_report(suspicious_ips):
    """Generate security report"""
    pass
```

## Usage Example (Planned)

```bash
# Analyze authentication log
python log_analyzer.py /var/log/auth.log --threshold 5

# Export to JSON
python log_analyzer.py /var/log/auth.log --output report.json

# Custom threshold
python log_analyzer.py /var/log/auth.log --threshold 10 --alert
```

## Implementation Plan

### Phase 1: Prototype
- [ ] Basic log file reading
- [ ] Simple IP extraction
- [ ] Dictionary-based counting
- [ ] Basic reporting

### Phase 2: Enhancement
- [ ] Multiple log format support
- [ ] Configurable thresholds
- [ ] Pattern matching
- [ ] CSV/JSON export

### Phase 3: Production
- [ ] CLI interface
- [ ] Error handling
- [ ] Security considerations
- [ ] Documentation

## Security Considerations

- Validate log file paths (prevent path traversal)
- Handle malformed log entries gracefully
- Sanitize output to prevent injection in reports
- Implement safe error handling
- Use generic error messages
- Log analysis operations for audit trail

## File Structure

```
python-log-analyzer/
├── README.md                    # This file
├── log_analyzer.py              # Main script
├── requirements.txt             # Dependencies
├── test_logs/                   # Sample log files for testing
│   ├── auth.log.sample
│   └── sshd.log.sample
├── tests/                       # Unit tests
│   └── test_analyzer.py
└── docs/                        # Documentation
    └── security_considerations.md
```

## Dependencies

- Python 3.x
- (To be determined based on implementation)

## Testing Strategy

1. **Unit Tests**
   - Test log parsing functions
   - Test counting logic
   - Test threshold detection

2. **Integration Tests**
   - Test with sample log files
   - Test export functionality
   - Test CLI interface

3. **Security Tests**
   - Test with malicious file paths
   - Test with malformed logs
   - Verify error message safety

## Portfolio Value

This project demonstrates:
- Application of fundamental Python concepts to security
- Understanding of log analysis for security monitoring
- Ability to detect brute force attacks
- Practical security tool development

## Next Steps

1. Create basic log parsing prototype
2. Implement IP extraction and counting
3. Add threshold-based alerting
4. Create reporting functionality
5. Add CLI interface
6. Document security considerations

## Related Projects

- **File Integrity Monitor** - Complementary file security tool
- **Vulnerability Triage Tool** - Security operations tool

## References

- [OWASP A07: Identification and Authentication Failures](https://owasp.org/www-project-top-ten/2021/A07_2021-Identification_and_Authentication_Failures/)
- [OWASP A09: Security Logging and Monitoring Failures](https://owasp.org/www-project-top-ten/2021/A09_2021-Security_Logging_and_Monitoring_Failures/)

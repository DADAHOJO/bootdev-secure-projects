# File Integrity Monitor

A file integrity verification tool for detecting unauthorized modifications.

## Status

🔄 Planning Phase

## Overview

This project evolves from Boot.dev Python exercises (file handling, functions, dictionaries, error handling) to create a practical security tool for monitoring file integrity using cryptographic hashes.

## Boot.dev Concepts Applied

- **File Handling** - Reading files for hash calculation
- **Functions** - Modular hash operations
- **Dictionaries** - Storing file hash mappings
- **Error Handling** - Safe file operations
- **Hashing** - Cryptographic integrity verification (future learning)

## Security Mapping

### OWASP Top 10

**A08: Software and Data Integrity Failures**
- Detects unauthorized file modifications
- Verifies file integrity
- Alerts on changes

**A02: Cryptographic Failures**
- Uses secure hash algorithms
- Proper hash storage
- Hash comparison

## Features

### Planned Features

- [ ] Calculate SHA-256 hashes for files
- [ ] Store baseline in JSON/SQLite
- [ ] Compare current state to baseline
- [ ] Report changes (modified, new, deleted)
- [ ] Exclude certain files/directories
- [ ] Scheduled scanning support
- [ ] Recursive directory scanning
- [ ] Hash algorithm selection

### Prototype Structure

```python
import hashlib

def calculate_hash(filepath):
    """Calculate SHA-256 hash of file"""
    pass

def create_baseline(directory):
    """Create baseline hashes for directory"""
    pass

def compare_integrity(directory, baseline):
    """Compare current state to baseline"""
    pass

def generate_report(changes):
    """Generate integrity report"""
    pass
```

## Usage Example (Planned)

```bash
# Create baseline
python file_monitor.py --create-baseline /path/to/directory

# Check integrity
python file_monitor.py --check /path/to/directory

# Update baseline
python file_monitor.py --update-baseline /path/to/directory

# Exclude patterns
python file_monitor.py --check /path/to/directory --exclude "*.tmp" --exclude "*.log"
```

## Implementation Plan

### Phase 1: Prototype
- [ ] Basic hash calculation
- [ ] Single file integrity check
- [ ] Simple baseline storage

### Phase 2: Enhancement
- [ ] Directory scanning
- [ ] Recursive traversal
- [ ] JSON baseline storage
- [ ] Change detection

### Phase 3: Production
- [ ] CLI interface
- [ ] Exclusion patterns
- [ ] Scheduled scanning
- [ ] SQLite backend option

## Security Considerations

- Use SHA-256 or stronger hash algorithm
- Secure storage of baseline hashes
- Validate file paths before access
- Handle permission errors gracefully
- Protect hash database from tampering
- Handle symlinks and hard links securely

## File Structure

```
file-integrity-monitor/
├── README.md                    # This file
├── file_monitor.py              # Main script
├── requirements.txt             # Dependencies
├── test_files/                  # Sample files for testing
├── tests/                       # Unit tests
│   └── test_monitor.py
└── docs/                        # Documentation
    └── security_considerations.md
```

## Dependencies

- Python 3.x
- hashlib (standard library)
- (To be determined based on implementation)

## Testing Strategy

1. **Unit Tests**
   - Test hash calculation
   - Test baseline creation
   - Test comparison logic

2. **Integration Tests**
   - Test with sample directories
   - Test modification detection
   - Test exclusion patterns

3. **Security Tests**
   - Test with malicious file paths
   - Test hash database tampering
   - Test symlink handling

## Portfolio Value

This project demonstrates:
- Understanding of cryptographic integrity verification
- File system security knowledge
- Practical application of hashing
- Security monitoring tool development

## Next Steps

1. Implement SHA-256 hash calculation
2. Create baseline storage mechanism
3. Implement directory scanning
4. Add change detection logic
5. Create reporting functionality
6. Add CLI interface
7. Document security considerations

## Related Projects

- **Python Log Analyzer** - Complementary log security tool
- **Vulnerability Triage Tool** - Security operations tool

## References

- [OWASP A08: Software and Data Integrity Failures](https://owasp.org/www-project-top-ten/2021/A08_2021-Software_and_Data_Integrity_Failures/)
- [OWASP A02: Cryptographic Failures](https://owasp.org/www-project-top-ten/2021/A02_2021-Cryptographic_Failures/)
- [NIST SP 800-57 Part 1 Rev. 5](https://csrc.nist.gov/publications/detail/sp/800-57-part-1-rev-5/final) - Recommendation for Key Management

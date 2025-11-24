# Quick Reference: Enhanced Risk Scoring System

## 🎯 Risk Score Scale (1-1000)

| Score | Severity | Meaning | Action |
|-------|----------|---------|--------|
| **950-1000** | 🔴 **CRITICAL** | Confirmed compromised (specific version) | Immediate action required |
| **850-900** | 🟠 **HIGH** | Potentially compromised (all versions) | Action within 24 hours |
| **600-700** | 🟡 **MEDIUM** | Suspicious patterns | Review within 1 week |
| **300-400** | 🔵 **LOW** | Low-risk finding | Monitor |
| **100** | ℹ️ **INFO** | Safe version (monitored package) | Awareness only |
| **50** | ✅ **CLEAN** | Not affected by Shai Halud | No action needed |

---

## 🔄 Duplicate Detection

When the same compromised package appears multiple times:
- **CRITICAL**: +5 points per duplicate (max +50)
- **HIGH**: +3 points per duplicate (max +30)

**Example:**
```
Package: @ctrl/tinycolor@4.1.1 (appears 2x)
Base Risk: 950 + Duplicate Penalty: 5 = Final Risk: 955/1000
```

---

## 📊 Finding Types

### 1. CRITICAL (950-1000) - Confirmed Compromised
```
[Risk Score: 950/1000] CONFIRMED COMPROMISED package detected: 
@ctrl/tinycolor@4.1.1 (known compromised versions: 4.1.1, 4.1.2)

🚨 CRITICAL (Risk: 950/1000): IMMEDIATELY update to safe version 4.1.0
```

### 2. HIGH (850-900) - Potentially Compromised
```
[Risk Score: 850/1000] POTENTIALLY COMPROMISED package detected: 
posthog-js@1.100.0 (ALL VERSIONS potentially compromised - no version info available)

⚠️ HIGH RISK (Risk: 850/1000): Assume ALL versions compromised. 
Consider removing or finding verified alternative.
```

### 3. INFO (100) - Safe Version
```
[Risk Score: 100/1000] Safe version detected: @ctrl/tinycolor@4.1.0 
(compromised versions: 4.1.1, 4.1.2)

ℹ️ Package is using a safe version. Continue monitoring.
```

### 4. CLEAN (50) - Not Affected
```
[Risk Score: 50/1000] Library express version 4.18.2 is not affected by Shai Halud

✓ Not affected. No action required.
```

---

## 🧪 Testing

### Test File Location
```
test_comprehensive_scan/package.json
```

### Run Test
```bash
python3 enhanced_npm_compromise_detector_phoenix.py test_comprehensive_scan/
```

### Expected Results
- CRITICAL: 17 packages (includes duplicates)
- HIGH: 14 packages
- INFO: 3 packages
- CLEAN: 11 packages

---

## 📋 Quick Commands

### Scan a Project
```bash
python3 enhanced_npm_compromise_detector_phoenix.py /path/to/project/
```

### Scan with Phoenix Import
```bash
python3 enhanced_npm_compromise_detector_phoenix.py /path/to/project/ \
  --enable-phoenix
```

### Scan with All Libraries
```bash
python3 enhanced_npm_compromise_detector_phoenix.py /path/to/project/ \
  --enable-phoenix --import-all
```

---

## 🔍 Understanding Findings

### Metadata in Phoenix Findings
```json
{
  "severity": "950.0",
  "details": {
    "risk_score": 950,
    "risk_score_max": 1000,
    "risk_level": "CRITICAL",
    "is_confirmed_compromised": true,
    "is_potentially_compromised": false,
    "is_duplicate": true,
    "duplicate_count": 2
  }
}
```

---

## 🎯 Prioritization Guide

### Immediate (0-24h)
- Risk Score: 900-1000
- Packages: CRITICAL + HIGH duplicates
- Action: Stop using, update immediately

### High Priority (1-7 days)
- Risk Score: 800-899
- Packages: HIGH (potentially compromised)
- Action: Audit, find alternatives

### Medium Priority (1-4 weeks)
- Risk Score: 600-799
- Packages: MEDIUM suspicious
- Action: Review, monitor

### Low Priority (Monitor)
- Risk Score: < 600
- Packages: LOW, INFO, CLEAN
- Action: Awareness, continue monitoring

---

## 📚 Documentation

- **Complete Update Guide**: `SCANNER_RISK_SCORING_UPDATE.md`
- **Test Documentation**: `test_comprehensive_scan/README.md`
- **Usage Guide**: `docs/USAGE_GUIDE.md`
- **Phoenix Integration**: `docs/PHOENIX_INTEGRATION_GUIDE.md`

---

## ✅ Quick Validation

Check if your scan is working correctly:

1. **Risk Scores Displayed**: ✓ Findings show `[Risk Score: X/1000]`
2. **Severity Levels**: ✓ CRITICAL, HIGH, INFO, CLEAN detected
3. **Duplicate Detection**: ✓ Duplicates show increased risk
4. **Potentially Compromised**: ✓ HIGH findings note "ALL VERSIONS"
5. **Phoenix Metadata**: ✓ Includes risk_score, is_duplicate, etc.

---

**Version**: 2.0  
**Last Updated**: November 24, 2025  
**Database**: 608 packages (198 confirmed + 410 potentially compromised)


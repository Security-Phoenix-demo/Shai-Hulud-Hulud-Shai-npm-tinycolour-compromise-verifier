# Comprehensive Security Test Package

## Purpose
This test package is designed to validate the enhanced NPM compromise detector with the new risk scoring system (1-1000 scale) and duplicate detection features.

## Test Coverage

### 1. CRITICAL Risk (950-1000) - Confirmed Compromised Packages
These packages have specific versions that are confirmed compromised:

**In dependencies:**
- `@ctrl/tinycolor@4.1.1` - Risk: 950 (compromised version)
- `@ctrl/ngx-codemirror@7.0.1` - Risk: 950
- `@ctrl/ngx-emoji-mart@9.2.1` - Risk: 950
- `@nativescript-community/perms@3.0.5` - Risk: 950
- `@nativescript-community/sqlite@3.5.2` - Risk: 950
- `@operato/board@9.0.36` - Risk: 950
- `@operato/utils@9.0.22` - Risk: 950
- `angulartics2@14.1.1` - Risk: 950
- `another-shai@1.0.1` - Risk: 950
- `@things-factory/auth-base@9.0.43` - Risk: 950
- `@things-factory/email-base@9.0.42` - Risk: 950

**In devDependencies:**
- `ngx-toastr@19.0.1` - Risk: 950
- `@rxap/ngx-bootstrap@19.0.3` - Risk: 950
- `eslint-config-teselagen@6.1.7` - Risk: 950
- `@teriyakibomb/ember-velcro@2.2.1` - Risk: 950

**In peerDependencies:**
- `@ctrl/ngx-rightclick@4.0.1` - Risk: 950

### 2. HIGH Risk (850-900) - Potentially Compromised Packages
These packages are potentially compromised with NO version information available:

**In dependencies:**
- `posthog-js@1.100.0` - Risk: 850 (ALL versions potentially compromised)
- `@posthog/plugin-server@1.50.0` - Risk: 850
- `@asyncapi/cli@1.2.10` - Risk: 850
- `@asyncapi/parser@3.0.0` - Risk: 850
- `@ensdomains/ensjs@4.0.0` - Risk: 850
- `ethereum-ens@0.8.0` - Risk: 850
- `@postman/postman-mcp-server@2.0.0` - Risk: 850
- `@zapier/zapier-sdk@14.0.0` - Risk: 850
- `mcp-use@1.0.0` - Risk: 850
- `posthog-node@3.0.0` - Risk: 850

**In devDependencies:**
- `@posthog/rrweb@2.0.0` - Risk: 850
- `@asyncapi/generator@1.15.0` - Risk: 850

**In optionalDependencies:**
- `@posthog/zendesk-plugin@1.0.0` - Risk: 850
- `@ensdomains/ens-contracts@1.2.0` - Risk: 850

### 3. INFO Risk (100) - Safe Versions of Monitored Packages
These are safe versions of packages that have other compromised versions:

**In devDependencies:**
- `@ctrl/tinycolor@4.1.0` - Risk: 100 (safe version, 4.1.1-4.1.2 are compromised)
- `@nativescript-community/sentry@4.6.42` - Risk: 100 (safe version)
- `@operato/graphql@9.0.22` - Risk: 100 (safe version)

**In peerDependencies:**
- `@things-factory/integration-base@9.0.42` - Risk: 100 (safe version)

### 4. CLEAN Risk (50) - Not Affected by Shai Halud
These packages are not in the compromise database at all:

- `express@4.18.2` - Risk: 50
- `lodash@4.17.21` - Risk: 50
- `react@18.2.0` - Risk: 50
- `vue@3.3.4` - Risk: 50
- `axios@1.4.0` - Risk: 50
- `typescript@5.2.0` - Risk: 50
- `webpack@5.88.0` - Risk: 50
- `eslint@8.50.0` - Risk: 50
- `prettier@3.0.0` - Risk: 50
- `jest@29.6.0` - Risk: 50
- `mocha@10.2.0` - Risk: 50

### 5. Duplicate Detection Test
The following package appears in BOTH dependencies and devDependencies with different versions to test duplicate detection:

- `@ctrl/tinycolor`
  - In dependencies: `4.1.1` (COMPROMISED - Risk: 950+)
  - In devDependencies: `4.1.0` (SAFE - Risk: 100)

This tests the scanner's ability to:
- Detect the same package in different dependency types
- Apply different risk scores based on version
- Increment risk score for duplicates of compromised packages

## Expected Results

### Risk Score Distribution
- **CRITICAL (950-1000)**: 16 packages (with potential duplicate penalties)
- **HIGH (850-900)**: 14 packages
- **INFO (100)**: 4 packages
- **CLEAN (50)**: 11 packages

### Total Findings
- **Compromised**: 30 packages total (16 confirmed + 14 potentially)
- **Safe/Clean**: 15 packages total (4 safe versions + 11 clean)
- **Total Packages**: 45 packages

## Running the Test

### Basic Scan
```bash
python3 enhanced_npm_compromise_detector_phoenix.py test_comprehensive_scan/
```

### With Phoenix Integration
```bash
python3 enhanced_npm_compromise_detector_phoenix.py test_comprehensive_scan/ --enable-phoenix
```

### With Full Tree Analysis
```bash
python3 enhanced_npm_compromise_detector_phoenix.py test_comprehensive_scan/ --full-tree-analysis
```

### With All Libraries Import
```bash
python3 enhanced_npm_compromise_detector_phoenix.py test_comprehensive_scan/ --enable-phoenix --import-all
```

## Expected Output Highlights

### Confirmed Compromised (CRITICAL)
```
🚨 CRITICAL (Risk: 950/1000): CONFIRMED COMPROMISED package detected: @ctrl/tinycolor@4.1.1
   Remedy: IMMEDIATELY update @ctrl/tinycolor to safe version 4.1.0
```

### Potentially Compromised (HIGH)
```
⚠️ HIGH RISK (Risk: 850/1000): POTENTIALLY COMPROMISED package detected: posthog-js@1.100.0
   (ALL VERSIONS potentially compromised - no version info available)
   Remedy: Assume ALL versions are compromised. Consider removing or finding alternative.
```

### Duplicate Detection
```
🚨 CRITICAL (Risk: 955/1000): CONFIRMED COMPROMISED package detected: @ctrl/tinycolor@4.1.1
   (DUPLICATE: found 2 times - increased severity)
```

### Safe Version
```
ℹ️ INFO (Risk: 100/1000): Safe version detected: @ctrl/tinycolor@4.1.0
   (compromised versions: 4.1.1, 4.1.2)
```

### Clean Package
```
✓ CLEAN (Risk: 50/1000): Library express version 4.18.2 is not affected by Shai Halud
```

## Risk Score Explanation

The new risk scoring system uses a 1-1000 scale:

| Risk Range | Severity | Description |
|------------|----------|-------------|
| 950-1000 | CRITICAL | Confirmed compromised with specific version |
| 850-900 | HIGH | Potentially compromised (all versions) |
| 600-700 | MEDIUM | Suspicious patterns or indicators |
| 300-400 | LOW | Low-risk findings |
| 100 | INFO | Safe version of monitored package |
| 50 | CLEAN | Not affected by Shai Halud |

### Duplicate Penalty
- CRITICAL packages: +5 points per duplicate (max +50)
- HIGH packages: +3 points per duplicate (max +30)

## Test Validation Checklist

- [ ] All 16 CRITICAL packages detected
- [ ] All 14 HIGH (potentially compromised) packages detected
- [ ] All 4 INFO (safe versions) packages identified
- [ ] All 11 CLEAN packages identified
- [ ] Duplicate detection works (@ctrl/tinycolor appears twice)
- [ ] Risk scores are in correct ranges (1-1000)
- [ ] Duplicate penalty applied correctly
- [ ] Descriptions include risk scores
- [ ] Remedies are appropriate for risk level
- [ ] Phoenix findings include detailed metadata

## Database Version
- **Database**: compromised_packages_2025.json v2.0
- **Total Packages in DB**: 608 (198 confirmed + 410 potentially compromised)
- **Last Updated**: 2025-11-24

## Notes

This test package intentionally includes a mix of:
- **Production dependencies** with various risk levels
- **Development dependencies** to test devDependencies scanning
- **Peer dependencies** to test peerDependencies scanning
- **Optional dependencies** to test optionalDependencies scanning
- **Duplicate packages** with different versions
- **Clean packages** from popular frameworks

The test validates the scanner's ability to:
1. Correctly identify all types of compromised packages
2. Apply appropriate risk scores on 1-1000 scale
3. Detect and penalize duplicates
4. Distinguish between confirmed and potentially compromised
5. Provide contextual remediation advice
6. Generate accurate Phoenix Security findings


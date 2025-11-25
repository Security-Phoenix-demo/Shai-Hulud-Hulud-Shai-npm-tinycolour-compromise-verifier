# Changelog
## NPM Package Compromise Detector - 2025 Updates

All notable changes to the compromised packages database and detection tools.

---

## [4.0.0] - 2025-11-25 - **4TH WAVE MAJOR UPDATE**

### 🚨 **CRITICAL SECURITY ALERT**

This is the largest update to date, confirming **482 additional packages** as compromised and bringing the total to **690 confirmed compromised packages** across **37 organizations**.

### Added - Compromised Packages (482 total)

#### Major Organization Compromises

**@asyncapi (37 packages)**
- All AsyncAPI generator, parser, template, and tooling packages
- Includes: `@asyncapi/cli`, `@asyncapi/generator`, `@asyncapi/parser`, `@asyncapi/modelina`
- Plus all templates: java, nodejs, python, php, go, dotnet, html, markdown
- **Impact**: API development, code generation, documentation tools

**@posthog (56 packages)**
- Complete PostHog analytics ecosystem compromised
- Core packages: `posthog-js`, `posthog-node`, `posthog-react-native`
- All plugins: geoip, twilio, sendgrid, snowflake, postgres, and 40+ more
- Session replay packages: `@posthog/rrweb`, `@posthog/rrweb-player`, etc.
- **Impact**: Analytics, user tracking, session replay, data export

**@postman (19 packages)**
- Postman MCP integration and CLI tools
- Platform binaries: linux-x64, macos-arm64, macos-x64, windows-x64
- Testing tools: wdio-allure-reporter, wdio-junit-reporter
- **Impact**: API testing, development tools, CI/CD pipelines

**@ensdomains (47 packages)**
- Complete ENS (Ethereum Name Service) ecosystem
- Core packages: `@ensdomains/ensjs`, `@ensdomains/ens-contracts`
- Resolver and gateway packages
- Development tools: hardhat plugins, viem extensions
- **Impact**: Web3 development, Ethereum integration, blockchain applications

**@voiceflow (43 packages)**
- Complete Voiceflow conversational AI platform
- SDK and runtime packages
- Type definitions and configuration packages
- NestJS integrations and common utilities
- **Impact**: Conversational AI, chatbot development, voice applications

**@kvytech (10 packages)**
- Medusa e-commerce plugins
- All Medusa plugins: announcement, newsletter, product-reviews, promotion
- **Impact**: E-commerce platforms using Medusa

**@quick-start-soft (9 packages)**
- Markdown processing and document tools
- Translation and image processing utilities
- **Impact**: Documentation tools, content management

**@actbase (14 packages)**
- React Native mobile development packages
- Korean app development tools (Kakao, Naver integrations)
- **Impact**: Mobile app development, Korean market apps

#### Additional Organization Compromises

**@fishingbooker** (4 packages)
- React components: swiper, loader, pagination
- Browser sync plugin

**@accordproject** (3 packages)
- Concerto analysis, markdown processing
- Contract and legal tech tooling

**@voiceflow** - See major section above (43 packages)

**@hover-design** (2 packages)
- React and core design system packages

**@faq-component** (2 packages)
- React and core FAQ components

**@antstackio** (3 packages)
- Express GraphQL proxy, JSON to GraphQL converter
- ESLint configuration

**@pruthvi21** (1 package)
- use-debounce React hook

**@lpdjs** (1 package)
- Firestore repository service

#### Individual Package Compromises (250+)

**React Native & Mobile (20+)**
- `react-native-use-modal`, `react-native-worklet-functions`
- `react-native-email`, `react-native-phone-call`, `react-native-fetch`
- `react-native-jam-icons`, `react-native-log-level`, `react-native-websocket`
- `expo-audio-session`, `react-native-datepicker-modal`
- All `@strapbuild/react-native-*` perspective image cropper variants

**Blockchain & Web3 (15+)**
- `ethereum-ens`, `crypto-addr-codec`
- `create-hardhat3-app`, `test-hardhat-app`, `test-foundry-app`
- `evm-checkcode-cli`, `gate-evm-tools-test`, `gate-evm-check-code2`
- `bytecode-checker-cli`, `web-types-htmx`, `web-types-lit`

**MCP & AI Tools (12+)**
- `@mcp-use/cli`, `@mcp-use/inspector`, `@mcp-use/mcp-use`, `mcp-use`
- `create-mcp-use-app`, `lite-serper-mcp-server`
- `claude-token-updater`, `n8n-nodes-tmdb`, `n8n-nodes-viral-app`
- `@hapheus/n8n-nodes-pgp`, `dialogflow-es`

**Development Tools (30+)**
- `bun-plugin-httpfile`, `vite-plugin-httpfile`
- `axios-builder`, `axios-cancelable`, `axios-timed`
- `redux-forge`, `redux-router-kit`
- `kill-port`, `shell-exec`, `get-them-args`
- `eslint-config-zeallat-base`, `eslint-config-trigo`
- `github-action-for-generator`, `create-glee-app`

**Testing & Quality (15+)**
- `@lessondesk/babel-preset`, `@lessondesk/eslint-config`
- `formik-error-focus`, `formik-store`
- `lint-staged-imagemin`, `enforce-branch-name`

**UI Components (20+)**
- `react-library-setup`, `react-component-taggers`, `react-element-prompt-inspector`
- `react-jam-icons`, `react-qr-image`, `react-keycloak-context`
- `orbit-soap`, `orbit-boxicons`, `orbit-nebula-editor`, `orbit-nebula-draw-tools`
- `@orbitgtbelgium/*` mapbox drawing tools and components

**Utilities (40+)**
- `tenacious-fetch`, `just-toasty`, `compare-obj`, `flatten-unflatten`
- `bytes-to-x`, `cpu-instructions`, `exact-ticker`
- `image-to-uri`, `set-nested-prop`, `url-encode-decode`
- `license-o-matic`, `barebones-css`, `nanoreset`, `wenk`
- `sort-by-distance`, `fuzzy-finder`, `feature-flip`, `fittxt`, `flapstacks`

**Korean Market Specific (8+)**
- `korea-administrative-area-geo-json-util`
- `shinhan-limit-scrap`, `calc-loan-interest`
- `scgs-capacitor-subscribe`, `scgsffcreator`

**Capacitor Plugins (7+)**
- `capacitor-plugin-apptrackingios`, `capacitor-plugin-purchase`
- `capacitor-plugin-scgssigninwithgoogle`
- `capacitor-purchase-history`, `capacitor-voice-recorder-wav`

**Miscellaneous Compromised (50+)**
- `jan-browser`, `discord-bot-server`, `chrome-extension-downloads`
- `coinmarketcap-api`, `luno-api`, `pico-uid`
- `token.js-fork`, `typeorm-orbit`, `gitsafe`
- `designstudiouiux`, `hyperterm-hipster`, `command-irail`
- `jacob-zuma`, `ito-button`, `poper-react-sdk`
- And many more...

### Changed

**Database Statistics:**
- **Confirmed compromised packages**: 208 → **690** (+482)
- **Potentially compromised packages**: 400 → **0** (-400, all moved to confirmed + 82 new)
- **Total packages in database**: 608 → **690**
- **Affected organizations**: 29 → **37** (+8 new major organizations)

**All packages now have "all" versions marked as compromised** where specific version information was not available.

### Impact Assessment

**Critical Impact Sectors:**
1. **API Development**: AsyncAPI toolchain completely compromised
2. **Analytics & Tracking**: PostHog ecosystem fully compromised
3. **Web3/Blockchain**: ENS and Ethereum tooling compromised
4. **Mobile Development**: React Native and Capacitor plugins affected
5. **AI/Conversational Interfaces**: Voiceflow and Dialogflow compromised
6. **E-commerce**: Medusa plugins affected
7. **Testing & Development Tools**: Wide range of dev tools compromised

**Recommended Actions:**
1. **IMMEDIATE**: Scan all projects with updated database
2. **URGENT**: Remove or replace all 690 compromised packages
3. **CRITICAL**: Review projects using @asyncapi, @posthog, @postman, @ensdomains, @voiceflow
4. **IMPORTANT**: Check for data exfiltration from analytics and tracking packages
5. **REQUIRED**: Audit Web3 applications for wallet compromise
6. **ESSENTIAL**: Review mobile apps for permissions and data access

---

## [3.0.0] - 2025-11-24 - **Zapier Packages Update**

### Added - Zapier Compromised Packages (10 packages)

**With Specific Versions (8 packages):**
1. `@zapier/zapier-sdk` - versions 0.15.5, 0.15.6, 0.15.7 (safe: 0.15.4)
2. `zapier-platform-core` - versions 18.0.2, 18.0.3, 18.0.4 (safe: 18.0.1)
3. `zapier-platform-cli` - versions 18.0.2, 18.0.3, 18.0.4 (safe: 18.0.1)
4. `zapier-platform-schema` - versions 18.0.2, 18.0.3, 18.0.4 (safe: 18.0.1)
5. `@zapier/mcp-integration` - versions 3.0.1, 3.0.2, 3.0.3 (safe: 3.0.0)
6. `@zapier/secret-scrubber` - versions 1.1.3, 1.1.4, 1.1.5 (safe: 1.1.2)
7. `@zapier/ai-actions-react` - versions 0.1.12, 0.1.13, 0.1.14 (safe: 0.1.11)
8. `@zapier/stubtree` - versions 0.1.2, 0.1.3, 0.1.4 (safe: 0.1.1)

**All Versions Affected (2 packages):**
9. `@zapier/babel-preset-zapier` - all versions
10. `@zapier/eslint-plugin-zapier` - all versions

### Changed
- **Confirmed compromised**: 198 → 208 (+10)
- **Potentially compromised**: 410 → 400 (-10)
- **Organizations affected**: 29 (added @zapier)

### Added - Features
- Enhanced scanner logic to handle "all" versions case
- Improved detection for packages with all versions compromised

---

## [2.0.0] - 2025-11-24 - **Test Variations & Features**

### Added - Test Infrastructure
- `test_variations/mobile-focused/` - 17 mobile packages, 7 clean
- `test_variations/backend-api-focused/` - 21 backend packages, 8 clean
- `test_variations/frontend-web-focused/` - 25 frontend packages, 10 clean
- `test_zapier_confirmed/` - All 10 Zapier packages

### Added - Scanner Features
- `--pull-all` mode for auto-discovering GitHub repositories
- `--detail-log` mode for complete library visibility
- `--delete-local-files` for automatic cleanup
- `--import-all` for importing clean libraries to Phoenix
- Custom tags support for Phoenix findings and assets

### Changed - Scanner Improvements
- Dual-scale risk scoring (1-1000 internal, 1-10 Phoenix API)
- Duplicate package detection with severity escalation
- Enhanced Phoenix API integration
- Automatic GitHub API fallback system

---

## [1.0.0] - 2025-09-17 - **Initial Release**

### Added - Initial Database
- **198 confirmed compromised packages** with specific versions
- **410 potentially compromised packages** without version info
- **29 organizations affected**

### Major Affected Organizations (Initial)
- @ctrl - 15 packages
- @nativescript-community - 25 packages
- @art-ws - 15 packages
- @crowdstrike - 10 packages
- @operato - 15 packages
- @teselagen - 10 packages
- @things-factory - 8 packages
- @nstudio - 8 packages

### Added - Detection Tools
- Shell script scanner (`quick-check-compromised-packages-2025.sh`)
- Python comprehensive scanner (`npm_package_compromise_detector_2025.py`)
- Phoenix Security integration (`enhanced_npm_compromise_detector_phoenix.py`)
- Multiple test cases and validation suites

---

## Summary Statistics

| Version | Date | Confirmed | Potentially | Total | Orgs | Change |
|---------|------|-----------|-------------|-------|------|--------|
| 4.0.0 | 2025-11-25 | **690** | 0 | **690** | **37** | +482 confirmed |
| 3.0.0 | 2025-11-24 | 208 | 400 | 608 | 29 | +10 Zapier |
| 2.0.0 | 2025-11-24 | 208 | 400 | 608 | 29 | Features |
| 1.0.0 | 2025-09-17 | 198 | 410 | 608 | 29 | Initial |

---

## Links

- [4th Wave Summary](4TH_WAVE_SUMMARY.md)
- [Zapier Update](ZAPIER_CONFIRMED_PACKAGES_UPDATE.md)
- [Pull-All Feature](PULL_ALL_FEATURE_GUIDE.md)
- [Test Variations](TEST_VARIATIONS_SUMMARY.md)
- [Complete README](README.md)

---

**Last Updated**: November 25, 2025  
**Database Version**: 4.0.0  
**Total Packages**: 690 confirmed compromised  
**Status**: 🚨 **CRITICAL** - Immediate action required for all users


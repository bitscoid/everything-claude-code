# everything-claude-code Development Patterns

> Auto-generated skill from repository analysis

## Overview

This repository is a comprehensive collection of AI coding tools, skills, agents, and configurations designed for cross-platform compatibility across multiple AI coding environments (Claude, Cursor, OpenCode, Codex). It serves as a centralized hub for AI development patterns, featuring multi-language documentation and standardized workflows for maintaining consistency across different AI coding platforms.

## Coding Conventions

### File Naming
- Use **camelCase** for JavaScript files: `skillManager.js`, `hookHandler.js`
- Use kebab-case for directory names: `skill-addition`, `cross-platform-sync`
- SKILL.md files always use UPPERCASE for the filename

### Import/Export Patterns
```javascript
// Mixed import styles supported
import { skillManager } from './skillManager.js';
const { hookHandler } = require('./hookHandler');

// Mixed export styles supported
export { newFunction };
module.exports = { legacyFunction };
```

### Directory Structure
```
skills/[skill-name]/SKILL.md
.cursor/skills/[skill-name]/SKILL.md
.agents/skills/[skill-name]/SKILL.md
.agents/skills/[skill-name]/agents/openai.yaml
```

### Commit Message Conventions
- **Format:** `type: description` (average 73 characters)
- **Types:** `feat`, `fix`, `chore`, `test`
- **Examples:**
  - `feat: add new skill for API integration`
  - `chore: release v2.1.0`
  - `fix: resolve cross-platform sync issue`

## Workflows

### Skill Addition
**Trigger:** When adding a new skill to the repository
**Command:** `/add-skill`

1. Create `SKILL.md` file in `skills/[skill-name]/`
2. Copy skill to `.cursor/skills/[skill-name]/SKILL.md`
3. Copy skill to `.agents/skills/[skill-name]/SKILL.md`
4. Add `openai.yaml` metadata to `.agents/skills/[skill-name]/agents/`
5. Update `README.md` skill count and directory listing
6. Update `.codex/AGENTS.md` with new skill reference

```yaml
# Example openai.yaml structure
name: "skill-name"
description: "Brief skill description"
version: "1.0.0"
platform: "openai"
```

### Cross-Platform Sync
**Trigger:** When maintaining feature parity across AI coding platforms
**Command:** `/sync-platforms`

1. Update main skill/agent/rule file
2. Copy to `.cursor/` directory with platform-specific formatting
3. Copy to `.agents/` directory with openai.yaml metadata
4. Update `.codex/AGENTS.md` references
5. Update `.opencode/` configuration files
6. Update `README.md` cross-platform parity table

### Plugin Manifest Update
**Trigger:** When updating plugin version or configuration
**Command:** `/update-plugin`

1. Update version in `package.json`
2. Update `.claude-plugin/plugin.json` with new version
3. Update `.claude-plugin/marketplace.json` with version and metadata
4. Sync agent/skill declarations between manifests
5. Run validation checks

```json
{
  "version": "2.1.0",
  "name": "everything-claude-code",
  "skills": ["skill1", "skill2"],
  "agents": ["agent1", "agent2"]
}
```

### Hook System Update
**Trigger:** When adding new hooks or modifying hook behavior
**Command:** `/add-hook`

1. Update `hooks/hooks.json` with new hook configuration
2. Add/modify hook script in `scripts/hooks/`
3. Copy hook configuration to `.cursor/hooks.json` if needed
4. Add corresponding hook script to `.cursor/hooks/`
5. Update `hooks/README.md` documentation

### Release Workflow
**Trigger:** When publishing a new version
**Command:** `/release`

1. Update version in `package.json`
2. Update `.claude-plugin/plugin.json` and `marketplace.json` versions
3. Update `.opencode/package.json` version
4. Update `README.md` with new stats/features
5. Run `scripts/release.sh`
6. Create release commit with `chore: release vX.X.X` message

### Pull Request Merge
**Trigger:** When merging community contributions
**Command:** `/merge-pr`

1. Review contributed skill/agent/rule files
2. Merge with `Merge pull request #X` message format
3. Add `LGTM — [description]` comment in commit message
4. Ensure security validation for any scripts
5. Update relevant documentation if needed

### Documentation Maintenance
**Trigger:** When updating documentation or stats
**Command:** `/update-docs`

1. Update main `README.md` with new counts/features
2. Update `README.zh-CN.md` for Chinese documentation
3. Update `docs/ja-JP/README.md` for Japanese documentation
4. Update `docs/zh-TW/README.md` for Traditional Chinese
5. Ensure consistency across all language versions

## Testing Patterns

### Test File Structure
- Test files follow pattern: `*.test.js`
- Tests are co-located with source files when possible
- Framework: Not specifically detected, but JavaScript-based

```javascript
// Example test structure
describe('Skill Manager', () => {
  test('should add new skill correctly', () => {
    // Test implementation
  });
});
```

## Commands

| Command | Purpose | Frequency |
|---------|---------|-----------|
| `/add-skill` | Add new skill across all platforms | ~8x/month |
| `/sync-platforms` | Sync configurations across AI platforms | ~4x/month |
| `/update-plugin` | Update plugin manifests and versions | ~3x/month |
| `/add-hook` | Add or modify hook configurations | ~3x/month |
| `/release` | Publish new version with version bumps | ~1x/month |
| `/merge-pr` | Merge community contributions safely | ~6x/month |
| `/update-docs` | Update multilingual documentation | ~4x/month |